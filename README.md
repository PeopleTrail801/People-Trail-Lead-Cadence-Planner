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

Use **Chrome or Edge** if you can. Firefox and Safari work, but they can't auto-save to an Excel file, so click **Backup** at the end of each day. Safari can also clear a site's data if you don't open it for a week or so.

Each rep's leads live only in their own browser. Nothing syncs on its own (see "How the two reps share" below).

## Weekly workflow

1. **Monday: Import.** Upload the ZoomInfo export (CSV/XLSX) or paste the lead report. Check the column mapping, pick the owner, import. Duplicates are merged, not doubled. If you and your teammate split one list, split it before importing so you don't both work the same people.
2. **Afternoon prep: Score.** Open each new company and tick **Higher-touch** and **Organized**, and set a **Trigger** if you found one. Mid-sized is set automatically for Prime accounts (gold, $10K–$150K a year in checks). These raise the Optimal score and move the account up the queue.
3. **Each morning: Today tab.** Nurture re-contacts are already on the list. Click **Start top contacts** (the app recommends how many your caps can carry; the queue mixes every lead source plus closed-lost follow-ups and revisits that are due), then work the three blocks in order: calls (sorted by who's in their best calling window, east to west), emails (opens your mail app pre-filled), LinkedIn. Click an outcome on every touch.
4. **End of day: Backup.** Click **Backup** at the top and save the `.xlsx` to your shared drive (or turn on auto-save).
5. **Friday: KPIs tab.** Check the week against your dial target, and download the KPI report if your manager wants it.

## Sprint and nurture (version 2.1, not in playbook, review)

A contact no longer runs all 15 touches. It leaves its cadence as soon as it has had **3 calls, 3 emails and 1 LinkedIn message**, then moves to **nurture**:

- **Business days (not in playbook, review).** Cadence days now count Monday to Friday: day 3 is the third working day from the start, skipping weekends and days off. Before, day N was N-1 calendar days later and weekend dates rolled to Monday, so at higher volume Mondays got two to three times the calls and LinkedIn touches of other days. In a four-week test at 40 dials a day, business-day spacing gave 37–46 dials every day instead of 65–80 on Mondays and about 35 the rest of the week. Change it on the Cadence tab (**How cadence days are counted**); it applies to contacts started from then on, each contact keeps the spacing it started with, and contacts already in a cadence before this version stay on calendar days until their next start. The choice is shared through the tracker. Marking a day off still moves everything once, not twice.
- **Sprint.** Cold: 8 touches, ends business day 7 (about 9 calendar days) (connection request, calls 1–3, emails 1–3, LinkedIn message 1). Re-engage: 8 touches over 10 days (email 2 "quick question" and a LinkedIn message added). Win-back: 7 touches, ends day 16 (call 4 skipped). RFP check-in: 7 touches over 14 days (LinkedIn reconnect day 3, email day 8, call 3 and email 3 day 14 added). Steps past the exit are marked **after the sprint** on the Cadence tab.
- **What counts.** Any logged call or email. For LinkedIn only a message counts (message, voice note, win-back reconnect), not a connection request, Followed or Follow requested. **Skip** doesn't count, so the sprint runs on until the minimum is really met. No LinkedIn profile: no LinkedIn minimum, one more email. No email (or emails paused after a bounce): no email minimum.
- **Nurture rounds.** Every 14 days the contact comes back on Today for one call and one email (opener NR, voicemail VMN, email "one idea for [Their Company]"), tagged "Nurture 1 of 3". They start by themselves. After 3 rounds the contact is **parked** and comes back as a revisit in 90 days, through the start queue, on the re-engage track.
- Any real answer (connected, replied, booked, not now, not interested, unsubscribe) ends the rounds; out of office doesn't. **Undo last touch** puts the contact back in the sprint and restores its round.
- **Settings → Sprint and nurture**: the three minimums, days between re-contacts, number of rounds, or switch it off to go back to the full playbook cadence. Shared with your teammate through the tracker. Remove the nurture email on the Cadence tab if you need fewer emails.
- **First open after the update:** your contacts who already meet the minimum move to nurture, with the first re-contact 14 days after their last touch. A note on Today says how many.

## Every lead type in one start queue

The start queue holds new leads from **every source** (ZoomInfo, Apollo, Sales Navigator, Event, Other list, Referral, Inbound, Manual add, Old lead) plus **closed-lost follow-ups** whose date has come and **revisits** that are due. The queue line shows the mix (for example "2 ZoomInfo · 1 Inbound · 1 Closed-lost due"), and **Start top contacts** puts each on the right track: cold, win-back / RFP check-in, or re-engage. Inbound leads rank first, then referrals, then the Optimal score (not in playbook, review). Nurture re-contacts aren't in the queue; they start by themselves and their calls come out of the day's room first.

- **+ Add lead** (Today's start queue line, top of Leads): for referrals, inbound requests and one-offs. Name and company are required; pick the source and who referred them, and tick **Start the cadence today** to put call 1 on today's list (or untick to put them at the top of the queue). A lead already in the app is updated, not doubled.
- **Lists from other tools:** Import as usual and pick the **Source** (Apollo, Sales Navigator, Event, Other list…). Source shows as a tag on Today, filters Leads, and splits KPIs → Segments.
- New saved views in Leads: **Nurture: re-contact due** and **Referral or inbound, not started**.

## Lead types, the upload log and Leads added

- **Per-row lead type on import.** A column such as "Lead type", "Lead source" or "List name" maps to **Lead type / source** automatically, and each row gets its own type. Everyday wording is read (for example "Apollo export" is Apollo, "Trade show booth" is Event, "Website form" is Inbound). The review step shows how many rows were recognized; blank or unrecognized rows take the **Source** picked below the preview, and a loss reason or close date always means closed lost. With **Update existing leads** ticked, a re-import can change a lead's type (never to or from closed lost). HubSpot's "Original Source" analytics column is ignored.
- **Bulk fix.** Leads → tick leads → **Set lead type…** (closed-lost leads are left alone; use Mark closed-lost for those).
- **When leads came in.** Every lead keeps the date it was added. Leads has an **Added** column (date and lead type), an **Added this week / last week / last 30 or 90 days** filter, and **Sort: newest added**.
- **Upload log** (Import tab): every lead list or pasted report imported, with date, file, owner, how many were new or updated, the lead types of the new ones, and the Source picked. Trackers and run sheets aren't logged. It travels in the tracker (sheet "Uploads"), so your teammate's uploads show after a swap; it follows Working as.
- **KPIs → Leads added**: leads added in the period by week and by lead type, with how many have a phone and were started, reached and booked. The card at the top compares leads added a week (last 4 weeks) with what your dial target needs, and shows the days of starts left in the start queue (not in playbook, review). The KPI report download adds "Leads added by type", "Leads added by week" and "Upload log" sheets.

## Filling both power hours

**Ramp-up recommendation (not in playbook, review).** The number in the start-queue box now plans for ramp-up instead of the long run. It counts the calls already on the books for the next 15 business days (cadence steps due, overdue ones, call-backs, nurture re-contacts and dials logged today, allowing for the expected live-answer drop-off), then works out how many new contacts to start on each day to keep every day as close to your dial target as it can. A day short of the target counts more than a day over it. With nothing in nurture yet, that's about twice the long-run number (for example about 18 a day for a 40-dial target instead of 9), and it falls as nurture calls arrive. With calendar-day spacing (days 3 and 5 roll weekend dates to Monday) it starts more early in the week and fewer on Thursday and Friday; with business-day spacing the calls spread evenly anyway. Contacts you've already started today count toward today's number. **Why N?** shows the day-by-day plan, the long-run number, and the email and LinkedIn load at that pace. The run sheet's planned starts use the same day-by-day plan, so the week's dial counts show what you'll actually make. Set the dial target in Settings → Daily capacity first.

**Why 7?** on the start queue line now shows how many dials your call blocks hold (each Calls block on the daily schedule × dials per hour): about 81 a day with the 9:00 run sheet. **Use 81 as my dial target** sets it (not in playbook, review: the playbook's block is 30). Approximate daily load:

| Dial target | New contacts a day | Emails a day | LinkedIn a day |
|---|---|---|---|
| 30 (playbook) | 7 | 28 | 12 |
| 81 (both power hours) | 19 | 75 | 32 |
| 30, nurture call only | 7 | 17 | 12 |

Nurture adds an email each round, so emails stay over the 20 cap unless the nurture email is removed. About 19 new contacts a day is roughly 95 a week, so it needs lists from more than one source.

## Account size colors

Every lead is color-coded by estimated annual check spend: estimated annual checks (one per hire) × average revenue per check (Settings, default $45).

- **Gold · Prime:** $10K–$150K a year, the prime customer.
- **Green · RFP:** over $150K a year; these accounts usually buy through an RFP.
- **Blue · Small:** under $10K a year.

Prime accounts automatically get the Optimal score's **Mid-sized** green light, so the score and the color always agree (you can still override Mid-sized per company). The badge (for example "Prime · $63K") shows on Today cards, Leads rows and the contact card, with a matching colored stripe. Filter Leads by size. The range and price per check are in Settings.

Annual hires come from the lead file's "Est. annual hires". When that's blank, the app estimates them from employees × the industry's annual hiring rate (BLS JOLTS benchmarks: restaurants ~85%, hotels ~65%, gaming and trucking ~60%, civil construction ~55%, construction and home-improvement retail ~50%, agriculture/real estate/waste/logistics/post-acute ~40%, physician clinics ~35%, cruise/marine/aviation/distribution ~30%, hospitals and engineering/design ~28%, fuel ~25%, insurance/title/financial holding ~22%, pipeline ~20%, local government/transit/airports ~18%, state government and utilities ~15%). Estimated figures show an asterisk. These are directional sizing estimates, not company-reported numbers.

## Working ahead and moving tasks

- **Tomorrow's tasks** (bottom of Today): click **Work ahead** to see the next business day's calls, emails and LinkedIn touches and do them now. A touch done early counts today, and the rest of the cadence keeps its dates. Something still due today on the same channel for that person comes first.
- **Do tomorrow** (on every task due today): moves just that touch to the next business day. The rest of the cadence doesn't move. Run sheets and the tracker file keep the move.

## Today, focus mode and the layout

- **Header (one row):** tabs, **✉ Email back** (paste any reply, auto-reply or bounce), a backup status dot (green good, amber needs a backup, red problem; hover for details), **Backup** (download your tracker) and **Working as**.
- **Bar that stays at the top of Today:** "N of M done today", dials against target, and a jump button with a count for each section (Call-backs, Connected, Catch up, Calls, Emails, LinkedIn, Waiting).
- **Needs attention:** one strip for HubSpot exports, closed-lost follow-ups, renewals, revisits, contacts missing a phone or email, and a reminder when your teammate's tracker is over a week old.
- **Order:** call-backs, then **Connected** (warmest first), then catch-up, then today's calls, emails and LinkedIn. The start queue is one line; **Why 7?** shows the math.
- **Focus mode ▸** shows one task at a time with its script open. Keys: **1–9** log the numbered outcome (calls: 1 no answer, 2 voicemail, 3 connected, 4 gatekeeper, 5 call back, 6 meeting booked, 7 wrong number, 8 not the right person, 9 do not call; emails: 1 sent, 2 replied…; LinkedIn: 1 sent, 2 waiting for response…), **D** dial, **O** open the email or LinkedIn profile, **C** copy, **T** do tomorrow, **N** skip for now, **P** back, **Esc** exit. Filter to Calls for your power hour. A banner appears when a call-back is 15 minutes away.
- **Research list** (bottom of Today): contacts in your start queue missing a phone or email.

## Call-back alerts

Click **🔔 Alert me before call-backs** (Today) or turn them on in **Settings → Call-back alerts**. You get a browser notification (plus a sound and an in-app alert) a set number of minutes before each call-back, with their name, company, phone and your note. It works while the app is open in a tab, even in the background. If notifications are blocked for the site, you still get the in-app alert and sound.

## Check new leads against HubSpot

On the Import tab, upload a HubSpot export of customers, open deals and anyone else you shouldn't cold-call (contacts and/or companies). Leads matching on email, company domain or company name are tagged **In HubSpot: [stage]** and held out of the start queue; the queue line says how many. Open one and click **Work it anyway** to let it through. Leads → **Already in HubSpot** lists them. The list travels in the tracker, so your teammate gets it too. Reload it every month or so.

## Other screens

- **Leads:** saved views across the top (Prime not started, Not started, In a cadence, Connected or booked, No touch in 14+ days, Closed-lost due in 30 days, Missing phone or email, Already in HubSpot, Both reps had it) and a **Last touch** column.
- **KPIs:** four views: Summary, Playbook scorecard, Cadence steps and hours, Segments.
- **Scripts:** search box, filter by library, libraries collapse, and **Preview with** fills every script with a chosen contact's details.
- **Settings:** a menu down the left side jumps to each section.

## Getting leads into HubSpot

The playbook's rule (slide 31): lead status tracks prospecting, and the deal is created in HubSpot once pricing is discussed and a follow-up is booked. So when a lead books discovery, the app exports the **contact and its company** (one file, both objects, linked on each row) with lead status "Discovery booked". It doesn't create deals.

1. **Once:** in Settings, add each rep's **HubSpot login email** (Reps card) so owners are assigned. Under **Settings → HubSpot**, check the lead status names match your HubSpot exactly.
2. **Once, in HubSpot:** make sure the playbook's properties exist (Persona on contacts; Mid-sized, Higher-touch, Organized, Annual checks (est.), Current provider, Contract renewal date on companies). Optional contact properties: Best time to reach, Prospecting summary (multi-line text). Optimal score is calculated in HubSpot, so it isn't in the file.
3. **Each time someone books:** Today's **Needs attention** strip shows **Export N to HubSpot**. Click it (also in Settings → HubSpot). Each contact is marked with the export date so it isn't exported twice; **Export all discovery-booked again** re-sends everyone. Any other contacts: tick them in Leads → Export to HubSpot CSV.
4. **In HubSpot:** Contacts → Import → file from your computer → one file → multiple objects → Contacts and Companies. Map contact columns to contact properties and company columns to company properties, map "Contact record ID" to Record ID, and choose "Don't import" for anything you haven't built.

**What's in the file:** email, name, title, phones, contact owner, lead status, persona, best time to reach, and a **Prospecting summary** (cadence, touch counts, when you spoke, when discovery was booked, Optimal score and account size, trigger, closed-lost details, notes); company name, **domain**, owner, city, state, employees, industry, the three green lights, annual checks, current provider and renewal date.

**No duplicates:** HubSpot matches contacts by email and companies by domain. The domain comes from the ZoomInfo **Website** column if there is one, otherwise from the contact's work email (Gmail and other personal addresses are skipped, and the export warns you). Closed-lost contacts carry their HubSpot **Record ID**, so they update the existing record. You can edit a company's domain in the contact card.

## Days off and catching up

- **Catch up: missed days** (top of Today) lists every touch that was due on an earlier day and hasn't been done, with a count per day. Today's call, email and LinkedIn sections show only today's work.
- **I was off [day]: shift the cadence** marks that day as a day off and moves every one of your contacts' remaining touches forward one business day, so the spacing between touches stays the same. Call-backs booked for that day move to the next business day at the same time. An **Undo** bar appears for 10 minutes.
- **Settings → Days off**: add holidays and PTO ahead of time. **Add and shift the cadence** moves everything after that date; **Add without shifting** just keeps new plans off that day. Cadences, call-back retries and run sheets skip days off like weekends. Days off belong to you and don't travel to your teammate.

## LinkedIn: waiting for response, no profile, subject lines

- **Waiting for response** logs the message or request as sent and adds the person to **LinkedIn: waiting for response** on Today, with how many days they've waited. When they answer, click **Replied** (moves them to Connected and counts as a response), **Accepted**, or **No response**. Their cadence keeps going in the meantime.
- **No LinkedIn profile** turns that contact's remaining LinkedIn touches into emails: the connection request becomes an email the next day (day 1 already has one), the message an email on day 7, the voice note an email on day 12. Undo by changing **LinkedIn** in the contact card. These add to your daily email count.
- **Subject lines**: LinkedIn message scripts have a subject with a **Copy** button. LinkedIn only shows subjects on InMail and Sales Navigator messages to people you aren't connected to. Edit them on the Scripts tab.

## Copy buttons

Email cards have **Copy** next to the address and the subject line, plus **Copy body**, for when you send from a mail app that doesn't open from the link. The contact card has Copy next to the email too.

## Updating and removing leads

- **Edit one lead:** click it anywhere (Today, Leads) to open its card. Every field is editable, including status, owner, best time and the closed-lost details.
- **Delete:** **Delete lead** at the top of the card, or tick several in Leads and click **Delete**. An **Undo** bar appears for 10 minutes.
- **Update many at once:** tick them in Leads and use the bulk menus (assign, set status, **Mark closed-lost: reason…**). Or re-import a file on the Import tab with **Update existing leads with this file's values** ticked: values in the file replace what's there, and empty cells never erase anything. Without the tick, only blanks get filled.
- **Mark as closed-lost:** the button on any lead's card stops its cadence and opens the closed-lost details.

## Closed-lost deals (win-backs)

Deals that were quoted and lost are already in HubSpot. Bring them into the planner to time the follow-up and work it by phone.

1. **Export from HubSpot** (contacts or deals) with: name, email, phones, job title, company, state, employees, industry, deal name, amount, close date, closed lost reason, recycle date, and, if you track them, competitor, contract renewal date and best time to call.
2. **Import it** on the Import tab. Source → **Closed lost (HubSpot export)**, or leave it on Auto: rows with a loss reason or close date are treated as closed lost. Columns map automatically.
3. Each contact waits (status Nurture) until its **follow-up date**: the HubSpot recycle date if there is one; otherwise 90 days before a known renewal; otherwise a default for the loss reason (price 90 days, competitor 120, timing 90, no decision 45, other 90; edit in Settings).
**Why they went another way.** Tick every reason that applies: price; reporting and technology; service and speed of results; went with a competitor; wants an industry specialist; not interested; timing; no decision; under contract; RFP where you were a comparison bid; RFP terms you can't meet. Or paste their response into the card: the app reads the competitor and reasons from it (for example "First Advantage is who we have chosen. Pricing… Reporting and Technology… Services and Speed of Results" becomes First Advantage + price, reporting and technology, speed and service). Also set **how far it got** (emailed only, talked, demo done, quote sent); the scripts refer back to it ("We last connected at your demo back in May…").

**Which script.** RFP reasons use the **RFP check-in** (3 touches: get on the next bid list, learn the criteria, ask whether the terms can move). Otherwise: a renewal within 120 days; then not interested ("go for the no"); industry specialist (uses [Industry proof] from Settings); two or more of price / technology / service ("which one matters most now?"); then the single reason.

**Follow-up timing** uses the longest wait among their reasons (price 90 days, technology 120, service 120, competitor 120, industry 180, not interested 180, timing 90, no decision 45, RFP 365), unless there's a HubSpot recycle date, a next RFP date (60 days before) or a known renewal (90 days before). All editable in Settings.

4. On that date they appear on Today under **Closed-lost follow-ups due** with the loss reason, quote, who they went with and their best time. Click **Start win-back track**.

**Win-back track** (8 touches over 21 days, phone-first): call 1 + voicemail and email 1 chosen by loss reason (price, competitor, timing, no decision, or renewal if one is within 120 days), LinkedIn reconnect day 3, call 2 with a new reason day 5, email 2 day 8, call 3 + voicemail day 12, "close the file" email day 16, call 4 + closing voicemail day 21. Win-back call cards show the loss summary and the brush-off turnarounds.

**Fill in two things for better scripts:** on the contact, "What they said" (fills [Loss detail]); in Settings, "What's new at Peopletrail" (fills [What's new], used whenever a script gives a new reason to talk).

**Best time to reach** (any contact): type it in the contact card, e.g. "Tue/Thu 8-9am" or "after 2pm", or import it from HubSpot. The app plans and sorts that contact's calls to match and shows it on every call and call-back card.

**Already in HubSpot.** When a win-back books, the app reminds you to open the existing record and start a new deal, and the HubSpot CSV export leaves closed-lost contacts out. The quoted amount sets the account-size color (instead of the estimate).

**Call-back scripts and brush-offs** (all contacts): every scheduled call-back shows an opener that keeps your word ("You asked me to call you back at…"), a voicemail if they miss it, and a gatekeeper version. Brush-off turnarounds follow the playbook's Ledge → Mirror → Pause → Ask. Edit them on the Scripts tab under "Call-backs and brush-offs".

**Sources of the techniques.** Jeb Blount's five-step phone framework (get attention, identify yourself, the reason, a because, ask) and Art Sobczak's rule of never calling "just to check in" (every follow-up brings a new reason) shape the openers. Belal Batrawy's "no fluff, lead with the problem" shapes the no-decision opener. Script names say which idea each one uses. Blount is in the playbook's framework list; the others aren't, so the win-back scripts are marked for manager review. Check them against your own training material before rolling them out.

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

## Email replies and auto-replies

After you click **Sent**, the contact stays in the cadence and leaves Today until their next step is due. Replies can come in any time, so paste them into **✉ Email back** at the top of any page (the whole reply, or just their address or name). The app reads the message, picks a type, and you confirm:

- **Interested** → Connected (colleagues pause). **Booked a meeting** → Discovery booked.
- **Not now / check back later** or **Not interested** → cadence stops; back on Today on the revisit date (90 or 180 days by default, editable).
- **Not me / talk to someone else** → Unqualified; add the person they named and they go to the top of the queue, tagged "Referred by".
- **Unsubscribe** → Do not contact.
- **Out of office / holiday** → enter the return date (read from the auto-reply when it can). The contact's remaining touches move later so the cadence restarts when they're back. Not counted as a response.
- **Left the company** → Unqualified; add their replacement if named.
- **Bounce-back** → opens the bounce window below.

The reply is recorded on the email it answers, so the KPIs' reply rate and "which touches get responses" count it. You can also log one from the contact card (**Log an email reply**, or **Replied?** next to a sent email), and **Undo last reply / touch** reverses it.

## Bounce-backs

When a bounce arrives after you clicked Sent, paste the bounce message into **✉ Email back** at the top; the app recognizes it as a bounce. You can also click **Bounced?** next to the email in the contact's history. Then pick the type:

- **Address doesn't exist:** enter the right address. The app suggests likely ones from the pattern your other contacts at that company use. The email goes back in your list to resend. With no address, that contact's emails pause and calls and LinkedIn continue.
- **Blocked by their server:** resending won't help, so that contact's emails pause. Two blocks at one company pause emails to the whole company.
- **Temporary:** the email goes back in your list.

If bounces pass 2% of the week's emails, Today shows a warning. Blocks can mean IT should check SPF, DKIM and DMARC on peopletrail.com.

## Does it save?

Yes. Every change saves instantly in the browser and survives closing the tab or restarting. It does not move between browsers or computers by itself, and clearing site data erases it. Two ways to protect it:

1. **Auto-save to an Excel file** (Settings, Chrome or Edge): pick a file once, ideally in OneDrive or Google Drive, and every change is written to it. After a browser restart, click "Resume auto-save" once. Close the file in Excel while the app is open, because Excel locks it.
2. Click **Backup** daily.

## What you can edit

- **Scripts tab:** any opener, voicemail, email or LinkedIn message, plus add your own. Reset restores the playbook wording.
- **Cadence tab:** every step's day, channel, label and script, add or remove steps, and which opener/voicemail each persona gets.
- **Run Sheet tab:** the daily time blocks.
- **Settings:** reps, daily caps, per-hour rates, best windows for calls / emails / LinkedIn, account size (revenue per check and the prime range, which also sets Mid-sized), email signature.

Edits travel inside the tracker file, so your teammate can load the same scripts and cadence.

## How the two reps share

Each rep runs the app in their own browser with their own assigned leads. To see each other's work, import your teammate's tracker file on the Import tab: it merges by contact and keeps whichever version was updated most recently. Use **Working as** in the header to switch views, or choose **Both reps**.

- **Everything on a lead travels.** Statuses, touch history (including earlier cadences), call-backs, bounces, replies and auto-replies, LinkedIn status, best time, moved tasks, closed-lost details, unqualified reasons and company scoring all come across in the tracker file. With **Working as → Both reps**, your teammate's Today, Leads and KPIs show exactly what you see.
- **Owners stay right.** Each contact keeps the rep who owns it, matched by name. If your copy still says "Rep 2", it's renamed to your teammate's name the first time you import their tracker.
- **Same lead on both lists.** If you both imported the same person, they're merged into one contact (matched by email, then name and company) and tagged **Both had it**. Filter Leads by Source → "Both had it", agree who keeps each one, set the owner, then click **Mark sorted**.
- **What a teammate's tracker changes.** It can bring their script, cadence, persona, best-window and scoring edits (the app asks first). It never changes your name, phone, daily schedule, caps or per-hour rates. Restoring **your own** backup brings everything back, schedule included.
- **Nurture travels.** Nurture rounds, parked dates, sources and "referred by" come across in the tracker. Re-contacts start only in the browser of the rep who owns the lead (the name picked on the first-run screen), even when you view **Both reps**, so a teammate's leads are never changed in your browser; their due re-contacts show in your view after the next swap.
- **Company rules work across reps after a swap.** "Max 2 active per company" and pausing colleagues after a connect only see the contacts in your browser, so swap trackers at least weekly.

## KPIs

The **KPIs** tab is built from outcomes you already log, so there's nothing new to enter. Pick This week, Last week, Last 30 days, Last 90 days or All time. It follows **Working as**, and **Both reps** adds a side-by-side table (after you've imported your teammate's tracker).

- **Headline numbers:** dials per day against your target, live-answer rate, conversations, discovery calls booked, email reply and bounce rates, LinkedIn accepts, and new contacts started. "Conversations" follows the playbook's chain: phone calls where you spoke with the prospect. Email and LinkedIn replies are counted separately.
- **Playbook scorecard:** the first three links of the playbook's chain (calls → conversations → discovery booked) with the conversion between each, the share of discovery calls at Optimal-3 accounts, and the playbook's "find the leak" table with your own numbers beside each symptom. Demos, agreements and revenue stay in HubSpot.
- **Monthly pace:** discovery calls booked this month against a goal (default 12.5 per rep, from the 2026 plan's 2.5 Optimal deals a month at about 20% conversion; the plan calls this illustrative, so set the real number in Settings). It also estimates how many dials a day the goal needs at your last-90-day rate.
- **Weekly trend** for the last 8 weeks.
- **Which touches get responses:** every cadence step with how often it was done, how often the prospect responded on that touch, and which step produced the first response for each meeting. Steps with no responses after 30+ tries are flagged. This is the evidence for trimming email steps to stay under the email cap.
- **Live-answer rate by the prospect's local hour:** checks the call windows against your own dials. Outcomes imported from a run sheet are left out, because the app only knows when you imported them, not when you called.
- **By account size, Optimal score and persona:** reach and meeting rates per group. Account size splits Small, Prime (in two halves) and RFP, so you can see whether Prime accounts really book best.
- **Download KPI report (.xlsx)** with all of the above.

The **HubSpot CSV** now includes the playbook's custom properties as their own columns (Persona, Mid-sized, Higher-touch, Organized, Optimal score, Annual checks, Current provider, Renewal date, Trigger), so they map straight to HubSpot properties on import. On Today, emails to Optimal-3 accounts are tagged "personalize this one" (the playbook's 10 custom emails a day).

"Discovery booked" set from the Connected list, the status menu or bulk edit now records the date, so it counts in the right week.

## What the app does automatically

- **Time zone per contact** from the direct phone's area code, then the business phone, then the company state. You can override it.
- **Persona** from the job title, which picks the day-1 opener, voicemail and first email. Owners, COOs and CFOs get the "cost of a bad hire" opener (O, new wording for manager review) and the playbook's referral email, Sequence C ("who owns background checks?"), asking them to point you to the screening owner. Email 2 replies in the thread of whichever email 1 they got. Change any persona's choices on the Cadence tab. A company trigger (new HR leader, hiring surge, new state) switches to the trigger opener.
- **15-touch, 21-day cadence** (6 calls, 6 emails, 3 LinkedIn), counted in business days (or calendar days with weekend dates rolling to Monday, Cadence tab), cut short by the sprint exit (see "Sprint and nurture"). Old leads (with a last-contacted date or prior status) get a shorter re-engage track instead.
- **Contract renewals** (playbook slide 14, Sequence F): when a company has a renewal date in the next 90 days and nobody there is in a cadence, Today lists it with a button per contact. Contacts you've worked before get the re-engage track; new ones get the cold cadence. **Not now** hides it until the renewal date changes. Add renewal dates in the contact drawer under Company.
- **Restarting a cadence keeps history.** Earlier touches stay in the contact's history, the tracker and your KPIs.
- **Stops** a contact's cadence on a connect or reply, and **pauses** colleagues at the same company. When the sprint minimum is met (or the last step is done), the contact moves to nurture rounds; with the sprint exit off, it moves to Nurture with a 90-day revisit.
- **Max 2 active contacts per company** at once (change in Settings).
- **LinkedIn status.** LinkedIn touches log **Request sent** (connection requests) or **Message sent** (messages and voice notes), plus Accepted and Replied, and **Followed** (you followed them) and **Follow requested** (private profile). The contact card remembers where you stand (request sent, connected, following, follow requested), and you can update it there when a request is approved.
- **Discovery booked → HubSpot.** See "Getting leads into HubSpot" above.

## Not from the playbook (review with your manager)

- The re-engage track for old leads and its opener (marked in the Scripts tab). The renewal trigger for it is in the playbook (Sequence F); using it for old leads with no renewal date is not.
- The wording of opener O (cost of a bad hire). The playbook names the approach for executives but doesn't script it.
- The three emails that replace LinkedIn touches when there's no profile.
- The win-back track, its scripts and the closed-lost follow-up timing defaults.
- The sprint exit (3 calls, 3 emails, 1 LinkedIn message), the nurture rounds and their scripts (NR, VMN, "one idea" email), the steps added to re-engage and RFP check-in, inbound and referral leads ranking first, the "use your call blocks" dial target, and the "leads needed a week" estimate on KPIs → Leads added, the ramp-up start recommendation, and counting cadence days as business days.
- The average revenue per check (default $45) that turns estimated checks into dollars. The $10K–$150K prime range itself is from the playbook, and it now drives the Mid-sized green light.
