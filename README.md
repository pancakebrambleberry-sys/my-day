# pbb-day

A personal day planner that runs in your browser. It has daily reminders, a finance tracker for two paydays (with "% left after bills"), a weekly workout plan with a workout streak calendar, a mood tracker, a thought dump, a motivational quote, a focus timer, and Day / Week / Month views. There are nine color themes and an optional password lock.

It is one file (`index.html`), so you can host it for free on GitHub Pages.

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

## Password lock

Press **Set password** to ask for a password each time the page opens on that device. It's a privacy screen, not strong security.

## Tips

- On iPhone: open the page in Safari, then Share → **Add to Home Screen**.
- Tap **My Day** at the top left to reload the latest data.
- Reminders, bills and workouts are all editable on the page.
