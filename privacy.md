# WorkoutSmith — Privacy Policy

**Effective date:** July 30, 2026
**Last updated:** 2026-08-15

---

## The short version

WorkoutSmith is a training app. It is built so that the things you would least want to leak — your workouts, your body, your sleep, your heart rate, where you live — stay on your iPhone.

- **Your training history and health data live on your phone**, in the app's own storage. There is no account required to use them, and they are not uploaded to us.
- **We run one server**, and it exists only for the social features: signing in, your friends list, challenges, leagues, and trophies. It holds your name, a handle, an avatar id, an unreadable fingerprint of your email address so friends who know it can send you a request, and the numbers for the specific metrics you chose to compete on. Nothing else.
- **We do not run ads, we do not use analytics or crash-reporting SDKs, and we do not track you.** There is no advertising identifier in this app and no third-party code that could collect one.
- **We do not sell your data. We never have and there is no mechanism in the app that could.**
- **The AI coach is optional.** When you use it, a summary of your training goes to Google or Anthropic. What is in that summary is listed in full below. Normally you bring your own API key and it is billed to your own account; there is also a capped shared option for people who have no key, where the same request is billed to ours instead. Both are described below.
- **You can delete everything**, from inside the app, without emailing anyone.

The rest of this document is the detail behind those sentences.

---

## Who this policy is for and who we are

This policy covers the WorkoutSmith iPhone app (bundle id `com.mig1278.aiworkout`) and its home-screen widget.

WorkoutSmith is published by Michael Lee, an individual developer based in
Massachusetts, USA. For privacy questions or requests, email
**mignet1278@gmail.com** — it is read by the developer personally.

---

## Where your data lives

There are only three places your data can be, and it is worth being precise about which is which, because the differences matter.

**1. On your iPhone.** This is where almost everything is. Your profile, your programs, every workout you have logged, every set, your chat history with the coach, your settings, your XP and achievements, and your saved home coordinate. This storage is local to the device. It is not synced to iCloud by the app, and there is no CloudKit configuration in the app — if you restore a new phone from an iPhone backup your data comes back through Apple's backup, not through us.

**2. On our server.** A single database in Amazon Web Services (region: US East, Northern Virginia). It holds only what the social features need. The complete list is in "What we store on our server" below. It does **not** hold your workout history, your programs, your chat with the coach, your sleep, your heart rate, your weight, or your home location.

**3. In accounts with other companies.** If you use the AI coach with your own Google (Gemini) or Anthropic (Claude) API key, those requests are billed to and governed by your account with that company, and we are not the account holder. If instead you use the shared coach, the request goes to the same place but on our account rather than yours — see "The shared coach" below. If you connect Fitbit, your phone talks to Google directly (Google owns Fitbit and now provides its data to apps) using your own Google login. In every case, those companies' privacy policies apply to what they do with what they receive.

---

## What stays on your device and never leaves it

The following are stored on your iPhone and are not transmitted to our server, to the AI coach, or anywhere else:

- Your full workout history: every exercise, set, rep, weight, RIR, warm-up, and rest.
- Your programs, whether AI-generated or hand-built.
- Your entire chat and voice conversation history with the coach. Our server keeps no conversation state; the transcript exists only in the app's local database.
- Your injuries, goals, experience level, and equipment notes, except where they are included in a coach request (see the AI coach section — this is the one exception, and it is under your control).
- Your birth year, biological sex, and hand-entered bodyweight. These are optional, used only for local strength-standard tables, and are sent nowhere.
- Sleep duration, resting heart rate, and heart rate variability. These are read from Apple Health or Fitbit, converted into a single readiness score on the device, and the underlying readings are never transmitted. Not to us, not to the AI.
- The training profile the app builds about you. From your logged workouts alone, the app works out how you train: what you have shown you can lift on each exercise, how reliably your reps-in-reserve reports match what you then do, how often you make a prescribed weight increase, and which exercises you swap or skip. It is computed on your phone, stored on your phone, and never sent to our server. If you use the AI coach, a few sentences summarising it are included in the coach request — that summary is listed in the coach section below, and it is the only part of this that goes anywhere. Nothing here is asked of you: it is all counted from workouts you had already logged, and deleting your data deletes it with them.
- The change journal for a program a friend shared with you. When you adopt somebody else's program, your phone keeps a record of how each session actually went against how it was written — what you swapped, skipped, or re-targeted, and whether you or your AI coach made each change — together with an untouched copy of the program as it was originally sent to you. It is stored on your phone with the rest of your history and is not transmitted anywhere, with one exception you control: if you switch on share-back for that program, a summary of it is sent to the person who wrote it. That is described under "Programs shared between friends" below, it is off unless you turn it on, and turning it off deletes what they were shown.
- Your home coordinate for the Adventure journeys (see its own section below).
- Your AI provider key, your Fitbit tokens, and your sign-in tokens, which are held in the iOS Keychain.

---

## Apple Health

Apple Health is optional. The app works without it; you grant access from Settings, per category, and you can revoke it at any time in the iOS Health app.

**What the app reads.** When you grant access, the app asks for: step count, walking and running distance, cycling distance, heart rate, resting heart rate, heart rate variability, body mass, sleep analysis, and your workout history. Workout history is read across all sources, so workouts recorded by an Apple Watch or another app are included.

Two of these reads are broader than you might assume, and we would rather say so:
- The journey odometer on the Adventure tab reads your **entire lifetime** walking and running distance history, because the feature is built on your all-time mileage. That total is computed and displayed on the device and is not transmitted.
- Workout history is read across a two-year window to power the Endurance track.

**What the app writes.** When you finish a workout in the app, it saves that workout to Apple Health with its type, start time, and end time. It does not write a calorie estimate, because a set log does not support an honest one. It does not write distance, heart rate, steps, or body weight. If you delete a workout log in the app, the matching Health entry the app created is deleted too.

**Background access.** The app has no HealthKit background delivery and no observer queries. It reads Health only while you have it open.

**What leaves the device.** Health data leaves your phone in exactly two situations, both of which require an action from you:

*a) If you use the AI coach.* Three Health-derived values are included in the coach's context: today's step count, an average workout heart rate figure, and your Health-recorded body weight, plus your readiness score as a single 0–100 number. Full detail in the next section.

If you wear an Apple Watch with the WorkoutSmith watch app during a workout, one more value is included while that workout is running: your heart rate at that moment, as a single number. It is measured on the watch, sent to your iPhone, and held in memory for the length of the session — it is never written to the app's database, never uploaded to our server, and it is dropped from the coach's context as soon as it stops being current. It is the only reading in the app that describes your body right now rather than your training, and it is there because it is the one thing your phone cannot measure while it sits on the bench beside you.

*b) If you make an activity metric compete or share.* The app uploads daily totals for only the metrics you have opted in, and there are three ways to opt one in, all of them things you do on purpose:

- you **join a challenge** that races on that metric;
- you **enrol in a league** on that metric;
- you set that metric to **Friends** or **Global** on the sharing screen (Compete → the privacy button → "What you share").

The third of these covers the friends board: setting steps to Friends is what puts your weekly step total on the boards your friends see, and it is what causes those totals to be uploaded. Before this release, setting a metric to Friends changed who *could* see it but never caused anything to be uploaded, so the board stayed empty; the setting now does what it says.

