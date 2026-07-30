# WorkoutSmith — Privacy Policy

**Effective date:** July 30, 2026
**Last updated:** 2026-07-30

---

## The short version

WorkoutSmith is a training app. It is built so that the things you would least want to leak — your workouts, your body, your sleep, your heart rate, where you live — stay on your iPhone.

- **Your training history and health data live on your phone**, in the app's own storage. There is no account required to use them, and they are not uploaded to us.
- **We run one server**, and it exists only for the social features: signing in, your friends list, challenges, leagues, and trophies. It holds your name, a handle, an avatar id, and the numbers for the specific metrics you chose to compete on. Nothing else.
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

**3. In accounts with other companies.** If you use the AI coach with your own Google (Gemini) or Anthropic (Claude) API key, those requests are billed to and governed by your account with that company, and we are not the account holder. If instead you use the shared coach, the request goes to the same place but on our account rather than yours — see "The shared coach" below. If you connect Fitbit, your phone talks to Fitbit directly using your own Fitbit login. In every case, those companies' privacy policies apply to what they do with what they receive.

---

## What stays on your device and never leaves it

The following are stored on your iPhone and are not transmitted to our server, to the AI coach, or anywhere else:

- Your full workout history: every exercise, set, rep, weight, RIR, warm-up, and rest.
- Your programs, whether AI-generated or hand-built.
- Your entire chat and voice conversation history with the coach. Our server keeps no conversation state; the transcript exists only in the app's local database.
- Your injuries, goals, experience level, and equipment notes, except where they are included in a coach request (see the AI coach section — this is the one exception, and it is under your control).
- Your birth year, biological sex, and hand-entered bodyweight. These are optional, used only for local strength-standard tables, and are sent nowhere.
- Sleep duration, resting heart rate, and heart rate variability. These are read from Apple Health or Fitbit, converted into a single readiness score on the device, and the underlying readings are never transmitted. Not to us, not to the AI.
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

*b) If you enter a challenge or league that races on a Health metric.* The app uploads daily totals for only the metrics you are actively competing on — steps, walking+running distance, running distance, running time. If you have not joined anything that races on a metric, that metric is never even read from Health, let alone uploaded. Uploads cover a rolling 35-day window so that totals stay correct if you were offline. What our server receives for these is a per-day figure, which over time forms a daily record of those activity totals for as long as you have an account.

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
| Live set | Current exercise, set number, and what you have logged so far, while a workout is running |
| Health | Today's step count, an average workout heart rate, and your Health-recorded body weight |
| Readiness | A score from 0 to 100, its band label, and whether Health data contributed |
| Fatigue | A plain-text fatigue summary and any deload recommendation |
| Milestones | A one-line note when you level up, and the outcome of a set the coach logged for you |

Your conversation history for the current chat is sent with each turn, because that is how a conversation works.

**What the coach is never told.** Your name, your email, your user id, your device id, your age, your height, your biological sex, your home address or coordinate, your friends, your competition standings, your trophies, and your raw sleep, resting heart rate, or HRV readings. Your hand-entered bodyweight is not sent either — only a body mass figure that came from Apple Health.

**A caution worth stating plainly.** The profile fields — goals, experience, and especially **injuries** — are free text that you wrote. Whatever you type there goes to your AI provider. If you record a medical detail in the injuries field, that detail is part of the coach request. Bear that in mind when filling it in.

**Voice.** Speech is transcribed by Apple's on-device speech recognition where the device supports it. Only the resulting text is sent to the coach; audio never reaches our servers.

**Your controls.** Nothing goes to the coach until you have acknowledged the disclaimer and turned on AI data sharing. Turning that setting off stops all coach requests. Removing your key turns the coach off entirely — it does not silently fall back to the shared coach; using that is a separate, deliberate choice you make in Settings.

---

## Fitbit

Optional, off unless you connect it. It exists for people who track sleep with a Fitbit rather than an Apple Watch, because Fitbit does not write into Apple Health.

You authorize it through Fitbit's own sign-in page, using PKCE with no client secret. There is no server in the path: your phone talks to Fitbit directly. The app requests two scopes, `sleep` and `heartrate`, and nothing else. Your Fitbit tokens are stored in your device's Keychain, marked not to sync to iCloud, and are never sent to our servers.

The app pulls sleep stages, resting heart rate, and heart rate variability, holds them in memory only, and folds them into your readiness score. Nothing from Fitbit is written to the app's database, and no Fitbit reading is ever sent to the AI coach or to our server. The coach sees only the readiness number.

Disconnecting clears the tokens from your Keychain immediately and asks Fitbit to revoke them. The local clearing always happens; the revocation is a best-effort network call, so if you disconnect while offline you may also want to remove the app from your Fitbit account settings.

Fitbit is only active in builds configured with a Fitbit connection. If the
App integrations screen in your copy of the app shows Fitbit as unavailable,
none of this section applies to your data.

---

## Home location and Adventure journeys

The Adventure tab can turn your walking and running mileage into a trip outward from home. Setting a home is optional; without it the feature falls back to fixed comparisons like marathon counts and needs no location at all.

