# Changelog

Every improvement to pbb-day is listed here, newest first. Each entry says what changed and why it helps.

## Nov 23, 2026

### Added
- **Rest day and sick day.** On the Day view, under the greeting, press **Rest day** or **Sick day** to mark that day off (press **Undo** to change your mind). A day off is not counted against you: your workout streak keeps going, a week where every workout day was off is skipped instead of breaking the streak, and the reminder, workout and water averages in the weekly and monthly recap leave that day out. The recap shows how many days were off, and the Week and Month views mark them as "off".
- **Weekly and monthly recap.** A new card at the top of the Week and Month views that sums up the period: how many reminders you finished (with your best day and most skipped one), workouts done out of planned, average water, average mood with your best and toughest day, how many thoughts you dumped and, for the month, what's left after bills. Each line compares with the previous week or month, and it names your weakest spot. It is worked out from your own entries in the browser, with no AI and no extra cloud use. The money and thoughts lines are hidden in view-only shares when you leave those out.
- **Start over.** Open **Backup** and press "Sign out and go back to the welcome page". It asks you to confirm, then clears this device and shows the welcome page again. If you were signed in, you are signed out, and your data stays safe in your Google account, so signing in again brings it back. Without Google, it warns you to download a backup first.
- **Try the welcome page again (preview link).** Opening the app with `#welcome` on the end of the link always shows the welcome page, even on a device that already has data. A yellow bar says it's a preview, nothing you type is saved or synced, and your own data is not touched. "Exit preview" goes back to the normal app.
- **Water tracker.** A small card under Today's workout with eight glasses. Tap a glass to fill up to it, and tap the last filled glass to take one back. Each day starts at zero, and it works on any day you browse.
- **Coming up.** A small card for things that happen on a certain date, like a dentist visit or a birthday. Type what it is, pick the date and press Add. Each item shows its date and has a tick box: tick it when it's done and it is crossed out, untick it to undo. Anything you haven't ticked stays in the list, and once its date has passed it turns red and says "overdue", so nothing gets forgotten. Items you ticked disappear the next day. It shows on every day you browse, three items at a time with a "+ more" button, and the add form opens only when you press "+ Add".
- **First-time welcome.** A new person is asked for their name, currency, how often they are paid, payday dates and salary before the dashboard opens, so they start with their own numbers, not example figures. They can skip it, or press "Have a code?" to view a shared dashboard. People who already have data are never asked, and a new device that signs in to an existing account loads the cloud data instead of starting blank.
- **Share a view-only copy.** Press **Share**, and friends can see your dashboard but not change it. You get a link with the code inside, and friends can also open the `#view` link and type the code. Money and thoughts are hidden unless you include them. **Stop sharing** switches it off.
- **Unhinged truth card.** A playful summary of your thoughts for the day, week or month. It uses only your own words and runs in your browser. If your thoughts sound heavy, it shows a kind message instead of a joke.
- **Export thoughts.** Download your thoughts as a spreadsheet file with the date and time of each one.
- **Backup and restore.** Save a full backup file and load it back later.
- **Currency dropdown:** ₱, $, €, £, ¥, ₹, ₩ and RM.
- **Paycheck settings.** Choose one or two paychecks a month, and set the payday dates yourself (set the second payday to 0 for none). Paydays on the 29th to 31st use the last day of shorter months.

### Changed
- **Tidier Day view on tablets.** On medium-width screens, Daily reminders now sits next to the mood card, and the small Coming up and workout cards sit side by side below, so the big empty block under them is gone.
- **Smaller workout card.** Today's workout still shows every exercise, but in a tight two-column list with smaller text, so it takes less room. It sits under Coming up in one column, and both cards are only as tall as their content, so the Day view is less crowded.
- The default reminders are now general: Stretch, Drink 8 glasses of water and Workout.
- Opening one top menu now closes the others. Esc closes them too.
- The password lock accepts a password with or without a stray space, and phone keyboards no longer capitalize or auto-correct the box.
- The README screenshots were retaken to show the current look.

## Earlier in November 2026

### Added
- Cloud sync with Google sign-in, so your phone and laptop match. It also works on one device with no sign-in.
- A greeting that uses your name.
- A logo, a tab title and iPhone Home Screen support (it refreshes when you open it).
- A workout calendar for the month with a weekly streak.
- Nine color themes.
- A password lock for each device.
- A README with pictures and setup guides.
