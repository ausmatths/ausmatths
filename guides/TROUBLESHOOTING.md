# Troubleshooting Guide

Common issues and solutions when transforming your GitHub profile.

## 📋 Quick Troubleshooting Table

| Problem | Likely Cause | Solution |
|---------|-------------|----------|
| Claude is not opening my GitHub repo | Not on github.com page | Refresh page, make sure you're on github.com/[username], then click Claude extension |
| Profile repo does not exist | Repository not created yet | Go to Step 2 and create the repository. Name MUST match your username exactly |
| Badges are not showing | Badges need time to load | Refresh the page. Shields.io badges take 5-10 seconds to load |
| GitHub stats card shows wrong username | Typo in the prompt | Tell Claude: "Fix all usernames in stats cards to [your-username]" |
| Claude stopped mid-way | Connection issue or pause | Type 'continue' and press Enter. Claude will resume |
| README looks broken or misaligned | Markdown formatting error | Tell Claude: "The README has formatting issues. Please fix the markdown and save again" |
| Want different theme/colors | Theme not customized | Tell Claude: "Change all themes to [dark/radical/tokyonight/merko/darkhub]" |
| Social media badges missing | Not included in original prompt | Edit the prompt to add YouTube, Medium, Instagram, or LinkedIn sections |
| Profile views counter not showing | Badge URL syntax error | Clear cache and refresh. If persists, tell Claude to regenerate the visitor counter |
| Repository says "404 Not Found" | Repo name doesn't match username | Repository name MUST be exactly your GitHub username (case-sensitive) |

---

## 🔴 Detailed Problem Solutions

### 1. Claude Extension Not Opening / Not Working

**Symptoms:**
- Claude icon doesn't appear in toolbar
- Clicking Claude icon does nothing
- Sidebar fails to load

**Solutions:**

a) **Extension not installed**
   - Go to [Chrome Web Store](https://chromewebstore.google.com)
   - Search "Claude"
   - Install the official Anthropic extension
   - Sign in with your Claude account

b) **Extension needs to be pinned**
   - Click the puzzle icon in Chrome toolbar (top right)
   - Find "Claude" in the list
   - Click the pin icon next to it
   - Try again

c) **Extension needs re-authentication**
   - Click the Claude icon
   - If you see "Sign in" button, click it
   - Sign in with your Claude account
   - Try again

d) **Restart Chrome entirely**
   - Close all Chrome windows
   - Reopen Chrome
   - Try again

---

### 2. GitHub Profile Repository Issues

**Symptom: "404 Not Found" when visiting github.com/[username]/[username]**

**Solution:**
The repository doesn't exist. Create it:

1. Go to [GitHub](https://github.com)
2. Click '+' button in top right → 'New repository'
3. **Repository name:** Must be EXACTLY your username (case-sensitive)
   - If your username is `JayanthBabu3`, repo must be `JayanthBabu3` (not jayanthbabu3)
4. Keep it **Public**
5. Check "Add a README file"
6. Click "Create repository"

GitHub will display: *"This is a special repository. Its README.md will appear on your profile."*

**Why the exact name matters:**
GitHub's special feature only works when the repository name matches your username exactly. Even one character difference breaks this.

---

### 3. Badges Not Showing

**Symptoms:**
- Image placeholder boxes instead of badges
- "Failed to load image" errors
- Shields.io badges don't render

**Solutions:**

a) **Wait and refresh** (Most common fix)
   - Refresh the page: `Ctrl+R` or `Cmd+R`
   - Wait 10 seconds
   - Refresh again
   - Shields.io takes time to generate badges on first load

b) **Clear browser cache**
   - Press `Ctrl+Shift+Delete` (Windows) or `Cmd+Shift+Delete` (Mac)
   - Select "Cookies and other site data"
   - Select "All time"
   - Click "Clear data"
   - Go back to your profile
   - Refresh