**The app does not use location services.** There is no GPS access, no `CLLocationManager`, and no location permission prompt, because it never asks the device where you are. Instead you type an address or a town name into a text field.

That typed text is converted to a coordinate by Apple's system geocoder, which means **the text you type is sent to Apple** the same way it is when you search in Maps. The app discloses this at the point you type it.

Once converted, **only the latitude and longitude are saved, never the address text.** The app displays it back to you rounded to roughly a mile. The coordinate is used in exactly one place, to compute how far along a journey you are, and it is deliberately excluded from the coach context, the widget, the data export, and every server request. We verified all four.

---

## What we store on our server

The server exists only for Compete. If you never sign in, you have no record on it at all.

**Signing in.** Sign in with Apple gives us a stable identifier Apple generates for this app, which is what we store as your account. Apple may also send an email address; the app receives it and **deliberately discards it — no email address is written to our database**, so we hold no way to email you. You may supply a display name.

**What your account record contains.** An internal id, the Apple identifier, your display name, your public handle if you set one, and your avatar id.

**Avatars are not photos.** There is no photo upload. An avatar is one of 256 preset combinations of a system icon and a colour palette, stored as a short text id and validated against that fixed list.

**What else is stored, and why.**

| | |
|---|---|
| Sessions | Your sign-in sessions, including a hash of the refresh token (not the token), plus the IP address and device user-agent of the sign-in |
| Sharing settings | Which metrics you have chosen to share, and with whom |
| Friends | Who you are friends with, and unredeemed invite codes |
| Challenges | The challenges you are in, their format and metric, your goal, and your state |
| Cheers | Which of four fixed emotes you sent to whom. There is no free-text messaging between users anywhere in this app |
| Metric values | The activity numbers for the metrics you compete on, as individual entries and as daily totals |
| Trophies | Placement, medal, metric, score, and the display name you had at the time |
| Leagues | Your division, weekly score, rank, and outcome |
| Feedback | Anything you submit through the in-app feedback form (see below) |
| Audit records | A log of security-relevant actions on your account — sign-ins, friend changes — with your id, IP address, and user-agent |

**What is never on our server.** Your workouts, sets, weights, programs, coach conversations, sleep, resting heart rate, HRV, body weight, injuries, goals, birth year, and home coordinate.

---

## Who can see what

- **Private by default.** Every metric starts private. Nobody sees any of your numbers until you change a setting. This is structural rather than a stored default: with no sharing row, the answer to "can this person see it" is no.
- **Friends** see your display name, avatar, and the specific metrics you set to friends-level sharing, plus standings in challenges you are both in. Friends are added by invite code only; there is no directory or user search.
- **Challenges** are visible only to their participants. Someone who is not in a challenge cannot see that it exists, even if they are your friend.
- **Global leagues** are opt-in and require you to pick a public handle first. Global boards show **only** your handle, avatar, score, and rank — never your display name. There is an automated test in the codebase asserting that no global response can serialize a display name or the Apple identifier. Global boards do also carry your internal account id, which is a random string not derived from your Apple identifier, but it is stable and visible to others in your cohort.
- **Turning global sharing off removes you from leagues immediately.**

---

## Feedback you send us

The in-app feedback form sends: a category, your message, and optionally a screenshot you attach. It also sends technical context that the form shows you before you send — app version and build, device model, iOS version, the screen you were on, the last few screens you visited, your locale, timezone, free disk space, and uptime.

You can send anonymously. When you do, the decision is made on the server, not trusted to the app: no account id and no name is written to the record.

Screenshots are stored in the same database as the rest of the feedback, not in a public bucket, and are never shown to other users.

For triage, feedback submissions are also copied to a private spreadsheet
accessible only to the developer. When you delete your account, the identifying
fields of your rows in that copy are removed as part of honoring the deletion.

---

## What we do not do

- **No advertising.** No ad SDKs, no ad identifier, no IDFA access.
- **No analytics or crash reporting.** No Firebase, no Sentry, no Amplitude, no Mixpanel. The app has no third-party dependencies of any kind — every dependency is Apple's own framework or first-party code in this repository.
- **No tracking.** The app does not collect data about you for advertising or measurement, does not link your activity to third-party data, and does not use the App Tracking Transparency framework because it has nothing to ask for.
- **No data brokers, no sale, no sharing for cross-context advertising.**
- **No push notifications.** Reminders are scheduled locally by your phone. The app has no push entitlement and never registers with Apple's push service, so we cannot send you anything.

---

## Getting your data out

Settings has an "Export workout history" option that writes your profile, programs, and full workout history — every set, rep, and weight — to a JSON file you can share or save wherever you like. It does not include your chat history, body weight, birth year, or home location.

The export file is written to a temporary folder on your device. iOS clears that folder periodically, but the app does not delete the file immediately after sharing.

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

It also deletes from Apple Health the workouts this app wrote there, leaving anything recorded by other apps or your watch untouched. If Fitbit is connected it disconnects it, and asks Fitbit to revoke the token as well as clearing it locally.

