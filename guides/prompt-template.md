# GitHub Profile Transformation Prompt Template

Copy this entire prompt and paste it into Claude Chrome Extension after filling in your details with [YOUR BRACKETS].

---

## COPY THIS ENTIRE PROMPT (Part 1 of 2)

I want you to transform my GitHub profile README. Do NOT ask me any questions. Just execute everything.

### MY DETAILS:
- **Name:** [YOUR NAME]
- **Role:** [YOUR ROLE]
- **Experience:** [X] years
- **Tech Stack:** [LIST YOUR TECHNOLOGIES]
- **YouTube:** [YOUR YOUTUBE URL] - [X] subscribers
- **Medium:** [YOUR MEDIUM URL] - [X] followers
- **Instagram:** [YOUR INSTAGRAM URL] - [X] followers
- **LinkedIn:** [YOUR LINKEDIN URL]
- **Portfolio:** [YOUR WEBSITE URL]

### INSTRUCTIONS - DO ALL OF THIS AUTOMATICALLY:

#### 1. Navigate to my GitHub profile README
- Go to my GitHub profile repository (github.com/[username]/[username])
- Open the README.md file
- Click Edit (pencil icon)

#### 2. Delete ALL existing content
Replace everything with a new professional README.

#### 3. Create and paste this complete README structure:

### SECTION A: ANIMATED HEADER
- Add a wave GIF greeting: `<img src="https://raw.githubusercontent.com/ABSphreak/ABSphreak/master/gifs/Hi.gif" width="30px">`
- Add animated typing effect using readme-typing-svg showing my role and a tagline
- Include a professional greeting line

### SECTION B: ABOUT ME
- Write a short confident intro about who I am
- Mention my technical specialization
- Mention my content creation presence if applicable (YouTube, Medium, Instagram)
- Add 3-4 fun bullet points about my personality, interests, or philosophy
- Use relevant emojis throughout

### SECTION C: TECH STACK
- Add shields.io badges for ALL my technologies
- Use colored badges with logos
- Organize by categories:
  - **Languages:** Programming languages I use
  - **Frontend:** Frontend frameworks and tools
  - **Backend:** Backend frameworks and services
  - **Cloud & DevOps:** Cloud platforms and DevOps tools
  - **Databases:** Database technologies
  - **Tools & Others:** Other tools and platforms

### SECTION D: SOCIAL MEDIA LINKS & PORTFOLIO
- YouTube badge with subscriber count (if provided)
- Medium badge with link (if provided)
- Instagram badge with follower count (if provided)
- LinkedIn badge with professional link
- Portfolio/Website badge (if provided)
- All badges must be clickable links

### SECTION E: GITHUB STATS
Use the tokyonight theme for all stats:
- **GitHub Stats Card** from anuraghazra/github-readme-stats
  - URL format: `https://github-readme-stats.vercel.app/api?username=[USERNAME]&show_icons=true&theme=tokyonight&hide_border=true`
- **GitHub Streak Stats** from github-readme-streak-stats
  - URL format: `https://streak-stats.demolab.com/?user=[USERNAME]&theme=tokyonight&hide_border=true`
- **Top Languages Card**
  - URL format: `https://github-readme-stats.vercel.app/api/top-langs/?username=[USERNAME]&layout=compact&theme=tokyonight&hide_border=true`

### SECTION F: GITHUB TROPHIES
- Use github-profile-trophy from ryo-ma/github-profile-trophy
- Theme: tokyonight
- URL format: `https://github-profile-trophy.vercel.app/?username=[USERNAME]&theme=tokyonight&no-frame=true&no-bg=true&margin-w=8`

### SECTION G: VISITOR COUNTER
- Add komarev profile views counter badge at the top
- URL format: `https://komarev.com/ghpvc/?username=[USERNAME]&label=Profile%20views&color=0e75b6&style=for-the-badge`

### SECTION H: FOOTER
- Add a "Let's Connect" section with all social links
- Add a professional closing line encouraging connection

---

## PROMPT CONTINUED (Part 2 of 2)

### 4. After pasting all content:
- Click **'Commit changes'** to save automatically
- Wait for the confirmation

### FORMATTING REQUIREMENTS:
- Use proper markdown formatting
- Add section headers with emojis
- Use horizontal dividers (---) between major sections
- Center alignment where appropriate using `<p align="center">`
- Use tables for tech stack organization
- Make sure all URLs are correctly formatted with my actual username

### RULES:
- ✅ Do NOT ask any questions. Just do it.
- ✅ Do NOT stop in the middle. Complete everything.
- ✅ Use my actual GitHub username in all URLs.
- ✅ Make sure all badge URLs are correct.
- ✅ Replace all [BRACKETS] with my actual values.
- ✅ Make it modern, clean, and professional.
- ✅ Use spaces and proper formatting for readability.

### VERIFICATION:
- All badge services (shields.io, komarev, github-readme-stats, etc.) should load without errors
- Links should be clickable
- Images should display properly
- The README should be properly formatted markdown

## <<< END OF PROMPT

---

## How to Use This Template

1. **Copy this entire prompt** (both Part 1 and Part 2)
2. **Fill in all [BRACKETS]** with your actual information:
   - [YOUR NAME] → Your actual name
   - [YOUR ROLE] → Your job title/specialization
   - [X] years → Number of years of experience
   - [LIST YOUR TECHNOLOGIES] → All your tech skills
   - [YOUR YOUTUBE URL] → Your YouTube channel URL
   - [X] subscribers → Your subscriber count
   - And so on...
3. **Use a text editor first** — Copy into Notepad/Google Docs, fill everything in, then copy the completed version
4. **Open Claude Chrome Extension** on your GitHub profile page
5. **Paste the complete prompt** into the chat
6. **Press Enter** and watch Claude transform your profile

## Optional Customizations

If you want to customize the prompt further:

- **Change themes:** Replace `theme=tokyonight` with `theme=radical`, `theme=merko`, `theme=onedark`, or `theme=darkhub`
- **Remove sections:** Delete any section header and content if you don't want that section
- **Reorder sections:** Move sections around as you prefer
- **Adjust styling:** Tell Claude "Make it more minimalist" or "Add more visual elements"

## Tips for Best Results

✨ **Use a template first:** Copy this into a text editor, customize carefully, then paste

✨ **Double-check your URLs:** Make sure your YouTube, LinkedIn, and other URLs are correct

✨ **Provide accurate numbers:** Subscriber counts and follower numbers should be current

✨ **Be specific about tech:** The more specific your tech stack, the better the badges Claude generates

✨ **Include your actual username:** Claude needs your GitHub username for all stat cards

---

*For detailed guidance, see [GUIDE.md](./GUIDE.md)*