If you have done none of the three for a metric, that metric is never even read, let alone uploaded. Setting a metric back to Private, leaving a league, or having a challenge end stops the uploads for it. The metrics are steps, walking+running distance, running distance, and running time. Steps and walking+running distance come from whichever activity source you chose, Apple Health or Fitbit, and are treated identically either way; running distance and running time always come from Apple Health. Uploads cover a rolling 35-day window so that totals stay correct if you were offline. What our server receives for these is a per-day figure, which over time forms a daily record of those activity totals for as long as you have an account.

Sleep, resting heart rate, heart rate variability, cycling distance, and your all-time journey mileage are never transmitted anywhere, under any setting.

---

## The AI coach

The coach is optional. The app is fully usable without it: manual logging, the hand-built program builder, progression, Adventure, and Compete all work with no AI configured.

**Your key, your account.** You supply your own API key from Google AI Studio (Gemini) or Anthropic (Claude). It is stored in your device's Keychain, marked so that it does not sync to iCloud Keychain and is not included in encrypted backups. It is never written to a log, never stored on our server, and never sent anywhere except as the authentication credential on your own coach requests.

**The shared coach, if you have no key of your own.** Settings offers a second option: use the coach without supplying a key. It is there so you can try the coach before deciding whether to go and get one, and it is the reason this app can be handed to an invited tester who has no Google account set up.

The difference is narrower than it sounds, and it is worth being exact about. It is not a different service and not a different destination: your message goes to the Google Gemini API either way, carrying the same context block listed below and nothing extra. **What changes is whose account the request is charged to.** With your own key, the request is billed to you and governed by your own agreement with Google or Anthropic, and we are not a party to it. With the shared coach, the request is billed to our Google account, and our agreement with Google covers it instead of yours. Google receives the same words in both cases; only the account name attached to them differs.

Because those requests spend our money rather than yours, they are capped, and the cap is deliberately tight. A signed-in account can send about sixty coach messages a day, where generating a whole program counts as five of them; without an account it is about eight. Past the cap the coach stops answering until the next day and tells you why. Keeping that count is the only thing the cap adds: a number, tallied against your account id or, if you are not signed in, your IP address, expiring on the same schedule as the rate-limit counters described just below. It records that a request happened, never what was in it.

Nothing else differs. On both paths the relay stores no conversation, logs no content, and holds no key after the request ends, and your training history stays on your phone.

The shared coach is a courtesy rather than a service, and the app says so where you choose it: it may be rate limited or switched off at any time. It only works at all while a real shared key is configured on the server, so on a build where none is, choosing it gets you an error instead of a coach. Either way the description above is what happens when it does work.

**How a request travels.** Your message goes over HTTPS to a small relay we run on AWS, which attaches the coaching instructions and forwards the request to Google or Anthropic — using your key, or ours if you chose the shared coach. The relay does not store your key: it exists in memory for the duration of that one request and is discarded. The relay keeps no conversation history.

**Nothing you write, and nothing the coach writes back, is logged.** Not your message, not the reply, not a truncated excerpt of either. When something goes wrong the relay records the shape of the failure rather than its contents: how long a reply was, where it stopped making sense, which check it failed, and a short random id for that one request so the lines belong together. The whole of the coach's output is treated as yours, including a generated program, which is built out of what you told it about your body. The relay's logs are deleted after 14 days regardless.

For rate limiting, the relay records a counter keyed to your device's IP address in its database. These counters expire automatically, within two minutes for the per-minute counter and within 48 hours for the daily one.

**Exactly what the coach is told.** Each coach message carries a context block. This is the complete list of what it can contain:

| | |
|---|---|
| Profile | Your goals, fitness level, experience, and injury notes — the free text you wrote |
| Preferences | Coach tone, reply length |
| Program | Program name, length, days per week, session names and their muscle groups |
| Today | Today's session and its exercises with target sets, reps, and weight |
| Recent workouts | Up to five, with date, session name, and the actual reps and weights you logged |
| Live set | Current exercise, set number, and what you have logged so far, while a workout is running — plus your heart rate at that moment, if you are wearing an Apple Watch running the WorkoutSmith watch app during the workout |
| Health | Today's step count, an average workout heart rate, and your Health-recorded body weight |
| Readiness | A score from 0 to 100, its band label, and whether Health data contributed |
| Fatigue | A plain-text fatigue summary and any deload recommendation |
| Milestones | A one-line note when you level up, and the outcome of a set the coach logged for you |
| Where a program came from | If you adopted a program someone else shared with you, a marker saying that this plan or session name was written by another person, and the times it was shared and adopted. Never their name, handle, email, or user id, and no text beyond what the rows above already carry. It is here for your protection rather than the coach's interest: knowing which words came from someone else is what lets the app hand them to the coach as a label another person wrote, never as an instruction to follow |
| A program that came out of a spreadsheet | If you imported a program from a spreadsheet, a marker saying that this plan or session name came out of a file rather than from you. Nothing about the file itself: not a link to it, not its name, not the Google account it was in, and no text beyond what the rows above already carry. A spreadsheet is something anyone can send you, so knowing which words arrived that way is what lets the app hand them to the coach as a label somebody else wrote, never as an instruction to follow |
| What the app has learned about you | A few sentences summarising patterns counted from your own logged workouts: where prescribed weight increases have landed and where you have stalled, which way your reps-in-reserve reports lean against what you then lifted, an exercise you have repeatedly swapped for another, and one you have repeatedly skipped |

Your conversation history for the current chat is sent with each turn, because that is how a conversation works.

**What the coach is never told.** Your name, your email, your user id, your device id, your age, your height, your biological sex, your home address or coordinate, your friends, your competition standings, your trophies, and your raw sleep, resting heart rate, or HRV readings. Your hand-entered bodyweight is not sent either — only a body mass figure that came from Apple Health.

**A caution worth stating plainly.** The profile fields — goals, experience, and especially **injuries** — are free text that you wrote. Whatever you type there goes to your AI provider. If you record a medical detail in the injuries field, that detail is part of the coach request. Bear that in mind when filling it in.

**Voice.** Speech is transcribed by Apple's on-device speech recognition where the device supports it. Only the resulting text is sent to the coach; audio never reaches our servers.

**Your controls.** Nothing goes to the coach until you have acknowledged the disclaimer and turned on AI data sharing. Turning that setting off stops all coach requests. Removing your key turns the coach off entirely — it does not silently fall back to the shared coach; using that is a separate, deliberate choice you make in Settings.

---

## Fitbit

Optional, off unless you connect it. It exists for people who track sleep and steps with a Fitbit rather than an Apple Watch, because Fitbit does not write into Apple Health.

Fitbit data now reaches apps through Google, which owns Fitbit and is retiring the older Fitbit developer interface. So you authorize this with the Google account your Fitbit is linked to, on Google's own sign-in page, using PKCE with no client secret. There is no server of ours in the path: your phone talks to Google directly. The app requests three read-only permissions and nothing else — sleep, health metrics and measurements (which covers resting heart rate and heart rate variability), and activity and fitness (which covers steps and distance). It asks for no permission to write anything back, and none to read your profile, so it is never told your name. Your tokens are stored in your device's Keychain, marked not to sync to iCloud, and are never sent to our servers.