c) **Badge URLs are broken**
   - Tell Claude: "Please regenerate all the tech stack badges and make sure all shields.io URLs are valid"
   - Claude will fix the URLs

d) **Internet connection issue**
   - Check your internet connection
   - Try on a different network if possible

---

### 4. GitHub Stats Cards Not Working

**Symptoms:**
- Stats card shows wrong username
- Stats card shows "Failed to load"
- "Stars", "Commits", "PRs" not displaying

**Solutions:**

a) **Wrong username in URL**
   - Tell Claude: "Fix all GitHub usernames in the stats cards to [your-actual-username]"
   - Example: "Fix all GitHub usernames in the stats cards to ausmatths"

b) **Stats service temporarily down**
   - Wait 15-30 minutes
   - Refresh your profile
   - The service may recover
   - If persists, tell Claude to switch to alternative stats service

c) **Username has special characters**
   - Some GitHub usernames have hyphens or underscores
   - Tell Claude: "My GitHub username is [your-exact-username]. Make sure this is used in all stat card URLs"

---

### 5. Claude Stops or Freezes During Editing

**Symptoms:**
- Claude starts editing but stops midway
- "Waiting for response" message persists
- Claude asks "Should I continue?" but doesn't auto-continue

**Solutions:**

a) **Tell Claude to continue**
   - Type `continue` in the chat
   - Press Enter
   - Claude will resume from where it left off

b) **Send a simpler follow-up**
   - Type: "Finish editing the README now"
   - Or: "Save the changes"
   - Claude will complete the remaining steps

c) **If it still doesn't work**
   - Take a screenshot of what's been done so far
   - Close Claude extension
   - Reopen it
   - Tell Claude: "I was editing my GitHub profile README. Here's what we completed: [describe]. Please continue from where we left off and complete the full README with all sections"

---

### 6. README Formatting Looks Broken

**Symptoms:**
- Text is misaligned
- Sections overlap
- Emojis display strangely
- Spacing is wrong

**Solutions:**

a) **Quick fix - Tell Claude to reformat**
   - Tell Claude: "The README has formatting issues. Please regenerate the entire README with proper markdown formatting and spacing"
   - Claude will reformat everything

b) **Specific formatting issue**
   - Tell Claude the specific problem
   - Example: "The tech stack section is misaligned. Fix the table formatting"
   - Example: "The social links are not centered. Use proper alignment"

c) **Full re-generation**
   - Tell Claude: "Delete all the current content and create a completely new professional README with all sections properly formatted"

---

### 7. Want to Change Theme/Colors

**Symptoms:**
- Current theme doesn't match your style
- Want a different color scheme
- Prefer dark/light mode

**Solutions:**

**Available themes:**
- `tokyonight` - Dark with purple/blue (Default)
- `radical` - Vibrant neon colors
- `merko` - Green theme
- `onedark` - Dark with blue
- `darkhub` - GitHub dark theme

**How to change:**
- Tell Claude: "Change all themes to [theme-name]"
- Example: "Change all themes to radical"
- Claude will update all stat cards, trophies, and badges to use the new theme

---

### 8. Social Media Links Not Working

**Symptoms:**
- YouTube/Instagram/LinkedIn badges not clickable
- Links go to wrong URLs
- Missing social media section

**Solutions:**

a) **Links not clickable**
   - Tell Claude: "Make all social media badges clickable links. Add YouTube, Medium, Instagram, and LinkedIn links"

b) **Wrong URL in social link**
   - Tell Claude: "Fix the [Social Media] link to [correct-url]"
   - Example: "Fix the YouTube link to youtube.com/@ausmatths"

c) **Add missing social link**
   - Tell Claude: "Add my [social-media] link to the profile. My [social-media] is [your-url]"
   - Example: "Add my YouTube link to the profile. My YouTube is youtube.com/@ausmatths"

d) **Remove social link**
   - Tell Claude: "Remove the [social-media] link from my profile"
   - Example: "Remove the Instagram link from my profile"

