# Medicine-Cabinet-

**The Medicine Cabinet** is a household medication management tool I built to solve a recurring problem in my own home — keeping track of daily medications for my parents, who take multiple tablets and syrups across morning, afternoon, and evening, and ensuring nothing runs out unexpectedly. Existing medication apps reminded users about individual medicines one at a time, but none of them solved the real coordination problem: when you order five different medicines together, each with different strip sizes and consumption rates (a 2×5 strip of 10 tablets lasts a different number of days than a 3×5 strip of 15), they all run out on different days. The app's core feature is a **batch reorder algorithm** that calculates the optimal single date to reorder everything as one bulk order, eliminating last-minute panic refills and pharmacy trips.

Built as a single self-contained HTML file that runs entirely in the browser with no backend or accounts required, the app is installable on Android phones as a Progressive Web App through Chrome, giving it a proper home screen icon and full-screen native-app feel. All data is stored locally on the device using browser storage, ensuring complete privacy — no medical information ever leaves the phone. The interface uses a calm, apothecary-inspired aesthetic with a Fraunces serif paired with Inter sans-serif, emerald and amber accents on a warm cream background, designed to feel reassuring rather than clinical for daily medication routines.

Key features include **person tabs** that let multiple family members (Mom, Dad, or any custom person) have their own filtered view of medicines and reorder dates, while also showing a combined household batch date when viewing "All." The app supports both **tablets and syrups** with appropriate units (tablets per strip vs. milliliters per bottle), automatically deducting stock when doses are marked taken — pulling from loose tablets/opened bottles first before opening a new strip or bottle. **One-tap dose buttons** at the top let users mark all morning, afternoon, or evening medicines as taken simultaneously, rather than tapping each medicine individually. An **automatic dose logging system** records every taken dose with a timestamp, and intelligently detects missed doses based on time windows — if morning medicines aren't taken by 12 PM, afternoon by 5 PM, or evening by midnight, they're auto-flagged as missed in the history without any manual input. Late doses taken after their cutoff are correctly marked as "late" rather than "on-time." Additional features include **per-medicine notes** (for instructions like "take with food"), customizable **reorder buffer days** so users decide how many days of safety margin to keep, **browser notifications** at 8 AM, 2 PM, and 8 PM for dose reminders plus reorder alerts, and **export/import backup** functionality so users can save a JSON snapshot of their complete data — medicines, people, and full dose history — to Google Drive or email for safekeeping or transferring to a new device.

The project is intentionally local-first and minimal: no servers, no subscriptions, no telemetry, no advertisements, no account creation. It exists to solve one family's problem well, and is open enough that anyone can fork the HTML and adapt it for their own household.


**How to Use The Medicine Cabinet**

**Setup (one-time, takes 5 minutes)**

1. Open the app URL in Chrome on your Android phone.
2. Tap Chrome's three-dot menu → **Install app** (or **Add to Home screen**). The app icon appears on your home screen.
3. Open the app from the home screen icon.
4. Tap **Enable** on the notification bar at the top to allow daily reminders. Allow when Android prompts.
5. The app comes with two default person tabs — **Mom** and **Dad**. To add more people (a child, grandparent, yourself), tap the **+** icon at the end of the tab row and enter a name.

**Adding your medicines**

6. Tap the green **+ Add Medicine** button at the bottom.
7. Fill in:
   - **Name** — e.g. "Metformin 500mg" or "Cough Syrup"
   - **For whom** — select Mom, Dad, or any person you've added
   - **Type** — choose Tablet or Syrup
   - For tablets: enter strips in stock, tablets per strip (10 for 2×5, 15 for 3×5), any loose tablets, and morning/afternoon/evening doses
   - For syrups: enter bottles in stock, ml per bottle, ml left in any opened bottle, and morning/afternoon/evening doses in ml
   - **Notes** (optional) — e.g. "Take with food," "Shake well"
   - **Reorder buffer days** — how many days before running out you want to be reminded (default is 5)
8. Tap **Save**. The medicine appears in the inventory.
9. Repeat for every medicine in your household.

**Daily use**

10. At the start of each day, open the app. The three large buttons at the top show how many morning/afternoon/evening doses are pending.
11. After Mom takes her morning meds, tap the **Mom** tab → tap the big **Morning** button. All her morning medicines are marked taken in one tap, stock is automatically deducted, and a log entry is recorded.
12. Repeat for afternoon and evening as doses are taken.
13. If only some medicines were taken (say Dad took his BP tablet but not his vitamin), use the individual dose buttons on each medicine card instead of the big "take all" button.

**Checking the reorder schedule**

14. The **batch reorder card** below the dose buttons shows the next date you need to place an order. On the "All" tab it shows the combined household date plus a breakdown for each person individually.
15. When the card turns amber, reorder is within a week. When it turns red, reorder today.
16. Place your bulk order on or before that date and update the stock in the app afterward (tap the pencil icon on each medicine to add the new strips/bottles).

**Reviewing history**

17. Tap **View Logs** (next to the item count in the Inventory header) to see complete dose history grouped by date.
18. Each day shows counts of on-time, late, and missed doses. Filter by person using the buttons at the top of the log view.
19. Doses not taken before their cutoff time (12 PM for morning, 5 PM for afternoon, midnight for evening) are automatically marked as missed — no manual action needed.

**Backup (recommended weekly)**

20. Scroll to the bottom of the app and tap **Export backup**. A JSON file downloads to your phone.
21. Save it to Google Drive, email it to yourself, or send via WhatsApp to yourself. This is your safety net if the browser data ever gets cleared.
22. To restore on a new device or after a clear, tap **Import backup** and select the JSON file.

**Recommended companion setup**

23. In addition to the app's notifications, set three repeating alarms on your phone's native clock app — 8 AM, 2 PM, 8 PM — labeled "Morning meds / Afternoon meds / Evening meds." Native alarms are more reliable than browser notifications on aggressive battery-saving phones, and combining the two gives the most foolproof reminder system.

---