**Sleep and heart rate stay on your phone.** The app pulls sleep stages, resting heart rate, and heart rate variability, holds them in memory only, and folds them into your readiness score. None of it is written to the app's database, and none of it is ever sent to the AI coach or to our server. The coach sees only the readiness number.

**Steps and distance can leave your phone, but only if you make them compete or share.** If you choose Fitbit as your activity source, your daily step and distance totals are used for challenges, leagues and the friends board exactly as Apple Health's are — which means a daily total is sent to our server when, and only when, you have opted that metric in one of the three ways listed above (joined a challenge on it, enrolled in a league on it, or set it to Friends or Global). Until you do one of those, nothing is uploaded. This is the same rule, and the same server, as for Apple Health activity data; the source you picked makes no difference to how it is treated. Nothing else Fitbit measures is ever uploaded.

Only one source counts your steps. If you connect Fitbit, you choose whether steps and distance come from Apple Health or from Fitbit, and the app never adds the two together.

Disconnecting clears the tokens from your Keychain immediately and asks Google to revoke them. The local clearing always happens; the revocation is a best-effort network call, so if you disconnect while offline you may also want to remove the app from your Google account's third-party access settings.

While this app is still in testing with Google, the permission you grant lasts seven days and then has to be granted again. The app will tell you when that happens. Nothing is lost in the meantime, and no data is read while the connection is lapsed.

Fitbit is only active in builds configured with a Fitbit connection. If the
App integrations screen in your copy of the app shows Fitbit as unavailable,
none of this section applies to your data.

---

## Home location and Adventure journeys

The Adventure tab can turn your walking and running mileage into a trip outward from home. Setting a home is optional; without it the feature falls back to fixed comparisons like marathon counts and needs no location at all.

**Your home is a place you type, not a place we detect.** You type an address or a town name into a text field. That typed text is converted to a coordinate by Apple's system geocoder, which means **the text you type is sent to Apple** the same way it is when you search in Maps. The app discloses this at the point you type it.

Once converted, **only the latitude and longitude are saved, never the address text.** The app displays it back to you rounded to roughly a mile. The coordinate is used in exactly one place, to compute how far along a journey you are, and it is deliberately excluded from the coach context, the widget, the data export, and every server request. We verified all four.

### The map's location button

The Adventure map has a button that centres the map on where you are. **It is the only thing in this app that reads your location, it reads it once per tap, and it never keeps the answer.**

- **You have to ask.** Nothing reads your location on launch, on opening the map, or in the background. The first time you tap the button, iOS shows you the standard permission prompt.
- **One reading, not tracking.** The app requests a single position fix and the hardware stops. There is no continuous location session, no blue dot following you, no background location, and no "always" permission — the app asks only for "while using".
- **Nothing is written down.** The coordinate is held in memory for as long as the map is on screen and is discarded when you leave it. It is not saved to the app's database, your preferences, the keychain, or the widget. It is never sent to our server, never given to the AI coach, and never included in an export. Closing the app forgets it completely.
- **Saying no costs you nothing.** If you decline, the map tells you so in one line and everything else works exactly as before: you can set a home by typing an address, move the map to any address you type, and use every other feature. The app worked this way before the button existed.

### Searching the map

Two things on the map ask Apple a question on your behalf, and only when you ask them to:

- **Typing an address** to move the map sends that text to Apple's geocoder, the same as setting a home does. The text is discarded afterwards and the map's position is not saved.
- **"What's nearby"** sends the part of the world currently on your screen to Apple's local search service and shows you the parks, museums and similar places it finds. We do not store the results, and we do not build a database of places from what anybody searches for. The list is gone when you leave the tab.

Both go to Apple as system services, exactly as they do in Maps. **Neither goes to our server**, and neither carries your account, your name, or anything else about you.

---

## What we store on our server

The server exists only for Compete. If you never sign in, you have no record on it at all.

**Signing in.** Sign in with Apple gives us a stable identifier Apple generates for this app, which is what we store as your account. You may supply a display name.

**Your email address, and what we actually keep.** Apple also sends an email address when you sign in. **We do not store it.** What we store instead is a *keyed fingerprint* of it: the address run through a one-way function under a secret key that is not in the database. It cannot be turned back into your address, and we hold no way to email you. It exists for exactly one purpose — so that a friend who already knows your address can send you a friend request, by our comparing fingerprints rather than by our knowing addresses.

**Friend requests by email.** When you send one, the address you typed is fingerprinted the same way and compared. Two things follow, and both are deliberate:

- **We never tell you whether that address has an account.** The reply is identical, to the letter and to the millisecond, whether it matched somebody or nobody. Otherwise this screen would be a way to find out who uses a fitness app, which is not yours or ours to disclose.
- **If it matched nobody, the fingerprint is kept for up to 30 days** — never the address itself — solely so that if that person signs up with it inside the window, your request is waiting for them instead of being lost. It becomes a request they can accept *or decline*, never an automatic friendship. It is deleted the moment it is used, when it expires, or when you delete your account, whichever comes first, and it is used for nothing else: no email is ever sent, and nothing is shared with anyone.

**What your account record contains.** An internal id, the Apple identifier, the email fingerprint described above, your display name, your public handle if you set one, and your avatar id.

**Avatars are not photos.** An avatar is one of 256 preset combinations of a system icon and a colour palette, stored as a short text id and validated against that fixed list. Photographs enter the app in exactly two other places, both described below: a picture you attach to a stop on a route you build, and a screenshot you choose to attach to feedback.

**What else is stored, and why.**

| | |
|---|---|
| Sessions | Your sign-in sessions, including a hash of the refresh token (not the token), plus the IP address and device user-agent of the sign-in |
| Sharing settings | Which metrics you have chosen to share, and with whom, plus your **Live** setting (see below) |
| Live status | Only while you are training, and only if you turned Live on: that you are training, what kind of activity it is, and one of five effort bands. Never a heart rate and never a location. It disappears on its own within 15 minutes of your last logged set, and it is deleted the moment you turn Live off |
| Friends | Who you are friends with, unredeemed invite codes, friend requests waiting for an answer, and email fingerprints for requests sent to addresses that have no account yet (kept 30 days, see above) |
| Challenges | The challenges you are in, their format and metric, your goal, and your state |
| Cheers | Which of four fixed emotes you sent to whom, inside a challenge. A cheer sent to a friend outside a challenge is **not** stored at all — only a marker that today's bonus to that person has been used. There is no free-text messaging between users anywhere in this app |
| Metric values | The activity numbers for the metrics you compete on or share, as individual entries and as daily totals |
| Daily goals | The daily step goal you set for the friends board. It is yours: it is used to work out your own percentage, and it is not shown to anyone else |
| Trophies | Placement, medal, metric, score, and the display name you had at the time |
| Leagues | Your division, weekly score, rank, and outcome |
| Notification devices | Only if you turned notifications about other people on: a device token from Apple for each phone you use, which addresses a notification to that device and identifies nothing else. Deleted when you turn them off, when you delete your account, and automatically 90 days after you last opened the app |
| Notification settings | Which categories you want, and the UTC offset your device reported, so nothing arrives in the middle of your night |
| Feedback | Anything you submit through the in-app feedback form (see below) |
| Groups | The friend groups you create or join: the group name, who is in it, who owns it, and whether members may bring others in |
| Routes and races | Routes you build (their name, the stops with their coordinates and any note you wrote, and the distances) and the races run on them: who is racing, who invited whom, and each check-in as a verdict that you reached a stop rather than a record of where you were |
| Route photographs | Pictures you attach to a route stop, held in private cloud storage with their embedded metadata refused at upload. Shown to the people you share that route or race with through short-lived links, and deleted when you delete the route |
| Programs shared between people | A program you send to a friend, and if you turn share-back on for a program you adopted, a summary of how your sessions went against how it was written |
| Landmark stamps (your passport) | Which landmarks your walking and running distance has reached, as a stamp per landmark with the date it was earned. It is a list of milestones you passed, never a location: no coordinate of yours is stored, and the landmarks themselves come from a fixed catalog bundled in the app |
| Diagnostic log | A 24-hour record of app EVENTS, attached to a feedback submission only when you turn the switch on for that report: screens you opened, whether a request succeeded and its status code, state changes, error identifiers, sync outcomes, the messages your iPhone and Apple Watch exchanged, and which tools your AI coach asked to use |
| Audit records | A log of security-relevant actions on your account — sign-ins, friend changes — with your id, IP address, and user-agent |

