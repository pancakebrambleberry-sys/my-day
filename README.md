# pbb-day

**A calm, one-page planner for your day.** Reminders, money, workouts, mood and a thought dump, all in one place that opens in your browser. It's free, has no ads, and works on your phone and laptop.

<p align="center">
  <img src="images/day-view.png" alt="Day view with reminders, Coming up, workout, water tracker, mood, workout streak calendar, quote and focus timer" width="860">
</p>

## What is it?

pbb-day is a personal dashboard made of one web page (`index.html`). Open it, tick off what you did today, log how you feel, and see how your week and month are going. There's nothing to install and nothing to pay for. Put it on your phone's Home Screen and it opens like an app.

## What can it do?

| | |
|---|---|
| **Daily reminders** | Your own checklist for the day, such as meds, stretching, feeding the pet or clearing your inbox. Each one has a time and turns "due" when it's late. |
| **Workout plan + streak** | A workout set for each weekday that shows up on its day. Mark it done and a monthly calendar fills in, with a weekly streak. |
| **Rest and sick days** | Mark a day off with one tap. It never counts against your streaks or your recap. |
| **Weekly and monthly recap** | On the Week and Month views, a summary of reminders, workouts, water, mood, thoughts and (monthly) money, compared with the last week or month. It is worked out from your own entries, with no AI. |
| **Water tracker** | Tap to log up to 8 glasses a day. |
| **Coming up** | Add something for a future date. Tick it off when done; if you miss it, it stays and turns red as overdue. |
| **First-time welcome** | New people answer a few quick questions (name, currency, paydays, salary) so they start with their own numbers. To try it again without touching your data, add `#welcome` to the link (preview only, nothing is saved). **Backup → Start over** signs out and returns to the welcome page. |
| **Money tracker** | One or two paychecks a month, each with its own salary, bills and payday date (the 10th and 25th to start, change them any time). Pick your own currency symbol, and set the second payday to 0 if you are paid once a month. It shows the **% of your salary left after bills**. |
| **Mood tracker** | Tap how you feel in the morning, afternoon and evening. It shows a summary for the day, week and month. |
| **Thought dump** | Get things out of your head and find them later. An optional **Unhinged truth card** gives a playful, private summary of your day, week or month. It uses only your own words and runs in your browser. |
| **Quote + focus timer** | A short motivating quote that changes every few hours, plus 15, 25 and 50 minute focus timers. |
| **Day, Week, Month** | See one day, the whole week, or the month at a glance. |
| **9 colors** | Yellow, Orange, Red, Pink, Purple, Maroon, Blue, Green and Gray. |
| **Password lock** | An optional password asked each time the page opens on that device. |
| **Share (view-only)** | With sync on, give friends a code. They press **View with code** and can look but not change anything. Money and thoughts are hidden unless you include them. |
| **Export and backup** | Download your thoughts as a spreadsheet file with the date and time of each one, or save a full backup file and restore it later. |
| **Sync** | Optional Google sign-in saves your data to the cloud, so your phone and laptop match. |

<p align="center">
  <img src="images/phone.png" alt="Phone view" width="260">
  &nbsp;&nbsp;
  <img src="images/themes.png" alt="The nine color themes" width="560">
</p>

<p align="center">
  <img src="images/welcome.png" alt="The first-time welcome screen" width="360">
</p>

<p align="center">
  <img src="images/truth-card.png" alt="The Unhinged truth card, a playful summary of your thought dump" width="760">
  <br><br>
  <img src="images/recap.png" alt="The weekly recap card on the Week view" width="760">
</p>

<p align="center">
  <img src="images/paycheck-settings.png" alt="Paycheck settings: currency, one or two paychecks, and payday dates" width="760">
</p>

## Who is it for?

- **People who like simple routines:** one place for the small daily things.
- **People with a salary paid twice a month:** see right away how much is left after bills.
- **People building a workout habit:** a plan for each day and a streak that rewards showing up.
- **People who want to track their mood** without a heavy journaling app.
- **People managing ADHD or a busy brain:** short checklists, a thought dump and a focus timer.
- **Students and workers** who want a free planner they can fully customize.
- **Anyone who wants their own copy:** it's one file you can change and host for free.

