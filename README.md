# Bus Gardian LogBook

A simple, phone-friendly log book for school bus drivers. Record each run
(school, route, bus, times, kids, notes) in seconds, review your week, and
export your logs. Built by Michelle Minor.

It is a single file, `index.html`. There is nothing to install and no server.
Open it in a browser and it works.

## Features

- **Today tab** - start a new log: date, school, route number, tier (0-5),
  bus number, start and end time, weather, road, shift, traffic, delay,
  odometer, number of kids, notes and issues.
- **Spare** checkbox with a spare bus number.
- **Route Sub/Breakdown** checkbox for when you are covering another route
  or a bus breakdown.
- **Start Route Now** and **Now** buttons to stamp the current time.
- **Week tab** - see your saved logs and totals.
- **Schools tab** - manage your list of schools.
- **Voice tab** - dictate or paste a note and fill the form from it.
- **Settings tab** - Google Sheets webhook, app info, and a protected
  "Clear and Reset" button.
- **Export tab** - download your logs as a CSV file.

## How to use it

### Log a run

1. Open the **Today** tab.
2. Check the date, then pick the **School**.
3. Enter the **Route Number** and **Tier**. The **Bus Number** starts at 4114
   and can be edited.
4. Tick **Spare** (and enter the spare bus number) or **Route Sub/Breakdown**
   if they apply.
5. Tap **Start Route Now**, or type the **Start Time**. Add the **End Time**
   when you finish.
6. Fill in the kids count and any notes, then tap **Save Log**.

The Route Sub/Breakdown box clears itself after each save so the next log is
not marked by accident.

### Fill the form from text (Voice tab)

Type, paste or dictate a note such as:

```
route 336 tier 0 bus 4114 PM 15 kids
```

Then tap **Fill Form From Text**, or copy the note and tap
**Paste & Fill From Clipboard**. The app reads route, tier, bus, kids,
AM/PM, delay minutes, weather, spare bus, school name, and the words
"breakdown" or "route sub". A message lists what it filled in. Check the form,
then tap **Save Log**. Nothing is saved automatically.

### Use Looki notes

The page cannot connect to Looki by itself (Looki signs in through a
browser login). To use Looki:

1. In Claude Code with the Looki plugin connected, ask for today's note as one
   line.
2. Copy that line.
3. In the app, open the **Voice** tab and tap **Paste & Fill From Clipboard**.

Your phone may ask permission to read the clipboard the first time. If it
refuses, paste into the text box and tap **Fill Form From Text**.

### Export your logs

Open the **Export** tab to download your logs as a CSV file you can open in
Excel or Google Sheets.

### Send logs to Google Sheets (optional)

In **Settings**, paste your Google Apps Script web app URL (it ends in
`/exec`) into the webhook box. Each saved log is then sent to your sheet. Each
log includes these fields: id, localDate, localTime, school, route, tier, bus,
spare, spareBus, breakdownCover, startTime, endTime, weather, road, tripShift,
traffic, delayMin, odometer, kids, notes, issues, createdAt.

### Clear everything

**Settings > Clear and Reset - All Keys** removes saved logs, schools and
settings from this device. You must tick the confirmation box and then tap
**Yes, Delete All**. This cannot be undone, so export your logs first.

## Install it on your phone

- **Android (Chrome):** open the site, tap the menu (three dots), then
  **Add to Home screen** or **Install app**.
- **iPhone (Safari):** open the site, tap Share, then **Add to Home Screen**.

## Where your data lives

Logs are saved in your phone's browser storage (localStorage), on that device
only. They are not uploaded anywhere unless you set up the Google Sheets
webhook. Clearing your browser data, using a private window, or switching
phones will not carry your logs over, so export regularly as a backup.

## Put it online

Host the single `index.html` anywhere that serves static files.

- **GitHub Pages:** repository **Settings > Pages**, choose the main branch
  and the root folder, then save.
- **Netlify:** drag the file onto a Netlify site, or link this GitHub
  repository under **Site configuration > Build & deploy**. No build command is
  needed.

Keep the file named `index.html` at the top level of the repository.

## Updating

Replace `index.html` with the new version and commit it. Your saved logs stay
on your device and are not affected by an update. If the app looks unchanged
after an update, refresh the page or close and reopen it.

## Privacy

Log kid counts only. Do not enter student names in notes if your district does
not allow it.

Version 7.1