**What is never on our server.** Your workouts, sets, weights, programs, coach conversations, sleep, resting heart rate, HRV, body weight, injuries, goals, birth year, and home coordinate.

---

## Notifications

There are two kinds and they work completely differently.

**Workout reminders are local.** You pick the days and the time in Settings, your phone schedules them, and nothing about them is sent anywhere. They stay silent while your streak is paused and once you have already trained that day.

**Notifications about other people are opt-in and come from our server.** These are the ones that tell you somebody invited you to a challenge or a race, asked to be friends, cheered you on, or that a challenge you were in has finished. They are **off until you turn them on**, and we never ask about them when you first open the app — only after something has happened that one of them would have been about.

- **Turning them on registers this device with Apple.** Apple gives your phone a device token and we store it against your account so a notification can be addressed to it. **It identifies the phone, not you**, and there is nothing anywhere in this service that reads it back, looks up who a token belongs to, or answers any question about a device — the only two things that can happen to one are that a notification is sent to it and that it is deleted.
- **When it is deleted.** When you turn notifications off, when you sign out on that device, when you delete your account, and automatically 90 days after the last time you opened the app. Apple also tells our server when a device is gone, and we delete the token then too.
- **We store your device's UTC offset**, sent by the app when it registers, for one purpose: so that nothing arrives between 10pm and 7am where you actually are. It is a number of minutes, not a place, and if it is missing we do not guess one — we simply apply no quiet hours rather than infer a timezone from your IP address.
- **What is in a notification.** The same small set of facts the app already shows you: what happened, who did it, and which challenge or race it was about. A notification never contains anybody else's numbers, standings, or location.
- **You choose which ones.** Every category has its own switch in Settings, and there are per-day caps on all of them so no failure anywhere upstream can turn into a stream of notifications.
- **We never send marketing.** There is no category for it, no code path to it, and no address to send it from — we do not store your email address at all.

---

## Who can see what

- **Private by default.** Every metric starts private. Nobody sees any of your numbers until you change a setting. This is structural rather than a stored default: with no sharing row, the answer to "can this person see it" is no.
- **Friends** see your display name, avatar, and the specific metrics you set to friends-level sharing, plus standings in challenges you are both in. If — and only if — you turn on Live sharing, friends also see the short-lived mid-workout marker described above while a workout is running; it can never be set to public. Friends are added two ways and no others: by an invite code shared out of band, or by a request sent to an email address someone already knows. **There is still no directory and no user search** — nothing anywhere lets you look up who has an account, including the email path, which never reports whether an address matched.
- **A friend request tells the person who sent it nothing.** If you decline one, the sender is not notified and sees no change; from their side the request simply stays sent. Accepting is the only outcome they learn about, because becoming someone's friend is visible by its nature.
- **The friends board** shows, for each metric you set to Friends, your total for the last seven days, how many of those days had a total, and how much of your own daily goal you reached. It never shows your goal itself, and a day you did not record is shown as having no update rather than as a zero. A friend who has shared nothing appears on nobody's board.
- **Live: whether friends can see that you are training right now.** This is a separate setting from every metric above, it is **off by default**, and it is friends-or-nobody: there is no public version of it, and the server refuses to store one. With it on, a friend's Social tab shows that you are mid-workout, what kind of activity it is, and roughly how hard you are working as one of five bands — **easy, steady, moderate, hard, or peak**. It is never a heart rate, never a number of any kind, and never a location. With it off you are invisible and nothing about your session is stored at all: the app does not send it, rather than sending it and having it hidden.
  - It goes away by itself. Each update lasts about 15 minutes, and the app refreshes it only when you log a set, so a phone that dies mid-workout drops off your friends' screens rather than leaving you shown as training forever.
  - Turning it off **deletes** whatever is currently stored, in the same request, rather than only stopping new updates.
  - It is not kept as history. There is no record of when you trained, no log of past sessions, and nothing to look back at — the only thing stored is the current one, and only while it is current.
- **Cheers with a boost.** A friend can send you one of three fixed reactions — a cheer, a flame, or a strength emote — and the first one each of you sends the other each day carries a small bonus to the XP in your own Adventure profile. **The cheer itself is not stored**: you learn about it from your change feed, there is no cheer history anywhere, and the only thing kept is a marker that today's bonus has been used. The XP it buys is worked out entirely on your own phone and is deliberately excluded from anything ranked, so cheering cannot move anybody's standing in a challenge or a league.
- **Challenges** are visible only to their participants. Someone who is not in a challenge cannot see that it exists, even if they are your friend.
- **Global leagues** are opt-in and require you to pick a public handle first. Global boards show **only** your handle, avatar, score, and rank — never your display name. There is an automated test in the codebase asserting that no global response can serialize a display name or the Apple identifier. Global boards do also carry your internal account id, which is a random string not derived from your Apple identifier, but it is stable and visible to others in your cohort.
- **Turning global sharing off removes you from leagues immediately.**

### Programs shared between friends

You can send a workout program to a friend, and they can send one to you. This is the only feature where one person's content lands on another person's device, so it has its own rules.

- **A shared program is a copy.** When you adopt a program a friend sent, you get your own copy of it. You can rename it, change the weights, swap exercises, or have your AI coach restructure it, and none of that reaches the person who wrote it unless you separately turn on share-back. Their original is untouched by anything you do, and your copy is yours.
- **What travels with a program** is its name, its days, its exercises, the prescribed sets, reps, loads, rest and notes. Nothing about you goes with it, and nothing about the author comes with it beyond their name as a friend you already have.
- **Sharing your results back is off unless you turn it on**, and it is a separate decision for each program you adopt. You are asked once, at the moment you adopt, and you can change the answer at any time in the privacy screen.
- **What the author sees when it is on:** how many sessions of that program you have completed against how many it prescribed, what you actually lifted compared with what they wrote, which exercises you changed or skipped and whether you or your coach changed them, and your best sets on that program.
- **What the author never sees, on or off:** any other training you do, your workout history, your chat with your coach, anything from Apple Health or Fitbit, your readiness or sleep or heart rate, your bodyweight, your location, or any program other than the one they gave you. The summary is built to carry counts and typical numbers only; it has no per-session detail in it and cannot be turned back into a training log.
- **Turning it off deletes it.** Revoking share-back removes the summary from our server rather than hiding it, so the author stops being able to see it at all. Nothing further is sent from that point.
- **Text other people wrote is treated as untrusted.** A program's name and notes are written by whoever shared it. Where that text is shown to your AI coach, it is explicitly marked as something another person wrote so the coach treats it as a label and never as an instruction, and the markers themselves are stripped from what people type so they cannot be forged.