It is not a medical or financial tool. It helps you keep track, and it doesn't give advice.

<p align="center">
  <img src="images/week-view.png" alt="Week view" width="420">
  &nbsp;
  <img src="images/month-view.png" alt="Month view" width="420">
</p>

---

## Option 1: Just use it

Open the link, press **Theme** to pick a color, and start. Sign in with Google to save your data to the cloud and see it on your other devices.

If you use the original link, your data is stored in the owner's Firebase project. Other users can't see it through the app, but the owner can see it in their Firebase console. If you want your data to be fully yours, use Option 2 or 3.

---

## Option 2: Your own copy, no Firebase needed

Firebase is **not required**. Without it, the page works fine but saves only in the browser on that one device. There is no sign-in and no sync between your phone and laptop. Clearing your browser's site data erases it.

1. Make a free account at github.com.
2. Open this repo and press **Fork** (top right). This copies it to your account.
3. In your copy, open `index.html`, press the pencil icon, and find the block that starts with `const FIREBASE_CONFIG={`. Change it to:
   ```js
   const FIREBASE_CONFIG={ apiKey:"", authDomain:"", projectId:"", appId:"" };
   ```
   An empty `apiKey` turns the cloud features off. Press **Commit changes**.
4. Go to your copy's **Settings → Pages**. Under "Build and deployment", choose **Deploy from a branch**, branch **main**, folder **/ (root)**, and press **Save**.
5. After a minute or two, your page is live at `https://YOUR-USERNAME.github.io/REPO-NAME/`.

If you skip step 3, your copy will still point at the original owner's Firebase. Always replace that block.

---

## Option 3: Your own copy with cloud sync (Firebase)

This gives you Google sign-in and syncing across your phone and laptop, with the data in your own account. It's free on Firebase's Spark plan.

1. Do steps 1 and 2 from Option 2. Don't change the config yet.
2. Go to **console.firebase.google.com** and sign in with a Google account.
3. Press **Create a project**, name it, and finish the wizard. Google Analytics is optional and can be off.
4. On the project home, press the **web icon `</>`** to add a web app. Give it any nickname. Don't tick "Firebase Hosting". Press **Register app**.
5. Copy the values shown in `firebaseConfig`: `apiKey`, `authDomain`, `projectId`, `appId`.
6. In `index.html` on GitHub, replace the config block with your values:
   ```js
   const FIREBASE_CONFIG={
    apiKey:"...",
    authDomain:"...",
    projectId:"...",
    appId:"..."
   };
   ```
   Press **Commit changes**.
