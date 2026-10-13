# Lead Cadence Planner

A one-page app for working the weekly lead list: import, score, filter by time zone, and run the daily call / email / LinkedIn cadence from the Peopletrail Outbound Sales Playbook.

## The one rule: lead data never goes in this repo

The repo holds only `index.html` and this README. Lead lists are loaded into your browser and stored there (IndexedDB) on your computer only. **Never commit a CSV, Excel file or tracker export to GitHub.** GitHub Pages sites are public, even when the repo is private on most plans.

Add this `.gitignore` so a stray file can't slip in:

```
*.csv
*.xlsx
*.xls
```

## Put it on GitHub Pages (5 minutes)

1. On github.com, create a new repository (for example `lead-cadence`).
2. Click **Add file → Upload files**, upload `index.html`, `README.md` and `.gitignore`, then **Commit**.
3. Go to **Settings → Pages**. Under **Source**, choose **Deploy from a branch**, branch `main`, folder `/ (root)`, then **Save**.
4. After a minute the page shows your site link (`https://<username>.github.io/lead-cadence/`). Bookmark it.

You can also just double-click `index.html` to run it locally. It needs internet once to load the Excel library.

## Setting up a second rep

Send your teammate the GitHub Pages link. The first time it opens in a new browser, the app asks **Who's using this browser?** Pick your name (or type it) and add your phone number. That name and phone fill [Rep] and [phone] in every script, voicemail and email signature, and new imports are assigned to you.

Use **Chrome or Edge** if you can. Firefox and Safari work, but they can't auto-save to an Excel file, so use **Download tracker** at the end of each day. Safari can also clear a site's data if you don't open it for a week or so.

Each rep's leads live only in their own browser. Nothing syncs on its own (see "How the two reps share" below).

## Weekly workflow

