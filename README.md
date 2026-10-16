# 🛡️ CompTIA Security+ 60-Day Tracker

> **60 days. 28 sections. 13 practice exams. One very satisfying confetti cannon.** 🎉

A gamified study tracker for the **CompTIA Security+ (SY0-701)** exam. It turns the Dion Training 60-day study plan into a daily mission board that **celebrates every check**, shows exactly what to study next, and tells you which exam topics are still holding you back.

No frameworks, no build step, no sign-up. Open it, tick a box, hear the *ding*, and watch the progress ring fill. ✨

**🔗 Live app:** `<add your live URL here>`

---

## 👀 Why this exists

Studying for a certification is a marathon, and motivation is the first thing to run out. Plain checklists are boring and spreadsheets don't cheer for you. This tracker makes progress **visible, rewarding and impossible to lose track of**, so all you have to do is show up for the next day.

---

## ✨ Features

### 🗓️ A study plan you can actually follow
- **60 days, 6 milestones:** 🧱 Foundations → 🧠 Core Concepts → 🚀 Advanced Topics → 🏁 Course Complete → 🎯 Practice Warrior → 🏆 Exam Ready
- **Real topic names:** every day shows its course section, such as *"Section 7: Data Protection"*
- **Lecture-level dropdowns:** open a day and tick off each lecture, plus the section checkpoint quiz. The "Watch" task completes itself when every lecture is done
- **Specific daily tasks:** notes, flashcards for that day's key terms, a self-test, and a review of yesterday's cards

### 🎮 Progress that feels good
- **Animated progress ring** and a **60-day journey map** that fills with colour as you go
- **Confetti** on every check, a bigger burst for each finished day and a full fanfare for each milestone
- **Unlockable milestone badges** with a reward you set yourself (🍕 pizza, anyone?)
- **Streak counter** 🔥 that counts consecutive study days
- **Different sounds** for check, uncheck, day complete and milestone unlocked, plus an on/off switch

### 📅 Dates that adapt to you
- Set a **start date** and the **finish date** fills itself in. Set the finish date and the start date follows. Either way, the plan is 60 days
- Each day card shows its **real calendar date**
- **Smart schedule messages:** *"Starts in 3 days"*, *"2 days ahead"*, or *"Finish Section 7: Data Protection today"*. Starting late is never counted as "behind"
- **Exam countdown** and a **days-to-finish** counter

### 📈 Practice exam tracker
- Log each score as a **percentage or out of 900**, and see a trend line against the pass mark (about 83%, or 750/900)
- Tap the **exam objectives you missed** (all 28, from 1.1 to 5.6), grouped by domain
- A **weak-topics heatmap** ranks your most-missed objectives, tagged with their domain (D1 to D5), with expandable domain dropdowns and an **Expand all / Collapse all** button
- A **notes box** on every day, which doubles as your brain dump

### ⏱️ Focus timer
- A **circular dial** you can drag, scroll or arrow-key from **1 to 120 minutes**
- A satisfying **analog "tick"** for every minute, with a heavier click every 5
- Quick presets, an alarm when time is up and an automatic 5-minute break

### ☁️ Sync across devices
- **Real-time sync** through Firebase Realtime Database. Tick a box on your laptop and it appears on your phone seconds later
- Offline friendly: changes are saved locally and sync when you're back online
- Light and dark mode, **backup code** export and restore, and a mobile-friendly layout

---

## 🗺️ The 60-day roadmap

| Milestone | Days | What you do |
|---|---|---|
| 🧱 **Foundations** | 1–10 | Sections 1–9: security basics to risk management |
| 🧠 **Core Concepts** | 11–20 | Sections 10–17: vendors, governance, architecture, IAM |
| 🚀 **Advanced Topics** | 21–30 | Sections 18–26: attacks, hardening, incident response, automation |
| 🏁 **Course Complete** | 31–33 | Security awareness, readiness assessment, one well-earned rest day |
| 🎯 **Practice Warrior** | 34–46 | One practice exam every day |
| 🏆 **Exam Ready** | 47–60 | Daily retakes until the answers are second nature |

---

## 🚀 Quick start

The app is a single static page, so there is nothing to install.

```bash
git clone https://github.com/rafaelsatriabhi/comptia-secplus-tracker.git
cd comptia-secplus-tracker
# open public/index.html in your browser, or serve it locally:
npx serve public
```

Your progress is saved in your browser automatically.

---

## ☁️ Turn on cloud sync (optional)

1. Create a **Firebase project** with a **Realtime Database**.
2. Set the database rules so each device needs a secret code to read or write its own data:
   ```json
   {
     "rules": {
       ".read": false,
       ".write": false,
       "trackers": {
         "$code": {
           ".read": true,
           ".write": true,
           ".validate": "newData.hasChild('u')"
         }
       }
     }
   }
   ```
3. Put your database URL in the app's `FB` constant.
4. In the app, open **Settings → Cloud sync** and tap **New code**.
5. On your other devices, paste the same code and tap **Connect**.

> 🔐 **Keep your sync code private.** It is the only key to your progress and notes. Anyone who has it can read and change that data.

---

## 🧰 Project structure

```
comptia-secplus-tracker/
├── public/            # The app (index.html)
├── .github/workflows/ # GitHub Actions: automatic deploys
├── firebase.json      # Firebase Hosting configuration
├── .firebaserc        # Firebase project alias
└── package.json       # Tooling (Prettier for formatting)
```

Format the code with `npx prettier --write public/index.html`.

## 🌍 Deploy

Pushes to the main branch can deploy automatically through GitHub Actions to Firebase Hosting. To deploy by hand:

```bash
npm install -g firebase-tools
firebase login
firebase deploy
```

---

## 🔬 Under the hood

- **Plain HTML, CSS and JavaScript** in one file, with no build step
- **Web Audio API** for every sound effect, so there are no audio files to load
- **Canvas** confetti and **SVG** charts, the progress ring and the timer dial
- **localStorage** for instant local saves, with **Firebase Realtime Database** (REST and server-sent events) for sync. The newest change wins
- Dark mode and responsive layout built in

---

## 🔒 Privacy

There are no accounts, no analytics and no tracking. Without cloud sync, your data never leaves your browser. With sync on, it lives only under your secret code in your own Firebase database.

---

## 🙏 Credits and disclaimer

- Study schedule adapted from the **Dion Training** CompTIA Security+ (SY0-701) 60-day study plan.
- This is an independent, unofficial study aid. It is **not affiliated with or endorsed by CompTIA or Dion Training**. *CompTIA Security+* is a trademark of CompTIA, Inc.

---

## 🤝 Contributing

Found a bug or have an idea, such as more sounds, new badges or other certification plans? Open an issue or send a pull request. Contributions are welcome. 💙

**Built by [@rafaelsatriabhi](https://github.com/rafaelsatriabhi)** to turn exam prep into something you actually look forward to.

<p align="center"><b>Now go tick that first box.</b> ✅ 🎆</p>