7. In Firebase, go to **Build → Authentication → Get started → Sign-in method**, choose **Google**, turn it on, pick a support email, and **Save**.
8. Go to **Build → Firestore Database → Create database**. Pick a location near you (it can't be changed later), choose **Production mode**, and press **Create**.
9. Open the **Rules** tab in Firestore, replace everything with the rules below, and press **Publish**:
   ```
   rules_version = '2';
   service cloud.firestore {
     match /databases/{database}/documents {
       match /users/{uid}/{document=**} {
         allow read, write: if request.auth != null && request.auth.uid == uid;
       }
     }
   }
   ```
   These rules let each signed-in person read and write only their own data.
10. Go to **Authentication → Settings → Authorized domains → Add domain** and add `YOUR-USERNAME.github.io`.
11. Turn on GitHub Pages as in step 4 of Option 2. Open your page and sign in with Google.

The keys in the config are not secrets. Anyone can see them in the page. The security rules from step 9 are what protect your data.

---

## Colors

Press **Theme** at the top of the page and choose Yellow, Orange, Red, Pink, Purple, Maroon, Blue, Green or Gray. The choice is saved with your data.

To add your own color, find the `THEMES` list in `index.html`, copy one entry, give it a new name, and change its color codes.

## Try the welcome page

New people see a short welcome page the first time they open the app. To try it yourself without touching your own data, open the link with `#welcome` on the end:

`https://pancakebrambleberry-sys.github.io/my-day/#welcome`

1. You see the welcome page with a yellow bar at the top saying it is a preview.
2. Answer the questions (name, currency, one or two paychecks, payday dates, salary, example bills) and press **Start**, or press **Skip for now**.
3. You land on the dashboard with your answers, and the yellow bar stays. Nothing is saved or synced, and your real data is not touched.
4. If you refresh the page, you go back to a blank welcome page. Every preview starts fresh.
5. Press **Exit preview** to go to the normal app. The answers you typed in the preview are not carried over.
   - On a device you already use, you see your own dashboard, just as you left it.
   - On a device that has never opened the app, you see the real welcome page, and this time your answers are saved when you press **Start**.
6. To go back to the real welcome page on a device you already use, open **Backup**, go to **Start over** at the bottom and confirm. This clears that device. If you are not signed in with Google, download a backup first.

## Coming up (things that happen on a certain date)

Press **+ Add** on the small **Coming up** card, type what it is (a dentist visit, a birthday, a bill) and pick the date. It shows the date next to each item.

- Tick the box when it's done. It gets crossed out, and you can untick it if you change your mind.
- Anything you haven't ticked stays in the list. If the date has passed it turns red and says **overdue**, so nothing gets forgotten.
- Ticked items disappear the next day.
- The card shows on every day you browse, three items at a time, with a "+ more" button.

## Password lock

Press **Set password** to ask for a password each time the page opens on that device. It's a privacy screen, not strong security.

## Sharing a view-only copy

This needs Option 3 (Firebase). Sign in, press **Share**, pick a code (6+ characters) and choose whether to show money and thoughts. After you start sharing, press **Copy link** and send it. Friends who open that link see your dashboard right away. You can also send `…/my-day/#view`, which asks them for the code as soon as it opens. They can also open the normal page, press **View with code** and type it. Nothing is remembered on their device, and they can't edit anything.

Add this to your Firestore rules, next to the `users` rule, then press Publish:

```
match /shares/{id} {
  allow get: if true;
  allow create: if request.auth != null && request.resource.data.owner == request.auth.uid;
  allow update: if request.auth != null && resource.data.owner == request.auth.uid && request.resource.data.owner == request.auth.uid;
  allow delete: if request.auth != null && resource.data.owner == request.auth.uid;
}
```

Note: anyone with the code can see what you chose to share, so use a code that is hard to guess. Press **Stop sharing** to turn it off.

## What's new

See [CHANGELOG.md](CHANGELOG.md) for every update that has been made.

## FAQ

**Is there a task bar I can reset every day, just for daily tasks?**
Kind of. The **Daily reminders** card is your daily checklist: you add things like stretching, water or a workout, tick them off, and they reset on their own every day. **Coming up** handles things with a date, like a dentist visit or a bill. There is no big to-do list or task manager, on purpose. I want pbb-day to stay calm and uncluttered, more of a daily check-in than another app full of tasks. I also still write my everyday tasks in a notebook, because I like writing them by hand. The app is for the gentle things around that: reminders, routines, mood, money and a place to dump thoughts. If you want a full task list, the code is open, so you can add one to your own copy.

**Does it cost anything?**
No. The page is free to use, and a personal copy fits comfortably in Firebase's free plan.

**Where is my data stored?**
On your device. If you sign in with Google, it is also saved to the cloud so it syncs between your phone and laptop. On the shared link, that cloud is the Firebase project of whoever runs the app, so if you want full control of your data, make your own copy (Option 3). You can also download a full backup or export your thoughts any time from the **Backup** panel.

**Do I have to sign in?**
No. Without signing in, everything is saved on that one device only. Sign in with Google if you want it on more than one device.

**Do I need a password?**
No, the lock is optional. If you set one, it only applies to the device where you set it.

**Can someone see my dashboard without being able to change it?**
Yes. Press **Share** to get a view-only link. Money and thoughts stay hidden unless you include them, and **Stop sharing** switches it off.

**What if I skip a day because I'm resting or sick?**
Press **Rest day** or **Sick day** on that day. It does not break your streak or count against your recap.

## Tips

- On iPhone: open the page in Safari, then Share → **Add to Home Screen**.
- Tap **My Day** at the top left to reload the latest data.
- Reminders, bills and workouts are all editable on the page.
