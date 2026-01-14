# How to Add Resources to the Website

This guide explains how to add presentations, PDFs, and other files to share with the community.

## Step 1: Add Your File to the Resources Folder

1. Place your file (PDF, PowerPoint, images, etc.) in the `resources/` folder
2. Use simple filenames without spaces (use hyphens instead)
   - Good: `intro-to-ai-coding.pdf`
   - Avoid: `Intro to AI Coding.pdf`

## Step 2: Update the Website to Display the Resource

Open `index.html` and find the Resources section (search for `resources-grid`).

### To add your first resource:

1. Find and **delete** this line:
   ```html
   <p class="no-resources">Resources coming soon! Check back after our next meetup.</p>
   ```

2. Add a resource card like this example:
   ```html
   <a href="resources/your-file-name.pdf" class="resource-card" target="_blank">
       <div class="resource-icon">
           <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
               <path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"></path>
               <polyline points="14 2 14 8 20 8"></polyline>
               <line x1="16" y1="13" x2="8" y2="13"></line>
               <line x1="16" y1="17" x2="8" y2="17"></line>
               <polyline points="10 9 9 9 8 9"></polyline>
           </svg>
       </div>
       <div class="resource-info">
           <h4>Your Resource Title</h4>
           <span class="resource-type">PDF</span>
       </div>
   </a>
   ```

### To add more resources:

Simply add another resource card inside the `resources-grid` div:

```html
<div class="resources-grid" id="resources-list">
    <!-- First resource -->
    <a href="resources/first-file.pdf" class="resource-card" target="_blank">
        ...
    </a>

    <!-- Second resource -->
    <a href="resources/second-file.pptx" class="resource-card" target="_blank">
        ...
    </a>

    <!-- Add more as needed -->
</div>
```

## Step 3: Commit and Push to GitHub

```bash
git add .
git commit -m "Add new resource: [resource name]"
git push
```

The website will automatically update within a few minutes.

---

## Quick Reference: Resource Card Template

Copy and paste this template, then update the highlighted parts:

```html
<a href="resources/FILE-NAME-HERE.pdf" class="resource-card" target="_blank">
    <div class="resource-icon">
        <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
            <path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"></path>
            <polyline points="14 2 14 8 20 8"></polyline>
            <line x1="16" y1="13" x2="8" y2="13"></line>
            <line x1="16" y1="17" x2="8" y2="17"></line>
            <polyline points="10 9 9 9 8 9"></polyline>
        </svg>
    </div>
    <div class="resource-info">
        <h4>TITLE HERE</h4>
        <span class="resource-type">PDF</span>
    </div>
</a>
```

**Change:**
- `FILE-NAME-HERE.pdf` - the actual filename in the resources folder
- `TITLE HERE` - a friendly name to display
- `PDF` - the file type (PDF, PPTX, ZIP, etc.)

---

## Deploying to GitHub Pages

1. Create a new repository on GitHub named `stuart-vibe-coding-community` (or any name you prefer)

2. Initialize git and push:
   ```bash
   git init
   git add .
   git commit -m "Initial commit: Stuart Vibe Coding Community website"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/stuart-vibe-coding-community.git
   git push -u origin main
   ```

3. Enable GitHub Pages:
   - Go to your repository on GitHub
   - Click **Settings** > **Pages** (in the left sidebar)
   - Under "Source", select **Deploy from a branch**
   - Select **main** branch and **/ (root)** folder
   - Click **Save**

4. Your site will be live at: `https://YOUR-USERNAME.github.io/stuart-vibe-coding-community/`

---

## File Size Limits

GitHub Pages has a soft limit of 100MB per file. For larger presentations:
- Compress PDFs using tools like [SmallPDF](https://smallpdf.com/)
- Convert PowerPoints to PDF for smaller file sizes
- Consider hosting large files on Google Drive and linking to them instead
