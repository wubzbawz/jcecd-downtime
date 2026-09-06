JCECD SHARED EMERGENCY CALL ENTRY v1

WHAT IT DOES
Call Processing creates one shared call. Law and/or Fire Dispatch sees it on another
device, opens it, and adds unit notifications and updates. Narrative updates carry
server timestamps and the operator name. The same 390,336-address Fire/JCSO lookup
is included.

YOU NEED TWO FREE SERVICES
1. GitHub Pages = hosts the website.
2. Supabase = stores/synchronizes the live calls.

SUPABASE SETUP
1. Create a free Supabase project.
2. Open SQL Editor -> New query.
3. Open supabase_setup.sql from this package, copy it into the query, and Run it.
4. Go to Authentication -> Users and create at least 3 email/password users:
   - CP test user
   - Law test user
   - Fire test user
5. In Project Settings/API, copy the Project URL and PUBLISHABLE key (or legacy anon key).
6. Open config.js in Notepad and replace BOTH PASTE_ values.
7. Save config.js.
8. NEVER use the service_role key in config.js.

GITHUB UPLOAD
Upload these to the ROOT of the GitHub repository:
index.html
config.js
data.tsv
calltypes.json
manifest.webmanifest
sw.js
icon-192.png
icon-512.png

You do not need to upload:
README_SETUP.txt
supabase_setup.sql

TEST WITH TWO DEVICES
DEVICE 1:
- Sign in as CP.
- Select Call Processing and operator CP01.
- Search a known address.
- Select Law and/or Fire/EMS.
- Pick call type(s).
- Enter narrative.
- SEND TO DISPATCH.

DEVICE 2:
- Sign in as Law Dispatch or Fire Dispatch.
- Open Active Calls.
- The call should appear automatically.
- Open it.
- Add: 435 ENR / E1 NOTIFIED / M12 ONS / etc.
- The update should appear on the other device.

IMPORTANT LIMITATION
Shared synchronization requires internet access to Supabase. If the center loses
internet completely, use the locally hosted LAN Backup CAD instead.

SECURITY
GitHub contains only the application/address/call-type files. Caller names, callback
numbers and narratives are stored in Supabase, not GitHub. This test uses authenticated
accounts and Row Level Security. Have JCECD IT/security review before operational use.
