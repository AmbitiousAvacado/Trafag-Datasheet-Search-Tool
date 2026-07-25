# Trafag Datasheet Search Tool
A small Windows app that does three things:

- **Search & open** – find a datasheet already on the PC and open it on the monitor your mouse is on. Two modes: **Search Title** (matches the file name) and **Search by Keyword** (finds words *inside* the PDF text).
- **Download** – type a Trafag document code (the "H" number, e.g. `H72303`), pick a language, and the datasheet downloads straight into the local datasheets folder.
- **Update** – check every datasheet in the folder for a newer revision and pull it automatically.

Keyword search reads the text layer of each PDF, so scanned/image-only datasheets (no text) won't match on content — only on their title.

This is the Windows version of the Mac "Trafag Datasheet Finder."

## How (datasheet) updates work

Trafag revisions are the one or two letters right after the H number: `H72304ac` is newer than `H72304ab` (letters run `a, b … z, aa, ab …`, so a longer suffix is always newer). When the tool finds a newer revision online it downloads it and moves the superseded file to the **Recycle Bin** (recoverable, not permanently deleted).

The check runs **automatically once a week**, on the first **Monday-morning logon**. It's installed as a logon shortcut the first time the app runs; each logon the program checks the date and does nothing unless it's the weekly slot (so multiple logins on Monday won't re-run it, and a missed Monday is caught the following week). If anything was updated, a short summary pops up. You can also run it any time from the **Updates** tab, and turn the weekly check on/off there.

---

## For Users

1. Double-click **`TrafagDatasheets.exe`**.
2. A **`Datasheets`** folder is created automatically next to the `.exe` (this is where PDFs are stored). To use a different folder, click **Change…** at the top. The program will make an internal record of this new location and the change will be persist moving foward even after the program is closed.

**To open a datasheet you already have:** go to **Find & open**, type any part of the name/number, double-click a result (or click *Open on this monitor*). The program does a quick search to find your cursor, note which monitor it is present on, and moves the PDF to that monitor.

**To download a new datasheet:** go to **Download**, type the document code (the **H** number, e.g. `H72303`), choose a language, click **Download datasheet**. It saves into the Datasheets folder and offers to open it.

> Where do I find the document code? It's the "H" number printed on the datasheet and at the start of each PDF's filename (e.g. `H72303am_EN_8252_NAT_...pdf`). Article numbers like `8252` are not accepted by the download lookup — use the H number.
