# DRESMIS.GITHUB.IO PROJECT - WEBSITE CONTROL GUIDE

## LOCATION
- **Linux:** `~/dresmis.github.io`  
- **Windows:** `C:\Users\esmis\Documents\dresmis.github.io`

---

## PROJECT INVENTORY

**Core Files**  
- `index.html` – Homepage  
- `style.css` – Global styling  
- `blank_page.html` – Template for all pages  

**Content Pages**  
- `todo-sobre-mi.html` – About  
- `contact.html` – Contact  
- `hobbies.html` – Hobbies & interests  
- `ciee.html` – Study Abroad  
- `dissertation-research.html` – Dissertation  

**Config / Tools**  
- `.vscode/tasks.json` – VS Code tasks (link checker, server)

---

## LOCAL SERVER (VIEW WEBSITE)

### Linux
```bash
cd ~/dresmis.github.io
http-server -p 8080
```

### Windows
1. Open VS Code  
2. Open `dresmis.github.io` folder  
3. Open Terminal / Command Prompt  

```bash
http-server -p 8080
```

- Open browser: `http://localhost:8080`  
- Stop server: `CTRL + C`

---

## LINK CHECKING

```bash
blc "http://localhost:8080/index.html" --recursive --filter-level=error
```

- 404 = broken internal link  
- 403 = blocked external site  
- 3xx = redirect (update if needed)  
- Repeat until all links clean

---

## STANDARD WORKFLOW

### Editing Existing Page
1. Open file in VS Code  
2. Make changes & save  
3. Refresh browser, verify layout & links  

### Creating New Page
1. Copy `blank_page.html` → `newpage.html`  
2. Update `<title>`, `<h2>`, page content  
3. Add link to navigation menu  
4. Test in browser  

### Updating Navigation
- Edit nav section in **all pages**  
- Keep links consistent: `Home | About | Contact | Hobbies | Study Abroad | Dissertation`  

### Styling Changes
- Edit `style.css`  
- Save and refresh  
- Check in Firefox & Chrome

### Fixing Links
- Run link checker (`blc`)  
- Update broken links  
- Re-run checker

---

## GIT SYNC BETWEEN RIGS

### Initial Setup (if folder not cloned yet)
```bash
cd ~/dresmis.github.io
git init
git remote add origin https://github.com/dresmis/dresmis.github.io.git 2>/dev/null
git fetch origin
git reset --hard origin/main
```

### Regular Update
```bash
cd ~/dresmis.github.io
git pull origin main
```

- Use the **Windows path** when working on the HP rig (`C:\Users\esmis\Documents\dresmis.github.io`)  
- **Backup local edits first** to avoid overwriting  

---

## COMMON PROBLEMS + FIXES

- **PORT 8080 IN USE:** Close server / reboot  
- **COMMAND NOT FOUND:** Restart VS Code, check Node.js installation  
- **Link checker slow:** Normal, be patient  

---

## DESIGN RULES

- Use `blank_page.html` as base  
- Keep navigation identical everywhere  
- Layout simple & readable  
- Footer consistent  

---

## PRE-PUBLISH CHECKLIST

- [ ] All pages load  
- [ ] Navigation works  
- [ ] No broken internal links  
- [ ] External links updated (https)  
- [ ] Layout consistent  
- [ ] Test in Firefox & Chrome  

---

## HTML CHEAT SHEET (Quick Reference)

| Tag | Purpose |
|-----|---------|
| `<html>` | Root element |
| `<head>` | Metadata, scripts, styles |
| `<title>` | Page title in browser |
| `<body>` | Page content |
| `<h1>…<h6>` | Headings |
| `<p>` | Paragraph |
| `<a href="URL">` | Link |
| `<img src="URL" alt="desc">` | Image |
| `<ul>` / `<ol>` | Lists |
| `<li>` | List item |
| `<div>` | Block container |
| `<span>` | Inline container |
| `<strong>` | Bold / important text |
| `<em>` | Italic / emphasis |
| `<br>` | Line break |
| `<link rel="stylesheet" href="style.css">` | Include CSS |

---

### NOTES
- Test locally before publishing  
- Keep things simple  
- Fix structure before design  
- Always sync GitHub before switching rigs