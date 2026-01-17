# Mobility Force Allocation Tool

Interactive Gantt chart for AMC A38 force allocation planning.

## Quick Start - GitHub Pages Deployment

### 1. Create Your Repository

1. Go to [github.com](https://github.com) and create a new repository
2. Name it something like `mobility-allocation` (or whatever you want)
3. Make it **Public** (required for free GitHub Pages)
4. Don't initialize with README (we'll upload our files)

### 2. Upload These Files

Upload the following files to your repository:
```
your-repo/
├── index.html          ← Main app (edit version)
├── mobility-data.json  ← Your data file
└── README.md           ← This file (optional)
```

**To upload:**
1. Click "uploading an existing file" on your new repo
2. Drag and drop the files
3. Click "Commit changes"

### 3. Enable GitHub Pages

1. Go to your repo's **Settings** tab
2. Click **Pages** in the left sidebar
3. Under "Source", select **Deploy from a branch**
4. Select **main** branch and **/ (root)** folder
5. Click **Save**

### 4. Access Your Site

After a minute or two, your site will be live at:
```
https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/
```

Example: `https://swap-amc.github.io/mobility-allocation/`

---

## How Data Persistence Works

### Automatic (localStorage)
- All changes auto-save to your browser's localStorage
- Data persists between sessions **on the same computer/browser**
- Different computers = different data (localStorage is local)

### Manual (JSON export/import)
1. Make your changes
2. Click **📤** (Export) to download `mobility-data-YYYY-MM-DD.json`
3. Rename it to `mobility-data.json`
4. Commit to your repo (replaces the old data file)
5. Anyone viewing the site will now load the updated data

### Workflow for Team Updates

```
You (admin):
1. Open the site
2. Make changes
3. Export JSON
4. Commit to GitHub

Others (viewers):
1. Open the site
2. See your latest changes (auto-loads from JSON)
```

---

## Creating a View-Only Version

To make a read-only viewer version:

1. Copy `index.html` to `viewer.html`
2. Edit `viewer.html` and change line 15:
   ```javascript
   const READ_ONLY = true;  // Changed from false
   ```
3. Commit both files
4. Share `https://username.github.io/repo/viewer.html` for view-only access

---

## File Structure

### mobility-data.json

```json
{
  "units": [
    { "id": "KC-A-1", "component": "A", "mds": "KC-135", ... },
    ...
  ],
  "wingInventory": {
    "92 ARW": { "tai": 28, "bai": 4, "depot": 2, "mds": "KC-135" },
    ...
  },
  "commitments": [
    { "id": "c1", "unitId": "KC-A-1", "startDate": "2027-01-01", ... },
    ...
  ],
  "tdgEntries": [
    { "id": "tdg-1", "ccmd": "CENTCOM", "period": "27.1a", ... },
    ...
  ]
}
```

---

## Troubleshooting

**Site not loading?**
- Wait 2-3 minutes after enabling Pages
- Check Settings > Pages for the URL
- Make sure repo is Public

**Data not updating?**
- Hard refresh the page (Ctrl+Shift+R)
- Check that `mobility-data.json` is in the root folder
- Check browser console (F12) for errors

**Changes not saving?**
- localStorage only works on the same browser/computer
- Use Export/Import to share data across devices

---

## Future Enhancements

For SharePoint/Teams integration or automatic sync, we'll need:
- Microsoft Graph API integration
- Azure AD app registration
- Excel file backend

(To be developed in a later phase)