**What it does not do is delete your account on our server.** It signs you out of that account on this device, but the account itself and everything listed under "Delete account" below survive, and signing in again brings you back to the same one. The two controls are deliberately separate, and you are free to use both.

**"Delete account" (Settings).** Deletes your account on our server. This is deliberately separate: your on-device workouts survive it. It removes your profile, your handle and Apple-identifier records, your sessions, your sharing settings, your friendships in both directions, your invite codes, your metric values and daily totals, your league enrolments and memberships, your challenge participations, and your change history. Challenges you created are removed along with their rosters and cheers.

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
- There is **no photo sharing between users**. Avatars are preset icons. The only image upload anywhere is a screenshot you attach to feedback, which goes to the developer and to no other user.
- There is **no user search or directory**. Friends are added only by an invite code shared out of band.
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
- Health metrics to the competition server, and the gate that reads nothing unless you have joined: `ios/AIWorkout/Core/Competition/MetricSyncService.swift:84-85, 119-121, 169-191, 201-212`
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
- PKCE, no client secret, scopes `sleep` and `heartrate`, redirect `aiworkout://fitbit-auth`: `ios/AIWorkout/Core/Integrations/Fitbit/FitbitOAuth.swift:54`, `FitbitConfig.swift`, `ios/Config.xcconfig:43`
- Tokens in Keychain, this-device-only: `ios/AIWorkout/Core/Integrations/Fitbit/FitbitTokenStore.swift:36-58`
- Endpoints and fields pulled; memory-only, no persistence: `ios/AIWorkout/Core/Integrations/Fitbit/FitbitAPI.swift`, `FitbitManager.swift`
- Coach sees only score/band/flag: `TrainerContextBuilder.swift:192-197`
- Disconnect clears locally then attempts revocation: `FitbitManager.swift` `disconnect()`
- Inert without a client id: `FitbitConfig.isConfigured`, `ios/Config.xcconfig:38`, `ios/AIWorkout/Features/Settings/IntegrationsSettingsView.swift:37, 104, 157-158`

### Home location and journeys
- Typed address only, no `CLLocationManager` anywhere: `ios/AIWorkout/Features/Adventure/HomeLocationEditor.swift`
- Geocoding call: `HomeLocationEditor.swift:172`; in-app disclosure at `:124-130`; displayed rounded at `:197`
- Only the coordinate persisted; address held in view state and cleared: `ios/AIWorkout/Models/AppSettings.swift:153-157`, `ios/AIWorkout/Features/Adventure/JourneyBridge.swift:38-51`
- Single consuming read site: `JourneyBridge.swift:28-29` (plus an `onChange` observation at `ios/AIWorkout/Features/Adventure/AdventureView.swift:112-113` that does not forward the value)
- Absent from coach context (`TrainerContextBuilder.swift`), widget (`ios/AIWorkout/Core/WidgetSnapshotWriter.swift`), export (`ios/AIWorkout/Features/Settings/WorkoutDataExport.swift`), and all server payloads (no matches in `backend/`, `server/`, `ios/AIWorkout/Core/Competition/`)
- Recap reduces to name/place/distance before the engine: `AdventureView.swift:231-236`
- No location usage string, no location entitlement: `ios/AIWorkout/Info.plist`, `ios/AIWorkout/AIWorkout.entitlements`

### On-device storage
- Eleven SwiftData models: `ios/AIWorkout/Debug/AppModelContainer.swift:13-25`
- Local-only container, no CloudKit argument and no CloudKit entitlement: `AppModelContainer.swift:38`; entitlements files
- Widget snapshot contents (no name, no identifier, no raw health values): `ios/Shared/WidgetSnapshot.swift:12-38, 124-137`
- Three Keychain items, all this-device-only: `AICoachConfig.swift:107-133`, `ios/AIWorkout/Core/Competition/TokenStore.swift:18-44`, `FitbitTokenStore.swift:36-58`
- Install identifier is local and only hashed locally: `ios/AIWorkout/Core/AvatarIdentity.swift:21-22`
- Export contents: `ios/AIWorkout/Features/Settings/WorkoutDataExport.swift`
- Local notifications only; no `aps-environment`, no remote-notification registration: `ios/AIWorkout/Features/Notifications/NotificationScheduler.swift:6-9`, entitlements files
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
- Apple email received and discarded; no email field exists on the user record: `server/src/apple.ts:81-86`, `server/src/app.ts:187-190`, `server/src/users.ts:12-35`, `server/src/store/types.ts:33-48`
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
- Cryptography limited to SHA-256 for PKCE and the Sign in with Apple nonce: `ios/AIWorkout/Core/Integrations/Fitbit/FitbitOAuth.swift:54`, `ios/AIWorkout/Features/Account/AccountSignInView.swift:104`
- Refresh tokens hashed server-side: `server/src/crypto.ts`
- No birthday collected; optional birth year is local only: `ios/AIWorkout/Features/Settings/ProfileEditorView.swift:69-75`, `ios/AIWorkout/Models/ProgramModels.swift:34`, used at `ios/AIWorkout/Features/Tracks/TracksBridge.swift:48`
