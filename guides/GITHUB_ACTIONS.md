# GitHub Actions for Profile Management

Optional GitHub Actions workflows for automating profile maintenance and updates.

## Overview

The GitHub Actions workflow helps you:
- 📊 Update stats and metrics automatically
- ✅ Validate profile markdown
- 🔍 Check badge URLs for broken links
- 📅 Schedule regular profile reviews

## Workflows Included

### 1. Profile Update Workflow

**File:** `.github/workflows/profile-update.yml`

**Purpose:** Automatically update profile stats and validate content

**Triggers:**
- Manual trigger (workflow_dispatch)
- Monthly schedule (1st of each month)

**What it does:**
- Validates README.md exists
- Checks for required profile sections
- Verifies badge URLs are accessible
- Commits changes if updates detected

### 2. How to Use

#### Option A: Manual Trigger

1. Go to your GitHub repository
2. Click "Actions" tab
3. Select "Profile Update Workflow"
4. Click "Run workflow"
5. Wait for completion

#### Option B: Automatic Schedule

The workflow runs automatically on the 1st of each month. No action needed.

#### Option C: Custom Schedule

To change the schedule, edit `.github/workflows/profile-update.yml`:

```yaml
schedule:
  - cron: '0 0 1 * *'  # Change this cron expression
```

**Cron Expression Explanation:**
- `0 0 1 * *` = 1st of month at midnight UTC
- `0 12 * * 0` = Every Sunday at noon UTC
- `0 0 * * *` = Every day at midnight UTC
- `0 */4 * * *` = Every 4 hours