---

### 9. Visitor Counter Not Appearing

**Symptoms:**
- Profile views badge missing
- Komarev counter not loading
- No "Profile views" text

**Solutions:**

a) **Wait for badge to load**
   - Visitor counter takes time to initialize
   - Refresh page after 30 seconds
   - Try in incognito mode

b) **Regenerate the badge**
   - Tell Claude: "The visitor counter badge is not showing. Please regenerate it using komarev service with the correct URL"

c) **Manual check**
   - Visit your profile in a new incognito window
   - This may trigger the counter
   - Go back and refresh your normal profile view

---

### 10. Claude Asks Too Many Questions

**Symptoms:**
- Claude asks "Would you like...?" or "Should I...?" repeatedly
- Claude doesn't just execute
- Seems like it's not following the "no questions" instruction

**Solutions:**

a) **Re-paste the full prompt**
   - Copy the entire prompt again
   - Make sure you include "Do NOT ask me any questions. Just execute everything."
   - Paste it fresh
   - Press Enter

b) **Be more directive**
   - Instead of asking Claude to help, tell it exactly what to do
   - Example: "Transform my GitHub profile README with all sections" 
   - Not: "Can you help me transform my GitHub profile?"

c) **Use the official prompt template**
   - Use the exact prompt from [prompt-template.md](./prompt-template.md)
   - It's designed to prevent Claude from asking questions

---

### 11. Multiple Issues at Once

**If you have several issues:**

1. **Tell Claude everything at once**
   ```
   Please fix these issues in my README:
   1. Change the theme to radical
   2. Fix the GitHub stats cards username to [your-username]
   3. Regenerate the tech stack badges
   4. Add my YouTube link: [your-url]
   5. Save the changes
   ```

2. **Or start fresh**
   - Tell Claude: "Delete everything and create a brand new professional README with all standard sections"
   - Then make specific customizations after

---

## ✅ Prevention Tips

### Do This to Avoid Most Issues:

1. ✅ **Use a text editor first**
   - Copy the prompt into Notepad/Google Docs
   - Fill in all [BRACKETS] carefully
   - Check spelling of usernames
   - Then paste into Claude

2. ✅ **Be on the right page**
   - Always start on your GitHub profile page: `github.com/[your-username]`
   - Then click Claude extension
   - This ensures Claude knows which profile to edit

3. ✅ **Use exact GitHub username**
   - Don't guess your username
   - Go to github.com to confirm it
   - Copy-paste it into the prompt

4. ✅ **Verify social links**
   - Copy-paste your YouTube, LinkedIn, etc. URLs directly
   - Don't type them manually

5. ✅ **Test one section at a time (if you want)**
   - You don't have to do everything at once
   - You can tell Claude: "Add just the tech stack section" first
   - Then add other sections later

---

## 🆘 Still Having Issues?

If you've tried all solutions above:

1. **Screenshot the error**
   - Take a screenshot of what you see
   - Include the Claude chat and the GitHub page

2. **Check the badges manually**
   - Visit the badge URLs directly in a new tab
   - See if they load
   - Example: `https://shields.io/badge/python-blue`

3. **Try incognito mode**
   - Open a fresh Chrome incognito window
   - Try the transformation again
   - This eliminates cache/extension conflicts

4. **Clear everything and start fresh**
   - Close Claude completely
   - Close all GitHub tabs
   - Restart Chrome
   - Go to your profile
   - Open Claude again
   - Paste a fresh prompt

---

## 📞 Getting Help

If none of these solutions work:

1. **Check Claude Help:** Visit support.anthropic.com
2. **Check GitHub Help:** Visit docs.github.com
3. **Verify your setup:**
   - Is Claude Chrome Extension installed?
   - Are you signed in to Claude?
   - Is your GitHub profile public?
   - Does your profile repository exist?

---

*Last Updated: 2026-05-29*
