JCECD DOWNTIME RESPONSE LOOKUP - PHONE PWA

CONTENTS
- index.html: complete address/fire/JCSO beat lookup
- sw.js: offline cache/service worker
- manifest.webmanifest: installable app metadata
- icon-192.png / icon-512.png: app icons

IMPORTANT
A PWA must be served from HTTPS (or localhost for testing). It will NOT install correctly by opening index.html directly from Files, email, OneDrive preview, or a ZIP.

DEPLOY
1. Upload ALL files in this folder, unchanged, to the same HTTPS web folder.
2. Open index.html through that HTTPS address on the phone.
3. Wait for the page to fully load once.
4. iPhone/iPad: Safari > Share > Add to Home Screen.
5. Android: Chrome > menu > Install app / Add to Home screen.
6. Close the browser.
7. Turn on Airplane Mode and open the JCECD Downtime icon.
8. Search several known addresses before approving for operational use.

UPDATES
When the lookup is rebuilt, replace all files and change the CACHE name in sw.js to a new version so devices receive the new copy.