[Cron Expression Help](https://crontab.guru/)

## Available Automations

### Stats Update

Automatically fetch and update:
- GitHub stats
- Contribution counts
- Most used languages
- Recent activity

**Enable by:** Customizing the workflow with API calls to:
- GitHub API for stats
- Badge services for metrics
- Analytics tools

### Badge Validation

Check all badge URLs in your README:
- Shields.io badges
- GitHub-readme-stats
- Profile views counter
- Trophy badges

**Enable by:** Running URL validation in the workflow

### Markdown Validation

Ensure README.md is properly formatted:
- Valid markdown syntax
- All links are working
- All images load correctly
- No broken formatting

**Enable by:** Using markdown linters in the workflow

### Content Checks

Verify profile content:
- Contact information present
- Tech stack properly formatted
- Social links included
- Call-to-action present

**Enable by:** Customizing regex patterns in the workflow

## Customization Guide

### Modify the Workflow

1. Open `.github/workflows/profile-update.yml`
2. Edit the steps as needed
3. Commit and push
4. Workflow will run automatically

### Add New Steps

Example: Add step to update stats from API

```yaml
- name: Update GitHub Stats
  run: |
    # Fetch stats from GitHub API
    curl -H "Authorization: token ${{ secrets.GITHUB_TOKEN }}" \
      https://api.github.com/users/[YOUR-USERNAME]
    
    # Update README with new stats
    # Add sed/awk commands to replace placeholders
```

### Add Notifications

Send workflow status notifications:

```yaml
- name: Notify on Success
  if: success()
  run: echo "✓ Profile validation passed!"

- name: Notify on Failure
  if: failure()
  run: echo "✗ Profile validation failed!"
```

## Advanced Automations

### Auto-Update README from Template

Automatically regenerate README from a template:

```bash
# In your workflow
cp templates/professional-readme.md README.md
sed -i 's/\[YOUR-NAME\]/Your Name/g' README.md
sed -i 's/\[YOUR-ROLE\]/Your Role/g' README.md
git add README.md
git commit -m "Auto-update README from template"
```

### Fetch Latest Stats from APIs

```bash
# Get GitHub stats
STATS=$(curl -s https://api.github.com/users/[USERNAME])

# Parse JSON and update README
STARS=$(echo $STATS | jq '.public_repos')
FOLLOWERS=$(echo $STATS | jq '.followers')

# Update README with values
sed -i "s/STARS_COUNT/$STARS/g" README.md
sed -i "s/FOLLOWERS_COUNT/$FOLLOWERS/g" README.md
```

### Validate All Links

```bash
# Install link checker
npm install -g broken-link-checker

# Check README.md for broken links
blc file:///$(pwd)/README.md -r
```

### Generate Profile Report

```bash
# Create a report of profile statistics
echo "# Profile Report" > PROFILE_REPORT.md
echo "Generated: $(date)" >> PROFILE_REPORT.md
echo "## Statistics" >> PROFILE_REPORT.md
echo "- Repos: $(curl -s https://api.github.com/users/[USERNAME] | jq '.public_repos')" >> PROFILE_REPORT.md
```

## Troubleshooting Workflows

### Workflow Not Running

1. **Check if Actions are enabled:**
   - Go to Settings → Actions → General
   - Verify "Actions permissions" allows workflows

2. **Check workflow file syntax:**
   - GitHub highlights syntax errors
   - Use yamllint to validate YAML

3. **Check run permissions:**
   - Ensure the action has necessary permissions
   - Add `permissions:` section if needed

### Workflow Fails on Commit

1. **Check git configuration:**
   ```yaml
   - name: Configure git
     run: |
       git config --local user.email "action@github.com"
       git config --local user.name "GitHub Action"
   ```

2. **Check repository permissions:**
   - Ensure the workflow has `contents: write` permission

3. **Check for merge conflicts:**
   - Multiple workflows may conflict
   - Use `git pull` before committing

### Badge URLs Return 404

1. **Verify URLs are correct:**
   - Check shields.io badges load in browser
   - Verify github-readme-stats endpoint

2. **Check for rate limiting:**
   - Badge services may rate-limit requests
   - Add delay between API calls

3. **Validate against live badges:**
   - Compare with working examples

## Security Considerations

### Secrets Management

If using GitHub API tokens:

1. **Create a personal access token:**
   - Go to Settings → Developer settings → Personal access tokens
   - Create new token with `repo` scope

2. **Store as secret:**
   - Go to repository Settings → Secrets and variables → Actions
   - Click "New repository secret"
   - Name: `GITHUB_TOKEN`
   - Value: Your token

3. **Use in workflow:**
   ```yaml
   - name: Use Token
     run: echo "Token exists" 
     env:
       TOKEN: ${{ secrets.GITHUB_TOKEN }}
   ```

### Best Practices

- ✅ Never commit tokens in code
- ✅ Use repository secrets for sensitive data
- ✅ Use minimal token scope (least privilege)
- ✅ Rotate tokens regularly
- ✅ Log out of actions when done

## Examples

### Example 1: Daily Stats Update

```yaml
name: Daily Stats Update
on:
  schedule:
    - cron: '0 0 * * *'  # Daily at midnight

jobs:
  update:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Update stats
        run: |
          # Your update script here
          echo "Stats updated"
      - name: Commit
        run: |
          git config user.name "bot"
          git config user.email "bot@example.com"
          git add README.md
          git commit -m "Update stats" || true
          git push
```

### Example 2: Weekly Validation

```yaml
name: Weekly Validation
on:
  schedule:
    - cron: '0 9 * * 1'  # Monday at 9 AM

jobs:
  validate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Validate markdown
        run: |
          if [ ! -f "README.md" ]; then
            echo "README.md missing!"
            exit 1
          fi
          echo "✓ README.md is valid"
```

### Example 3: Manual Trigger

```yaml
name: Manual Profile Update
on:
  workflow_dispatch:

jobs:
  update:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Regenerate README
        run: |
          # Regenerate README with latest data
          echo "Profile regenerated"
```

## Next Steps

1. **Test the workflow:**
   - Trigger manually first
   - Verify changes look correct

2. **Customize for your needs:**
   - Edit `.github/workflows/profile-update.yml`
   - Add custom validation steps

3. **Monitor runs:**
   - Go to Actions tab
   - Review workflow run logs

4. **Expand automation:**
   - Create additional workflows
   - Integrate with other tools

## Resources

- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Workflow Syntax Reference](https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions)
- [Cron Expressions](https://crontab.guru/)
- [GitHub API Reference](https://docs.github.com/en/rest)

---

*Last Updated: 2026-05-29*