---

## Feedback you send us

The in-app feedback form sends: a category, your message, and optionally a screenshot you attach. It also sends technical context that the form shows you before you send — app version and build, device model, iOS version, the screen you were on, the last few screens you visited, your locale, timezone, free disk space, and uptime.

You can send anonymously. When you do, the decision is made on the server, not trusted to the app: no account id and no name is written to the record.

Screenshots are stored in the same database as the rest of the feedback, not in a public bucket, and are never shown to other users.

For triage, feedback submissions are also copied to a private spreadsheet
accessible only to the developer, and a screenshot you attached is copied to a
private Google Drive folder that the spreadsheet links to. Neither the folder
nor the images in it are link-shared or public. When you delete your account,
the identifying fields of your rows in that copy are removed and the copied
screenshot is deleted, as part of honoring the deletion.

---

## What we do not do

- **No advertising.** No ad SDKs, no ad identifier, no IDFA access.
- **No analytics or crash reporting.** No Firebase, no Sentry, no Amplitude, no Mixpanel. The app has no third-party dependencies of any kind — every dependency is Apple's own framework or first-party code in this repository.
- **No tracking.** The app does not collect data about you for advertising or measurement, does not link your activity to third-party data, and does not use the App Tracking Transparency framework because it has nothing to ask for.
- **No data brokers, no sale, no sharing for cross-context advertising.**
- **No push notifications you did not ask for.** Workout reminders are still scheduled locally by your phone and nothing is sent anywhere to schedule them. Notifications about other people — an invitation, a cheer — are a separate thing you turn on, and until you do, this app never registers with Apple's push service and we have no way to reach you. See "Notifications" above.

---

## Getting your data out

Settings has an "Export workout history" option that writes your profile, programs, and full workout history — every set, rep, and weight — to a JSON file you can share or save wherever you like. It does not include your chat history, body weight, birth year, or home location.

The export file is written to a temporary folder on your device. iOS clears that folder periodically, but the app does not delete the file immediately after sharing.

Your programs and your workout history can also go to a Google spreadsheet, in your own Google Drive, under your own Google account. You sign in to Google yourself, on Google's own page, and we never hold your Google credentials. The app asks for two permissions and nothing wider: one to work with spreadsheets, and one that reaches only the files it created or that you handed to it, so the rest of your Drive stays invisible to it.

Workout history travels in that direction only. A program can come back in from a spreadsheet; results never can, and a history sheet is refused outright, because a number typed in a cell is not evidence that you lifted anything.

To receive a copy of the data our server holds about you, email
**mignet1278@gmail.com** from the address associated with your account and we
will provide it within 30 days.

---

## Deleting your data

Two separate controls, because they do different things.

**"Delete all data" (Settings).** Returns the phone to the state a fresh install starts in. There is no residue in a corner of the app you did not think to check; the point of this control is that it means what it says. It removes from the device:

- your profile, your programs, and your entire workout history — every exercise, set, rep and weight;
- your whole chat and voice conversation with the coach;
- your XP, your level, and every achievement tier you have earned;
- your saved home coordinate for the Adventure journeys;
- every setting, which includes your Apple Health category toggles, your reminder schedule and the reminders already scheduled with iOS, your streak and pause history, and your acknowledgement of the AI disclaimer and data-sharing consent, so both are asked again before anything is sent to a coach;
- all three Keychain items: your AI provider key, your Fitbit tokens, and your sign-in tokens;
- the smaller things kept alongside them — the cached copy of your account name and avatar, the bookkeeping recording which metrics have been uploaded, and the per-install identifier that seeds your default avatar;
- the widget's snapshot of your streak and readiness, so the home screen stops showing figures whose source has been deleted;
- any export file still sitting in the app's temporary folder.

It also deletes from Apple Health the workouts this app wrote there, leaving anything recorded by other apps or your watch untouched. If Fitbit is connected it disconnects it, and asks Google to revoke the token as well as clearing it locally.

**What it does not do is delete your account on our server.** It signs you out of that account on this device, but the account itself and everything listed under "Delete account" below survive, and signing in again brings you back to the same one. The two controls are deliberately separate, and you are free to use both.

**"Delete account" (Settings).** Deletes your account on our server. This is deliberately separate: your on-device workouts survive it. It removes your profile, your handle, Apple-identifier and email-fingerprint records, your sessions, your sharing settings, your friendships in both directions, your invite codes, the friend requests you sent and received, any waiting invitations you sent to addresses with no account, your metric values and daily totals, your league enrolments and memberships, your challenge participations, and your change history. Challenges you created are removed along with their rosters and cheers.

Two things survive by design, and you should know before you press it:
- **Trophies stay, anonymized.** Removing them would corrupt other people's competition histories. Your account id is cleared and your name is replaced with "Departed athlete", but the placement, metric, and score remain attached to that past challenge.
- **Feedback you submitted stays, de-identified.** Your account id and name are stripped, and any screenshot you attached is deleted outright, because a screenshot can show your body and your lifts. The message text and device context remain so that a reported bug does not vanish mid-investigation.

Security and audit records (sign-ins and account activity, including IP
address and device user-agent) expire automatically after 90 days. The single
record of an account deletion itself is kept, without IP or device details, as
proof the deletion happened.

**Deleting the app** removes everything on the device, including the Keychain items. It does not delete your server account; use "Delete account" first if you want both.

---

## Security

Traffic between the app and both our servers is HTTPS. Sign-in tokens, your AI provider key, and your Fitbit tokens are held in the iOS Keychain, marked so they do not sync to iCloud Keychain and are not included in encrypted device backups. Our database stores a hash of your refresh token rather than the token itself. Handles are sanitized against invisible and direction-reversing characters so that nobody can impersonate another athlete on a leaderboard.

No system is perfectly secure, and this is a small independent app rather than a company with a security team. The design compensates by keeping the sensitive material — your health data and your training history — on your own device, where a compromise of our server cannot reach it.

The server database keeps encrypted continuous backups for up to 35 days for
disaster recovery. Data you delete leaves those backups as they age out of that
window.

---

## Children

WorkoutSmith is not directed to children and is not intended for anyone under 13. We do not knowingly collect personal information from children under 13.

