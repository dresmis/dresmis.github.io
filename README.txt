MYWEB PROJECT - WEBSITE CONTROL GUIDE
====================================

LOCATION:
C:\Users\esmis\Documents\MYWEB


=================================================
PROJECT INVENTORY
=================================================

CORE FILES
----------
index.html              - Main homepage
style.css               - Global styling for all pages
blank_page.html         - Template for all pages

CONTENT PAGES
-------------
todo-sobre-mi.html      - About page
contact.html            - Contact page
hobbies.html            - Hobbies & interests
ciee.html               - Study Abroad
dissertation-research.html - Dissertation

CONFIG / TOOLS
--------------
.vscode/tasks.json      - VS Code tasks (link checker, server)


=================================================
LOCAL SERVER (VIEW WEBSITE)
=================================================

1. Open VS Code
2. Open MYWEB folder
3. Open Terminal

4. Run:
   http-server -p 8080

5. Open browser:
   http://localhost:8080

6. Stop server:
   CTRL + C


=================================================
LINK CHECKING (VERY IMPORTANT)
=================================================

1. Make sure server is running

2. Run:
   blc "http://localhost:8080/index.html" --recursive --filter-level=error

3. Wait (can take time)

4. Fix:
   - 404 = broken internal link
   - 403 = blocked external site
   - 3xx = redirect (update if needed)

5. Repeat until clean


=================================================
STANDARD WORKFLOW
=================================================

--- EDITING EXISTING PAGE ---

1. Open file in VS Code
2. Make changes
3. Save file
4. Refresh browser
5. Verify layout and links


--- CREATING NEW PAGE ---

1. Copy blank_page.html
2. Rename file (example: newpage.html)
3. Update:
   - <title>
   - <h2> REPLACE THIS TEXT
   - Page content
4. Add link to navigation menu
5. Test in browser


--- UPDATING NAVIGATION ---

1. Edit nav section in ALL pages
2. Keep links consistent:
   Home | About | Contact | Hobbies | Study Abroad | Dissertation
3. Save all files
4. Refresh browser


--- STYLING CHANGES ---

1. Edit style.css
2. Save file
3. Refresh browser
4. Check in multiple browsers (Firefox + Chrome)


--- FIXING LINKS ---

1. Run link checker (blc)
2. Identify broken links
3. Update or remove links
4. Re-run checker


=================================================
COMMON PROBLEMS + FIXES
=================================================

PORT 8080 IN USE:
- Error: EADDRINUSE
- Fix: Close server or reboot

COMMAND NOT FOUND:
- Restart VS Code
- Check Node installation

LINK CHECKER TAKES LONG:
- Normal
- Be patient


=================================================
DESIGN RULES (KEEP IT CLEAN)
=================================================

- Use blank_page.html for ALL pages
- Keep navigation identical everywhere
- Keep layout simple and readable
- Prefer left-aligned text for readability
- Keep footer consistent


=================================================
PRE-PUBLISH CHECKLIST (GITHUB)
=================================================

[ ] All pages load
[ ] Navigation works on all pages
[ ] No broken internal links
[ ] External links updated (https)
[ ] Layout consistent across pages
[ ] Test in Firefox and Chrome


=================================================
NOTES
=================================================

- Always test locally before publishing
- Keep things simple (less is better)
- Fix structure first, design second