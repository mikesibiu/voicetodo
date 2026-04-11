# VoiceList — Setup & Hosting Guide

A voice-controlled list manager that syncs with Google Tasks.
Say "add milk to my shopping list" and it's done.

---

## What You Need
- A free GitHub account (github.com)
- A free Google Cloud account (console.cloud.google.com)
- Chrome browser on your Android phone

---

## STEP 1 — Host the App on GitHub Pages (Free)

1. Go to **github.com** and sign in (or create a free account)
2. Click the **+** button → **New repository**
3. Name it `voicelist` — keep it public — click **Create repository**
4. Click **uploading an existing file**
5. Upload ALL the files from this folder:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `icons/icon-192.png`
   - `icons/icon-512.png`
6. Click **Commit changes**
7. Go to **Settings → Pages → Branch → main → Save**
8. Your app URL will be: `https://YOUR-USERNAME.github.io/voicelist`

---

## STEP 2 — Set Up Google Tasks API

1. Go to **console.cloud.google.com**
2. Click **Select a project → New Project** → name it "VoiceList" → Create
3. Go to **APIs & Services → Library**
4. Search **Tasks API** → click it → click **Enable**
5. Go to **APIs & Services → Credentials**
6. Click **Create Credentials → OAuth 2.0 Client ID**
7. If prompted, configure the consent screen first:
   - User type: **External** → Create
   - App name: VoiceList
   - Support email: your email
   - Click **Save and Continue** through the rest
8. Back in Credentials, click **Create Credentials → OAuth 2.0 Client ID**
9. Application type: **Web application**
10. Name: VoiceList
11. Under **Authorized JavaScript origins** click **Add URI** and add:
    `https://YOUR-USERNAME.github.io`
12. Click **Create**
13. Copy the **Client ID** (looks like: 123456789.apps.googleusercontent.com)

---

## STEP 3 — Connect the App

1. Open `https://YOUR-USERNAME.github.io/voicelist` in Chrome on your phone
2. Paste your Client ID into the setup screen
3. Tap **Connect to Google Tasks**
4. Sign in with your Google account when prompted
5. Done!

---

## STEP 4 — Install as App on Android

1. In Chrome, tap the **three-dot menu** (top right)
2. Tap **Add to Home Screen** (or "Install App")
3. Tap **Add**
4. VoiceList now appears on your home screen like any other app

---

## How to Use

Just tap the microphone and say:
- **"Add milk to my shopping list"**
- **"Add eggs to groceries"**
- **"Put flour on the baking list"**
- **"Add dentist to my appointments list"**

If the list doesn't exist yet, VoiceList creates it automatically.
Your lists sync instantly and appear in the Google Tasks app too.

---

---

## OPTIONAL — Add Alexa Voice Control via Easy Task

Easy Task is a free Alexa skill that connects directly to Google Tasks. Once set up, you can tell Alexa to add items to your lists and they appear instantly in VoiceList — and vice versa. It's the closest thing to how Alexa used to work with Any.do.

### Step 1 — Enable the Easy Task Skill

1. Open the **Alexa app** on your phone
2. Tap **More → Skills & Games**
3. Search for **"Easy Task"**
4. Tap **Enable to Use**
5. Sign in with the **same Google account** you used for VoiceList
6. That's it — Easy Task now reads and writes your Google Tasks lists

Alternatively, find it directly at:
`https://www.amazon.com/dp/B0DM1RC2LZ`

### Step 2 — Using Easy Task with Alexa

**Add an item to a specific list:**
> "Alexa, ask Easy Task to add milk to my Shopping list"
> "Alexa, ask Easy Task to add dentist appointment to my Work list"

**Create a new list:**
> "Alexa, ask Easy Task to create a Garage list"

**View what's in a list:**
> "Alexa, ask Easy Task to open my Shopping list"
> "Alexa, ask Easy Task to show my Work list"

**See what's due today:**
> "Alexa, ask Easy Task what is due today"

**Complete a task:**
> "Alexa, ask Easy Task to complete milk"

### Important: List Name Matching

Easy Task requires you to say the **exact list name** as it was created. It does not fuzzy-match the way VoiceList does on your phone.

**Example:** If your list is called "Groceries," say "Groceries" — not "grocery list" or "shopping."

**Tip:** Keep your list names short and consistent so there's nothing to guess:
- Shopping ✓
- Work ✓
- Home ✓
- Appointments ✓

If you create a list via Alexa ("create a Garage list"), use exactly "Garage" every time afterward.

### Free vs PRO Version

The free version covers everything you need for daily use:
- Add tasks to specific lists ✓
- Create new lists ✓
- View lists and tasks ✓
- Mark tasks complete ✓

The PRO version (paid) adds recurring tasks, Alexa reminders, resetting lists, and searching tasks by name. Most users won't need PRO.

### How VoiceList and Easy Task Work Together

Both tools connect to the same Google Tasks account, so they share the same lists automatically:

- Add "milk" via Alexa in the kitchen → see it in VoiceList on your phone
- Add "paint" via VoiceList on your phone → Alexa can read it back to you
- Check things off in the Google Tasks app → both Alexa and VoiceList reflect the change

Think of Google Tasks as the shared database, and VoiceList + Easy Task as two different voice-controlled front doors into it.

---

## Troubleshooting

**"Microphone permission denied"**
→ Go to Chrome Settings → Site Settings → Microphone → Allow for your site

**"Sign-in error"**
→ Make sure your app URL is in the Authorized JavaScript Origins exactly as shown

**Lists not loading**
→ Tap the refresh icon (↺) in the top right of the lists section

**Voice not working**
→ Must use Chrome browser — voice recognition doesn't work in other browsers