We reviewed the app against the features that typically raise child-safety questions:
- There is **no free-text messaging between users**. Encouragement is limited to four fixed emotes.
- There are **no user-supplied challenge names or descriptions**; every challenge title comes from a fixed set of formats.
- **Photographs, and who can see them.** Avatars are preset icons and are not photographs. You can attach a photograph to a stop on a route you build; that picture is stored in our private cloud storage, its embedded metadata (including any location the camera recorded) is refused rather than kept, and it is shown to the people you share that route or race with, through short-lived links, for as long as the route exists. Deleting the route deletes its photographs. A screenshot you attach to feedback goes to the developer and to no other user.
- There is **no user search or directory**. Friends are added by an invite code shared out of band, or by a request sent to an email address the sender already knows — and that request never reveals whether the address has an account, so it cannot be used to find anyone.
- Nothing is public by default. Global visibility requires deliberately opting a metric to global and choosing a handle.
- The app collects no birthday. An optional birth *year* field exists in Settings for strength-standard tables; it stays on the device and is never sent to our server.

The two fields another user can see that are free text are your **display name** and your **public handle**. Handles are restricted to letters, numbers, hyphens and underscores.

---

## Changes to this policy

If this policy changes materially, the effective date at the top changes and the updated version is posted at the same URL before the change takes effect. Because we do not store an email address for you, we cannot notify you by email — check this page.

---

## Contact

Privacy and deletion requests: **mignet1278@gmail.com**.

You can also reach us through the in-app feedback form, in Settings.

This policy is governed by the laws of the Commonwealth of Massachusetts, USA. The app is currently offered to testers in the United States; if it becomes available in the EU or UK, this policy will be updated with the disclosures those jurisdictions require before that availability.

---
---

# Appendix — where each claim was verified

Every path is relative to the repository root, `/Users/miklee/dev/AI_Workout_App`.

### Apple Health
- Read types (steps, body mass, heart rate, walking+running distance, cycling distance, resting heart rate, HRV SDNN, sleep analysis, workouts): `ios/AIWorkout/Core/Health/HealthStore.swift:198-223`
- Only one file in the app imports HealthKit: `ios/AIWorkout/Core/Health/HealthStore.swift:187`
- Write types requested (workouts, active energy): `HealthStore.swift:227-231`; workouts written with duration only, energy always nil: `HealthStore.swift:583-624`, `ios/AIWorkout/Core/Health/HealthManager.swift:236-241`
- Deleting app-written workouts by stored UUID: `HealthStore.swift:611`, called from `ios/AIWorkout/Features/Workout/WorkoutView.swift:109` and `ios/AIWorkout/Features/Settings/SettingsView.swift:538`
- Lifetime journey mileage read (`start: nil, end: nil`): `HealthManager.swift:176`, `HealthStore.swift:410`
- Two-year workout window: `HealthStore.swift:301`, `HealthManager.swift:52`
- No background delivery, no observer queries, no `UIBackgroundModes`: no matches for `HKObserverQuery` / `enableBackgroundDelivery` / `HKAnchoredObjectQuery` in `ios/`; `ios/AIWorkout/Info.plist`
- Usage strings (and the gap): `ios/AIWorkout/Info.plist:55-58`
- Health values in coach context: `ios/AIWorkout/Core/TrainerContextBuilder.swift:64-78, 192-209`, `ios/AIWorkout/Features/Chat/ChatView.swift:406-419`
- Live heart rate from the watch: measured in `ios/AIWorkoutWatch/WatchWorkoutSession.swift`, throttled by `ios/ProgressionEngine/Sources/WatchLink/HeartRateThrottle.swift`, held in memory only by `ios/AIWorkout/Core/CurrentWorkoutState.swift` (`recordHeartRate`, dropped past 90 seconds and on `clear()`), and reaching the coach at `TrainerContextBuilder.swift` `buildActiveSession`. It appears in no SwiftData model, no export, no widget snapshot, and no server payload
- Health metrics to the competition server, and the gate that reads nothing until you have opted a metric in: `ios/AIWorkout/Core/Competition/MetricSyncService.swift` (`activeMetrics()`, which fetches) calling `ios/ProgressionEngine/Sources/CompetitionKit/MetricUploadConsent.swift` (which decides, and is the single place the three opt-in routes are resolved). The rule is unit-tested case by case in `MetricUploadConsentTests.swift`, including that a private scope opts nothing in and that a metric keeps uploading until the *last* route to it closes.
- 35-day window: `MetricSyncService.swift:41`

### The AI coach
- Key in Keychain, `kSecAttrAccessibleWhenUnlockedThisDeviceOnly`, no iCloud sync: `ios/AIWorkout/Core/AICoachConfig.swift:106-133`
- Key sent only as a header, never logged: `ios/AIWorkout/Core/TrainerClient.swift:272-277`
- Relay uses the key per-request and does not persist it: `backend/src/app.ts:75-110`, `backend/src/providers/gemini.ts:41-47`
- Complete context struct: `ios/AIWorkout/Core/TrainerContextBuilder.swift` (whole file); rendered to prose at `backend/src/context.ts:270-304`
- Profile mapped to four fields only; name, sex, birth year, bodyweight, avatar, locations all withheld: `TrainerContextBuilder.swift` `buildProfile`, against the model at `ios/AIWorkout/Models/ProgramModels.swift:8`
- Consent gates before any send: `ChatView.swift:346-349, 361, 515`
- No conversation state on the server; no logging middleware: `backend/src/app.ts` (middleware list), all `console.*` calls in `backend/src`
- No message or model content in any log line: every `console.*` in `backend/src` carries a provider SDK error, a rate-limit decision, a token-verification reason, or a length/position, and none takes a message, a prompt, or a reply. The program route's failure diagnostics: `backend/src/app.ts:327-336`; the content-free parse-failure text and why V8's own message cannot be used: `backend/src/program.ts:267-290`; validation errors are field paths and type expectations that quote no value: `backend/src/program.ts:180-265`; tests asserting nothing identifiable survives into the diagnostics: `backend/test/program-diagnostics.test.ts`
- 14-day log retention: `infra/template.yaml:265`
- Rate-limit counters keyed by IP with 120s / 48h expiry: `backend/src/limits.ts:216-250`, `backend/src/ratestore.ts:132`
- On-device speech where supported: `ios/AIWorkout/Core/Speech/SpeechRecognizer.swift:73-76`
- Shared-coach path, and that a request with no user key spends the server's own key: `backend/src/app.ts:88`, `backend/src/guard.ts:186`, `ios/AIWorkout/Features/Settings/AICoachSettingsView.swift:118`, `infra/template.yaml:325`
- Shared-coach daily budget (60 units signed in, 8 anonymous; a chat turn costs 1 and a program 5), charged only when no user key is present, keyed to the account id or the source address, expiring in 48h: `backend/src/limits.ts:35-38, 76-91, 242-255`
- The shared key on the deployed stack is Gemini: `infra/template.yaml:326-331`
- Anthropic as a user-selectable provider: `backend/src/providers/anthropic.ts`, `ios/AIWorkout/Core/AICoachConfig.swift:11-45`