1. **Monday: Import.** Upload the ZoomInfo export (CSV/XLSX) or paste the lead report. Check the column mapping, pick the owner, import. Duplicates are merged, not doubled. If you and your teammate split one list, split it before importing so you don't both work the same people.
2. **Afternoon prep: Score.** Open each new company and tick **Higher-touch** and **Organized**, and set a **Trigger** if you found one. Mid-sized is set automatically from estimated annual hires (250–3,000). These raise the Optimal score and move the account up the queue.
3. **Each morning: Today tab.** Click **Start top contacts** (the app recommends how many your caps can carry), then work the three blocks in order: calls (sorted by who's in their best calling window, east to west), emails (opens your mail app pre-filled), LinkedIn. Click an outcome on every touch.
4. **End of day: Download tracker.** Save the `.xlsx` to your shared drive. This is your backup.
5. **Friday: KPIs tab.** Check the week against your dial target, and download the KPI report if your manager wants it.

## Run sheets

The **Run Sheet** tab builds a time-blocked plan for each of the next 5–20 business days, like the Oct 6 workbook but generated automatically:

- Each block shows your time and the Eastern / Central / Mountain / Pacific time, colored by whether that's a good window for that channel.
- Every due call, email and LinkedIn touch is placed in the block where that prospect is in their best window, until the block is full. Overflow is flagged.
- **Planned starts** spreads the start queue over the coming days so you can see the whole cadence load in advance.
- **Download run sheets (.xlsx)** gives you How to use, Run Sheet, one tab per day with scripts filled in, and a Scoreboard with formulas. Log outcomes in Excel, then import the file back into the app and every outcome is applied.
- **Edit daily schedule** lets you change, add or remove blocks, or load a preset (the playbook block, or your Oct 6 9:00 start).

## Call-backs

- On any call, click **Call back** and pick a date and time **in the prospect's time zone**; the app converts it to yours, including the Arizona and Hawaii shift when daylight saving starts or ends.
- **In 2 hours** only books today if that still falls inside their calling day and before your last schedule block ends. Otherwise it sets the next business day at 10am their time and tells you. Any time outside their business hours is flagged.
- **I spoke with them:** the cadence stops, the call-back becomes the next step, and their colleagues pause. **Gatekeeper said:** the cadence keeps going and the call-back is added on top.
- Call-backs show at the top of Today with a countdown, and on the Run Sheet in the block that contains that time.
- **No answer** on a call-back sets one retry for the next business day at the same time, up to 3 tries.
- In the Excel run sheet, call-backs are their own rows (Channel = Callback). Typing "call back" as a call outcome sets one for the next day at 10am their time; fix the exact time in the app.

## Bounce-backs

When a bounce arrives after you clicked Sent, paste the bounce message (or the address, or a name) into **Got a bounce-back?** on Today. You can also click **Bounced?** next to the email in the contact's history. Then pick the type:

- **Address doesn't exist:** enter the right address. The app suggests likely ones from the pattern your other contacts at that company use. The email goes back in your list to resend. With no address, that contact's emails pause and calls and LinkedIn continue.
- **Blocked by their server:** resending won't help, so that contact's emails pause. Two blocks at one company pause emails to the whole company.
- **Temporary:** the email goes back in your list.

If bounces pass 2% of the week's emails, Today shows a warning. Blocks can mean IT should check SPF, DKIM and DMARC on peopletrail.com.

## Does it save?

Yes. Every change saves instantly in the browser and survives closing the tab or restarting. It does not move between browsers or computers by itself, and clearing site data erases it. Two ways to protect it:

1. **Auto-save to an Excel file** (Settings, Chrome or Edge): pick a file once, ideally in OneDrive or Google Drive, and every change is written to it. After a browser restart, click "Resume auto-save" once. Close the file in Excel while the app is open, because Excel locks it.
2. **Download tracker** daily.

## What you can edit

- **Scripts tab:** any opener, voicemail, email or LinkedIn message, plus add your own. Reset restores the playbook wording.
- **Cadence tab:** every step's day, channel, label and script, add or remove steps, and which opener/voicemail each persona gets.
- **Run Sheet tab:** the daily time blocks.
- **Settings:** reps, daily caps, per-hour rates, best windows for calls / emails / LinkedIn, the mid-sized hire range, email signature.

Edits travel inside the tracker file, so your teammate can load the same scripts and cadence.

## How the two reps share

Each rep runs the app in their own browser with their own assigned leads. To see each other's work, import your teammate's tracker file on the Import tab: it merges by contact and keeps whichever version was updated most recently. Use **Working as** in the header to switch views, or choose **Both reps**.

- **Owners stay right.** Each contact keeps the rep who owns it, matched by name. If your copy still says "Rep 2", it's renamed to your teammate's name the first time you import their tracker.
- **Same lead on both lists.** If you both imported the same person, they're merged into one contact (matched by email, then name and company) and tagged **Both had it**. Filter Leads by Source → "Both had it", agree who keeps each one, set the owner, then click **Mark sorted**.
- **What a teammate's tracker changes.** It can bring their script, cadence, persona, best-window and scoring edits (the app asks first). It never changes your name, phone, daily schedule, caps or per-hour rates. Restoring **your own** backup brings everything back, schedule included.
- **Company rules work across reps after a swap.** "Max 2 active per company" and pausing colleagues after a connect only see the contacts in your browser, so swap trackers at least weekly.

## KPIs

The **KPIs** tab is built from outcomes you already log, so there's nothing new to enter. Pick This week, Last week, Last 30 days, Last 90 days or All time. It follows **Working as**, and **Both reps** adds a side-by-side table (after you've imported your teammate's tracker).

- **Headline numbers:** dials per day against your target, live-answer rate, conversations, discovery calls booked, email reply and bounce rates, LinkedIn accepts, and new contacts started. "Conversations" follows the playbook's chain: phone calls where you spoke with the prospect. Email and LinkedIn replies are counted separately.
- **Playbook scorecard:** the first three links of the playbook's chain (calls → conversations → discovery booked) with the conversion between each, the share of discovery calls at Optimal-3 accounts, and the playbook's "find the leak" table with your own numbers beside each symptom. Demos, agreements and revenue stay in HubSpot.
- **Monthly pace:** discovery calls booked this month against a goal (default 12.5 per rep, from the 2026 plan's 2.5 Optimal deals a month at about 20% conversion; the plan calls this illustrative, so set the real number in Settings). It also estimates how many dials a day the goal needs at your last-90-day rate.
- **Weekly trend** for the last 8 weeks.
- **Which touches get responses:** every cadence step with how often it was done, how often the prospect responded on that touch, and which step produced the first response for each meeting. Steps with no responses after 30+ tries are flagged. This is the evidence for trimming email steps to stay under the email cap.
- **Live-answer rate by the prospect's local hour:** checks the call windows against your own dials. Outcomes imported from a run sheet are left out, because the app only knows when you imported them, not when you called.
- **By company size, Optimal score and persona:** reach and meeting rates per group. The size table is the evidence for the 250–3,000 mid-sized range.
- **Download KPI report (.xlsx)** with all of the above.

The **HubSpot CSV** now includes the playbook's custom properties as their own columns (Persona, Mid-sized, Higher-touch, Organized, Optimal score, Annual checks, Current provider, Renewal date, Trigger), so they map straight to HubSpot properties on import. On Today, emails to Optimal-3 accounts are tagged "personalize this one" (the playbook's 10 custom emails a day).

"Discovery booked" set from the Connected list, the status menu or bulk edit now records the date, so it counts in the right week.

## What the app does automatically

- **Time zone per contact** from the direct phone's area code, then the business phone, then the company state. You can override it.
- **Persona** from the job title, which picks the day-1 opener, voicemail and first email. Owners, COOs and CFOs get the "cost of a bad hire" opener (O, new wording for manager review) and the playbook's referral email, Sequence C ("who owns background checks?"), asking them to point you to the screening owner. Email 2 replies in the thread of whichever email 1 they got. Change any persona's choices on the Cadence tab. A company trigger (new HR leader, hiring surge, new state) switches to the trigger opener.
- **15-touch, 21-day cadence** (6 calls, 6 emails, 3 LinkedIn) with weekend due dates rolling to Monday. Old leads (with a last-contacted date or prior status) get a shorter re-engage track instead.
- **Contract renewals** (playbook slide 14, Sequence F): when a company has a renewal date in the next 90 days and nobody there is in a cadence, Today lists it with a button per contact. Contacts you've worked before get the re-engage track; new ones get the cold cadence. **Not now** hides it until the renewal date changes. Add renewal dates in the contact drawer under Company.
- **Restarting a cadence keeps history.** Earlier touches stay in the contact's history, the tracker and your KPIs.
- **Stops** a contact's cadence on a connect or reply, and **pauses** colleagues at the same company. No answer after the last step moves the contact to Nurture with a 90-day revisit.
- **Max 2 active contacts per company** at once (change in Settings).
- **Discovery booked → HubSpot.** Settings has an export of discovery-booked contacts as a HubSpot import CSV.

## Not from the playbook (review with your manager)

- The re-engage track for old leads and its opener (marked in the Scripts tab). The renewal trigger for it is in the playbook (Sequence F); using it for old leads with no renewal date is not.
- The wording of opener O (cost of a bad hire). The playbook names the approach for executives but doesn't script it.
- The mid-sized range of 250–3,000 annual hires, read from the playbook's "250 to a few thousand people a year."