### Fitbit
- PKCE, no client secret, three read-only Google Health scopes, redirect derived from the iOS client id: `ios/AIWorkout/Core/Integrations/Fitbit/GoogleHealthOAuth.swift`, `GoogleHealthConfig.swift`, `ios/Config.xcconfig`
- Tokens in Keychain, this-device-only: `ios/AIWorkout/Core/Integrations/Fitbit/GoogleHealthTokenStore.swift`
- Endpoints and fields pulled; readiness readings memory-only, no persistence: `ios/AIWorkout/Core/Integrations/Fitbit/GoogleHealthAPI.swift`, `FitbitManager.swift`
- Steps and distance uploaded only for a metric the lifter has opted in (joined a challenge or league on it, or set it to Friends or Global): `CompetitionKit/MetricUploadConsent.swift` (the rule), `ios/AIWorkout/Core/Competition/MetricSyncService.swift` (`activeMetrics()` gate), `ios/AIWorkout/Core/Integrations/ActivityTotalsProvider.swift`
- An unanswered, declined or abandoned challenge invitation is **not** consent: `MetricUploadConsent.swift` (accepted participants only), test `MetricUploadConsentTests.testAnUnansweredOrRefusedInvitationIsNotConsent`
- The friends board reads only what each person volunteered, and omits a day nobody recorded rather than reporting it as zero: `server/src/friends-summary.ts`, `server/src/board-scoring.ts`, contract test `server/test/store-contract.ts` ("omits a day with no counting total rather than reporting it as zero")
- Your daily goal is never sent to anyone else: `server/src/friends-summary.ts` (`goal` is present only on the caller's own row), test `server/test/friends-summary.test.ts` ("never shows another person daily goal, only the caller own")
- Live status is not sent at all while it is off, rather than sent and hidden: `CompetitionKit/LiveRail.swift` (`PresenceGate.mayWrite`, which treats an unknown scope as private), `ios/AIWorkout/Core/Competition/PresenceService.swift` (which is the only caller), tests `LiveRailClientTests.testAnUnknownScopeIsTreatedAsPrivate` and `testPresenceIsWrittenOnlyWhenTheLiveScopeIsFriends`
- Live status carries an effort band and never a heart rate: `server/src/presence.ts` (`HR_ZONE_BANDS`), `CompetitionKit/FriendsHub.swift` (`HrZoneBand`), tests `LiveRailTests.testPresenceCarriesNoHeartRate` and `LiveRailUITests.testTheRailNeverPutsAHeartRateOnScreen`
- Turning Live off deletes what is stored in the same request: `server/src/app.ts` (`PUT /me/shares/:metric`, the `clearPresence` branch)
- Live status expires on its own within 15 minutes: `server/src/presence.ts` (`PRESENCE_TTL_MS`, enforced from the stamp in both backends)
- There is no public live rail to consent to: `server/src/presence.ts` (`LIVE_SHARE_SCOPES`), `CompetitionKit/LiveRail.swift` (`PresenceGate.scopes`), test `LiveRailClientTests.testThePickerOffersPrivateAndFriendsAndNotGlobal`
- A friend cheer stores nothing but the day's claim: `server/src/friend-cheers.ts`
- A cheer's XP cannot move anybody's standing: `LevelEngine/XPEngine.swift` (`workoutXP` is recomputed with the boosts left out, and `workoutXP` is the only total `MetricSyncService` uploads), tests `CheerBoostXPTests.testACheerIsWorthNothingInAnyRankedTotal` and `testABoostDoesNotDisturbTheRankedTotalThroughTheDailyCapEither`
- One activity source, never summed: `ActivityTotalsProvider.combining`, `ios/AIWorkout/Core/Integrations/ActivitySource.swift`
- Coach sees only score/band/flag: `TrainerContextBuilder.swift:192-197`
- Disconnect clears locally then attempts revocation: `FitbitManager.swift` `disconnect()`
- Inert without a client id: `GoogleHealthConfig.isConfigured`, `ios/Config.xcconfig`, `ios/AIWorkout/Features/Settings/IntegrationsSettingsView.swift`

### Home location and journeys
- Typed address only: `ios/AIWorkout/Features/Adventure/HomeLocationEditor.swift`
- Geocoding call: `HomeLocationEditor.swift` `lookUp()`; in-app disclosure in `privacySection`; displayed rounded in `coordinateText`
- Only the coordinate persisted; address held in view state and cleared: `ios/AIWorkout/Models/AppSettings.swift:153-157`, `ios/AIWorkout/Features/Adventure/JourneyBridge.swift:38-51`
- Single consuming read site: `JourneyBridge.swift:28-29` (plus an `onChange` observation at `ios/AIWorkout/Features/Adventure/AdventureView.swift:112-113` that does not forward the value)
- Absent from coach context (`TrainerContextBuilder.swift`), widget (`ios/AIWorkout/Core/WidgetSnapshotWriter.swift`), export (`ios/AIWorkout/Features/Settings/WorkoutDataExport.swift`), and all server payloads (no matches in `backend/`, `server/`, `ios/AIWorkout/Core/Competition/`)
- Recap reduces to name/place/distance before the engine: `AdventureView.swift:231-236`

### The one-shot location read (added with the map controls)
- The only `CLLocationManager` in the repository, and the only file that owns one: `ios/AIWorkout/Core/LocationMoment.swift`
- One fix per request via `requestLocation()`, never `startUpdatingLocation()`, so the hardware stops itself and no session can be left running
- When-in-use only: `NSLocationWhenInUseUsageDescription` in `ios/AIWorkout/Info.plist`; there is no `NSLocationAlwaysAndWhenInUseUsageDescription`, no background location mode in `UIBackgroundModes`, and no location entitlement in `ios/AIWorkout/AIWorkout.entitlements`
- Never persisted: the coordinate lives only in `LocationMoment.state` and in the map screen's `@State`, both dropped in `AdventureMapScreen.onDisappear`. No key is added to `LocalDataWipe` because there is nothing to wipe — held as a test in `ios/AIWorkoutTests/MapLocationTests.swift` `testTheWipeHasNothingNewToClear`
- Never transmitted: no call site passes a fix to the coach context, the widget snapshot, the export, or any server payload
- Refusal is a state and never an alert or a re-prompt: `LocationMoment.request()` returns early on `.denied`, covered by `testARefusalIsNeverAskedAgain`
- Nothing reads location unprompted: `testItAsksNothingUntilItIsAsked`, and the UI gate `testThePickerOffersLocationRatherThanDemandingIt`

### Map searches (Apple system services, not our server)
- Forward geocode of a typed address, discarded after use: `ios/AIWorkout/Features/Adventure/MapAddressSheet.swift`
- Nearby place lookup around the displayed region, on tap only, results held in view state and never stored: `ios/AIWorkout/Features/Adventure/NearbyPlaces.swift`
- No server-side place database was built and none is planned; the curated catalog remains a bundled file: `ios/ProgressionEngine/Sources/JourneyEngine/Resources/landmarks.json`

### On-device storage
- Eleven SwiftData models: `ios/AIWorkout/Debug/AppModelContainer.swift:13-25`
- Local-only container, no CloudKit argument and no CloudKit entitlement: `AppModelContainer.swift:38`; entitlements files
- Widget snapshot contents (no name, no identifier, no raw health values): `ios/Shared/WidgetSnapshot.swift:12-38, 124-137`
- Three Keychain items, all this-device-only: `AICoachConfig.swift:107-133`, `ios/AIWorkout/Core/Competition/TokenStore.swift:18-44`, `GoogleHealthTokenStore.swift`
- Install identifier is local and only hashed locally: `ios/AIWorkout/Core/AvatarIdentity.swift:21-22`
- Export contents: `ios/AIWorkout/Features/Settings/WorkoutDataExport.swift`
- Local reminders are scheduled by the device and nothing about them leaves it: `ios/AIWorkout/Features/Notifications/NotificationScheduler.swift`
- Remote notifications are opt-in, and the opt-in is our own flag rather than iOS's authorization status, so granting permission for reminders does not enrol anybody in push: `ios/AIWorkout/Features/Notifications/PushRegistrar.swift` (`OptIn`, and the invariant stated at the top of the file)
- Never asked at launch: the two ask moments are an invitation sent and a cheer received, both raised only from the Social tab: `PushRegistrar.consider(_:)`, `CompetitionRootView.swift`
- The device token is stored keyed by a hash of itself and there is no lookup by token and no read across users: `server/src/push/tokens.ts`; the routes are scoped to the caller: `server/src/app.ts` (`/me/push-tokens`)
- Token expiry at 90 days, refreshed on each registration; dead tokens dropped when Apple reports them: `server/src/push/tokens.ts` (`TOKEN_TTL_MS`, `dropDeadToken`)
- Quiet hours applied from the device's own offset, never inferred: `server/src/push/categories.ts` (`isQuietHour`)
- Per-category switches and per-day caps: `server/src/push/categories.ts` (`CATEGORY_DEFAULT_ENABLED`, `CATEGORY_DAILY_CAP`), `server/src/push/prefs.ts`
- Every sentence that can reach a lock screen, in one file under a banned-vocabulary test: `server/src/push/copy.ts`, `server/test/push-copy.test.ts`
- No third-party packages at all: `ios/project.yml` (only the local `ProgressionEngine`), `ios/ProgressionEngine/Package.swift` (no remote dependencies)
- No ad identifier or tracking framework: no matches for `AppTrackingTransparency`, `ASIdentifierManager`, `advertisingIdentifier`, `NSUserTrackingUsageDescription` in `ios/`
- Delete-all-data implementation: `ios/AIWorkout/Features/Settings/SettingsView.swift:544-596`; dialog copy at `:133-146`
- The stores outside SwiftData that the wipe reaches, each key named at the type that owns it: `ios/AIWorkout/Core/LocalDataWipe.swift`
- Every settings field returned to its default, including the home coordinate: `ios/AIWorkout/Models/AppSettings.swift:204-239`
- Tests: preference keys claimed and not claimed, and a settings row mutated field by field and reset: `ios/AIWorkoutTests/LocalDataWipeTests.swift`
- Delete-account implementation: `SettingsView.swift:147-186`; token and cache clearing at `ios/AIWorkout/Core/Competition/AuthStore.swift:195-200`

### The server
- Deployed store is DynamoDB, single table `aiworkout-prod`; SQLite is local development only: `server/src/lambda.ts`, `server/src/index.ts`, `infra/template.yaml:72-134, 193`
- Full entity and field list: `server/src/store/types.ts`, `server/src/store/dynamo.ts:117-232`
- Apple email kept only as a keyed HMAC under a server-side secret, never as an address; the hashing is the only thing done with it: `server/src/email-identity.ts`, `server/src/users.ts` (`upsertUserByAppleSub`, `recordEmailHash`), `server/src/store/types.ts` (`UserRow.email_hash`)
- No email address is written to any table, asserted by a test that reads every text column of every table after a request is sent: `server/test/friend-requests.test.ts` ("never stores an email address in any readable form")
- A friend request answers a match and a miss with identical bytes, an identical status and a padded identical response time: `server/src/friend-requests.ts`, `server/src/app.ts` (`POST /friends/requests`), tests in `server/test/friend-requests.test.ts` ("enumeration defence")
- An address with no account is kept only as a fingerprint, for 30 days, and converts to a request the new account may decline: `server/src/friend-requests.ts` (`convertPendingInvites`), `server/src/store/types.ts` (`PendingInviteRow`), tests "an invitation to somebody who has not joined yet"
- Declining notifies nobody and writes no change for the sender: `server/src/friend-requests.ts` (`declineFriendRequest`), test "decline is invisible to the requester"
- Global boards expose handle, avatar, score, rank, and internal id only: `server/src/leagues.ts:482-501, 534-545`; test asserting no name or Apple id leaks: `server/test/handle-anonymity.test.ts`
- Handle required before global sharing or leagues: `server/src/app.ts:409-414, 678-683`
- Sharing private by default, structurally: `server/src/shares.ts:21-37, 63-66`, `server/src/app.ts:390-395`, `server/src/metrics.ts:52-57`
- Leaving global drops league enrolment: `server/src/app.ts:418`
- Metric values stored per event plus daily rollups, no expiry: `server/src/metrics.ts:152-162`, `server/src/store/dynamo.ts:1230-1238`
- Cheers are four fixed emotes, no free text: `server/src/validation.ts:180-183`
- No user-supplied challenge names: `createChallengeSchema` in `server/src/validation.ts`
- Challenge detail hidden from non-participants: `server/src/challenges.ts:653-661`
- Avatars validated against a closed preset space: `server/src/avatars.ts`
- Handle sanitization: `server/src/handle.ts:23-41`, rationale in `server/SECURITY.md:22-43`
- Feedback fields, server-side anonymity decision, screenshot stored inline (no S3 bucket in the stack): `server/src/feedback.ts:10-14, 90, 98-119`, `server/src/store/dynamo.ts:667-671`, `infra/template.yaml`
- Account deletion: `server/src/app.ts:318-326`, `server/src/store/dynamo.ts:892-1010`; trophy anonymization `server/src/trophies.ts:17`; screenshot deletion and its rationale `server/src/store/dynamo.ts:939`
- Audit rows lack index keys and expiry, so deletion cannot reach them: `server/src/store/dynamo.ts:1072-1076`
- IP and user-agent captured for rate limiting and audit: `server/src/middleware.ts:25-33`
- No third-party SDKs, no analytics, no telemetry: `server/package.json`
- No bulk export route: full route list in `server/src/app.ts`
- 14-day CloudWatch retention; no API Gateway access logging; point-in-time recovery off: `infra/template.yaml:127-128, 159, 271`
- Development sign-in: absent from production. The deployed stack runs `EnableDevAuth=false` (`NODE_ENV=production`), under which the route at `server/src/app.ts:208-243` is never mounted; verified 2026-07-30 (`/auth/dev` returns 404, `/health` reports `devMode:false`)

### Transport and general
- HTTPS to both AWS endpoints: `infra/template.yaml:394` and the Lambda Function URL output
- App Transport Security has only `NSAllowsLocalNetworking`, with no arbitrary-loads exception: `ios/AIWorkout/Info.plist`
- Cryptography limited to SHA-256 for PKCE and the Sign in with Apple nonce: `ios/AIWorkout/Core/Integrations/Fitbit/GoogleHealthOAuth.swift`, `ios/AIWorkout/Features/Account/AccountSignInView.swift:104`
- Refresh tokens hashed server-side: `server/src/crypto.ts`
- No birthday collected; optional birth year is local only: `ios/AIWorkout/Features/Settings/ProfileEditorView.swift:69-75`, `ios/AIWorkout/Models/ProgramModels.swift:34`, used at `ios/AIWorkout/Features/Tracks/TracksBridge.swift:48`
