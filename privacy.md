# WorkoutSmith Privacy Policy

**Effective date:** August 29, 2026
**Last updated:** 2026-09-26

---

## The short version

WorkoutSmith is a training app built with privacy in mind. It is designed so that your private information (your workouts, steps, heart rate, sleep and the rest of your health data) stays on your device, or in Apple Health if you turn that on. Some features you use with other people, such as competing, sharing and racing, need part of that data to leave your device, and each one is described below. That includes location: routes, race check-ins and race photos involve where you are, and the "Location" section explains exactly how.

- **Your training history and health data live on your device**, in the app's own storage. You need no account to use them. They are not uploaded to us unless you turn on a feature that shares part of them, and each such feature is described below.
- **Our server is there for the features you use with other people:** signing in, friends, challenges, leagues and trophies, sharing programs and workouts, routes and races, cheers and Live status, reporting and blocking, and feedback. What it stores for them is listed under "What we store on our server". That list includes the coordinates of stops on routes you build, your race check-ins, and photos you attach to routes and races, which are kept in private cloud storage. The same Amazon Web Services account also runs the relay that forwards your AI coach requests. The relay keeps no record of your conversations.
- **We do not run ads, we do not use third-party analytics or crash-reporting code, and we do not track you.** The app has no advertising identifier and contains no third-party code that could collect one.
- **We do not sell your data**, and we do not share it for advertising.
- **Diagnostic logs stay on your device unless you send them.** The app keeps a short technical log to help fix problems. It is designed to leave out personal information, and it reaches us only if you choose to attach it when you send feedback.
- **The AI coach is optional.** If you use it, a summary of your training goes to Google or Anthropic, using your own API key and billed to your own account. The "AI coach" section lists what that summary contains.
- **You can delete your data from inside the app**, without emailing anyone. A few records deliberately outlive a deleted account. They exist so that nobody can wipe a moderation record by deleting their account and signing up again, and "Deleting your data" lists every one of them.

The rest of this document is the detail behind those sentences.

---

## Who this policy is for and who we are

This policy covers the WorkoutSmith iPhone app (bundle id `com.mig1278.aiworkout`), its Apple Watch app, and its home-screen widget.

WorkoutSmith is published by Michael Lee, an individual developer based in Massachusetts, USA. For privacy questions or requests, use Send feedback in the app (Settings > Feedback), or email **workoutsmithgeneralcontact@gmail.com** if you no longer have the app.

---

## Where your data lives

Your data can be in three places, and the differences between them matter.

**1. On your devices.** This is where almost everything is kept: your profile, programs, every workout and set you have logged, your chat with the coach, your settings, XP and achievements, your saved home coordinate, and the app's diagnostic logs. If you use the Apple Watch app, the watch keeps the workout in progress and a short diagnostic log until it can hand them to your iPhone. The app does not sync any of this to iCloud and has no CloudKit configuration. If you restore a new phone from a backup, your data comes back through Apple's backup, not through us.

**2. On our server.** This is a database and private file storage in Amazon Web Services (US East, Northern Virginia). It holds what the features you use with other people need, and "What we store on our server" lists it. It does not hold your workout history, programs, coach chat, sleep, heart rate, weight or home location, except for specific parts you choose to share (a program you send to a friend, or workouts you share with a coach).

**3. With other companies, under your own accounts or through Apple.** If you use the AI coach, your requests go to Google (Gemini) or Anthropic (Claude) on your own API key. If you connect Google Sheets, your device talks to Google directly under your own Google account. Apple handles Sign in with Apple, App Store purchases, Apple Health, notifications and the map services. Each of those companies' own privacy policies govern what they do with what they receive.

---

## What stays on your device

The following are stored on your device and are not sent to our server, to the AI coach, or anywhere else, except where an item says so:

- **Your full workout history**: every exercise, set, rep, weight, reps in reserve (RIR), warm-up and rest. Parts of it leave only if you share workouts with a coach (see "Sharing your workout history with a coach").
- **Your programs**, whether generated or built by hand. A program leaves only if you send it to a friend.
- **Your chat and voice conversations with the AI coach.** The transcript is kept only on your device. Each message you send goes to your AI provider with the context described under "The AI coach", and our relay keeps no copy.
- **Your injuries, goals, experience level and equipment notes.** These go to your AI provider as part of a coach request, and nowhere else.
- **Your birth year, biological sex and hand-entered bodyweight.** These are optional and are used only for strength-standard tables on the device.
- **Sleep, resting heart rate and heart rate variability.** These are read from Apple Health and turned into a readiness score on the device. No setting in the app sends the underlying readings anywhere.
- **The training profile the app builds from your logged workouts.** This covers what you have shown you can lift, how your reps-in-reserve reports compare with what you then do, and which exercises you swap or skip. It is computed and stored on the device. If you use the AI coach, a few sentences summarising it are part of the coach request.
- **The change journal for a program a friend shared with you**, and **the changes you have kept to a plan**. These stay on your device unless you turn on share-back for that program or share your workouts with a coach, as described below.
- **Your home coordinate** for Adventure journeys.
- **Your AI provider key, your Google tokens, and your sign-in tokens**, which are held in the iOS Keychain.

---

## Apple Health

Apple Health is optional. The app works without it. You grant access from Settings one category at a time, and you can revoke it whenever you like in the iOS Health app.

**What the app reads.** With your permission it reads step count, walking and running distance, cycling distance, heart rate, resting heart rate, heart rate variability, body mass, sleep analysis, and your workouts (including swimming distance recorded on a workout). It reads workouts from every source, so workouts recorded by an Apple Watch or another app are included. How far back a read reaches is limited by what you allow Apple Health to share; on newer versions of iOS, Apple itself asks you to choose between sharing only your recent history or all of it, and the app works within whatever you choose. Two of these reads treat that history differently:
- **The journey odometer and competitions** (the Adventure tab, challenges and leagues) can show older Apple Health history as part of your journey total or a competition total, worked out on the device. Not all of that history counts toward rewards: badges, XP, milestones and other achievements are earned only from activity logged after you install and start using the app.
- **Your training profile** (including the Endurance track) reads whatever workout history Apple Health shares with the app, calculated on the device. It shapes coaching and is informational only; it never earns a reward.

**What the app writes.**
- When you finish a workout on your iPhone, the app saves it to Apple Health with its type, start time and end time. On iOS 18 and later it also saves an effort score if you rated how hard your sets were. It does not write a calorie estimate, distance, heart rate, steps or body weight.
- If you run a workout on your Apple Watch without your phone, the watch saves it to Apple Health using Apple's own workout recorder, including the active energy the watch measures.
- If you delete a workout log in the app, the matching Health entry the app created is deleted too.

**Background access.** Today the app reads Health only while you have it open. If a future version reads new Health data in the background (for example, to keep a competition total current), it will do so only within the Health permissions you have granted, and the same rules about what leaves your device will apply.

**What leaves your device.** Health data leaves your device only when you use one of these features:

*a) The AI coach.* The coach's context includes today's step count, an average workout heart rate, your Health-recorded body weight, and your readiness score as a single number. If you wear an Apple Watch running the WorkoutSmith watch app during a workout, it also includes your heart rate at that moment and which heart-rate zone you are in. That live reading is held in memory for the session only. It is not saved to the app's database or sent to our server.

*b) Competing or sharing an activity metric.* The app uploads daily totals only for metrics you have opted in, and there are three ways to opt one in:
- you **join a challenge** on that metric;
- you **enroll in a league** on that metric;
- you set that metric to **Friends** or **Global** on the sharing screen (Social, then the privacy button, then "What you share").

If you have done none of these for a metric, the app does not even read it. Setting it back to Private, leaving the league, or the challenge ending stops the uploads. The metrics that come from Health are steps, walking and running distance, running distance and running time. Uploads cover a short rolling window of recent days, so our server keeps a daily record of those totals for as long as you have an account.

*c) Live status.* If you turn Live on, your friends can see which of a small set of effort bands you are training in. The band is worked out from your heart rate on your device. Only the band is sent, never the heart rate itself.

No current setting sends your sleep, resting heart rate, heart rate variability, cycling distance or lifetime journey mileage anywhere.

---

## The AI coach

The coach is optional. Logging, the program builder, progression, Adventure and Social all work with no AI configured.

**Your key, your account.** You supply your own API key from Google AI Studio (Gemini) or Anthropic (Claude). It is stored in your device's Keychain, set so that it does not sync to iCloud Keychain and is not included in backups. It is never written to a log or stored on our server. It is used only as the credential on your own coach requests. We do not run a coach on our own account, and the relay refuses any request that arrives without your key.

**How a request travels.** Your message goes over HTTPS to a small relay we run on AWS. The relay adds the coaching instructions and forwards the request to Google or Anthropic using your key. It holds your key only in memory for that one request, and it keeps no conversation history.

**What the relay logs.** It never logs your messages or the coach's replies, not even an excerpt. When something goes wrong, it logs the shape of the failure: how long a reply was, which check it failed, and a random id for that request. If it turns a request away for going over a usage limit while you are signed in, the log line includes your account id. The relay's logs are deleted after 14 days. For rate limiting, it keeps counters keyed to your account id if you are signed in, or to your IP address if you are not. The counters expire automatically once their window closes, whether that window is a minute or a day.

**What the coach is sent.** Each message carries a context block drawn from these categories:

| | |
|---|---|
| Your profile | Your goals, fitness level, experience and injury notes, as you wrote them |
| Your preferences | Coach tone, reply length and training style |
| Your program | Program name, length, days per week, and session names and muscle groups |
| Today and recent training | Today's session with its targets; a handful of recent workouts with the reps and weights you logged; weekly volume by muscle group and similar summaries worked out from your logs |
| A workout in progress | The current exercise, set and what you have logged so far. If you are wearing the watch app, also your heart rate at that moment and your heart-rate zone |
| Health and readiness | Today's step count, an average workout heart rate, your Health-recorded body weight, and your readiness score and band |
| Fatigue and milestones | A plain-text fatigue summary and any deload recommendation, level-ups, and the outcome of anything the coach logged for you |
| Where a program came from | A marker when a plan came from a friend or a spreadsheet, so the coach treats that text as a label and never as an instruction. It never carries the other person's name or any detail about the file |
| What the app has learned about you | A few sentences summarising patterns in your logged workouts |

Your conversation so far in the current chat is sent with each turn.

**What the coach is never sent.** None of the following leaves your device for the AI coach: your name, email, user id or device id; your age, height or biological sex; your home address or location; your friends, standings or trophies; your raw sleep, resting heart rate or HRV readings; your hand-entered bodyweight.

**A caution.** The profile fields, especially **injuries**, are free text you write, and whatever you type there goes to your AI provider. If you record a medical detail there, it is part of your coach requests.

**Voice.** Speech is transcribed by Apple's on-device speech recognition where your device supports it. Only the text is sent to the coach. Audio never reaches our servers.

**Your controls.** Nothing goes to the coach until you have accepted the disclaimer and turned on AI data sharing. Turning that off stops all coach requests. Removing your key turns the coach off completely.

---

## Location

This section describes how the app uses location today. If a future version uses location differently, this policy will say so before that version is released (see "Features we may add, and changes to this policy").

**What is true everywhere in the app today.** The app does not track your location continuously or in the background. It asks iOS only for "while using the app" permission, not "always", and it reads your location only when you tap something that needs it. Each read is a single position fix, not an ongoing session. Saying no costs you nothing outside the features that need location. You can set a home by typing an address, move the map by typing, and place route stops by address or by tapping the map.

Some of these reads are kept nowhere. Others become part of something you share with other people, and those do reach our server. Here is each one.

### Your home, for Adventure journeys

Setting a home is optional. **You type an address or a town; the app does not detect it.** Apple's system geocoder converts the text to a coordinate, which means **the text you type is sent to Apple**, just as it is when you search in Maps. Only the latitude and longitude are saved, never the address text, and they stay on your device. The coordinate is used only to measure your progress along a journey. It is not included in coach requests, the widget, the data export or anything sent to our server.

### The map's location button

The Adventure map has a button that centres the map on where you are. It reads your location once per tap and keeps the result only while the map is on screen. It is not saved, sent to our server, given to the coach, or included in an export. The first tap shows the standard iOS permission prompt.

### Route stops, including "use where I am"

When you build a route, each stop is a coordinate. You can place a stop by typing an address, by picking a point on the map, or by tapping **use where I am**, which takes a single position fix at that moment. **A route's stops, with their coordinates, names and notes, are saved on your device, and they are sent to our server when you share the route or use it for a race.** That is what makes it possible for other people to load it.

So a stop placed with "use where I am" records where you were when you placed it. **The people you share a route or race with can see its stops on a map.** A route's first stop is often where its author started, so if you begin a route at your front door, your front door is on the route. Place that stop somewhere else if you would rather it was not.

### Checking in during a race

Reaching a stop in a race is a check-in. Your phone takes a single position fix and compares it with the stop **on your device**. It then sends **which stop, when you reached it, and whether your phone's fix agreed**. It does not send your coordinates, the fix's accuracy, or your distance from the stop, and our server refuses a check-in that includes them.

**What other people in the race can work out.** They can see the route, and they can see that you reached stop four at 9:52. Together, that tells them which points on the course you reached and at what time. That is how a race board works. It is not a background track of your day, but it is location information about you, and you should know that before you race.

### Photos taken during a race

Race photos are not switched on yet. When they are, this is how their location is handled. A race photo's embedded data usually includes the time it was taken and often where. **Your phone reads that on the device**, compares the location with the course, and sends only the result (on the course, off the course, or no location) together with the time the photo was taken. The embedded data is then removed before the photo leaves your phone. Our server never receives the photo's coordinates. See "Photographs taken during a race".

### Searching the map

- **Typing an address** to move the map sends that text to Apple's geocoder. Nothing is saved.
- **"What's nearby"** sends the area shown on your screen to Apple's local search, and shows you parks, museums and similar places. We store nothing from it.
- **Searching for a place or getting directions** between stops uses Apple's map services in the same way.

All of these go to Apple as system services, as they do in Maps. **None of them goes to our server**, and none carries your account or name.

---

## What we store on our server

If you never sign in, our server has no account record for you. The only things it can hold from you are feedback you send and short-lived rate-limit counters.

**Signing in.** Sign in with Apple gives us a stable identifier that Apple creates for this app, and that identifier is your account. You may also give a display name.

**Your email address.** Apple also sends an email address when you sign in. **We do not store it.** We store a *keyed fingerprint* of it instead: the address run through a one-way function with a secret key that is kept outside the database. The fingerprint cannot be turned back into your address, and we have no way to email you. It exists so that a friend who already knows your address can send you a friend request.

**Friend requests by email.** When you send one, the address you typed is fingerprinted the same way and compared with our records.
- **You are never told whether that address has an account.** The reply is identical either way, so this screen cannot be used to find out who uses the app.
- **If it matches nobody, we keep the fingerprint (never the address) for up to 30 days**, so the request is waiting if that person signs up. It arrives as a request they can accept or decline. It is deleted once used, when it expires, or when you delete your account. No email is ever sent.

**Your account record** contains an internal id, the Apple identifier, the email fingerprint, your display name, your public handle if you set one, and your avatar id. **Avatars are not photos:** they are one of a limited set of preset icon-and-colour combinations.

**What else is stored, and why.**

| | |
|---|---|
| Sessions | Your sign-in sessions: a hash of the refresh token (not the token itself), plus the IP address and device user-agent of the sign-in. Kept until the session expires, at most 90 days |
| Sharing settings | Which metrics you share and with whom, and your **Live** setting |
| Live status | Only while you are training with Live on: that you are training, the kind of activity, and one of a small set of effort bands. It does not include your heart rate or your location. It expires a short time after your last logged set and is deleted as soon as you turn Live off |
| Friends | Your friends, unused invite codes, pending friend requests, and email fingerprints for requests to addresses with no account yet (kept 30 days) |
| Challenges and leagues | The challenges you are in (format, metric, goal and your standing), and your league division, weekly score, rank and outcome |
| Cheers | In a challenge: which of our fixed set of cheers you sent, and to whom. Between friends: the emote is not stored. The recipient's activity feed records that you cheered them, and a marker records that today's bonus has been used. There is no free-text messaging between users anywhere in this app |
| Metric values | The activity numbers for the metrics you compete on or share, as individual entries and daily totals |
| Daily goals | The daily step goal you set for the friends board. It is used to work out your own percentage and is shown to nobody else |
| Trophies | Placement, medal, metric, score, and your display name at the time |
| Groups | Friend groups you create or join: the group name, members, owner, and whether members can invite others |
| Programs and workouts you share | A program you send to a friend; if you turn on share-back for a program you adopted, a summary of how your sessions went; and, if you share your workouts with a coach, a summary of each workout you finish (see "Who can see what") |
| Routes and races | Routes you build (name, stops with their coordinates, names, short notes and links, and distances) and the races run on them (name, activity, schedule, settings, who is racing and who invited whom). Each check-in records which stop you reached, when, and whether your phone's fix agreed. Check-ins carry no coordinate: the only coordinates on our server are the route's stops |
| Route photographs | Pictures you attach to a route stop. Kept in private cloud storage, with embedded location and camera data removed on your device and refused by the server if any is left. Screened automatically, as described under "Photographs taken during a race". Shown through short-lived links to the people you share the route or race with, and deleted after you delete the route |
| Race photographs | Not switched on yet. When available: pictures added during a race, kept in the same private storage with embedded data removed. With each one we keep which stop it belongs to, the time it was taken, whether your device judged it on the course, and who you chose to show it to. Deleted six months after the race ends |
| Passport stamps | Which landmarks your walking and running distance has reached, and when. Landmarks are milestones from a fixed catalogue built into the app. No coordinate of yours is stored |
| Notification devices | Only if you turned on notifications about other people: a device token from Apple for each phone you use. It addresses notifications to that phone and identifies nothing else. Deleted when you turn notifications off, sign out, or delete your account, and 90 days after you last opened the app |
| Notification settings | Which kinds of notification you want, and your device's UTC offset, so that nothing arrives in the middle of your night |
| Reports, blocks and moderation | Reports about photographs and other content, your block list, an organizer's own ban list, records of race removals, and records of account suspensions. Each is described under "Races" and "If an account is suspended" |
| Apple purchase link | If you are signed in on iOS 18.4 or later, the identifier Apple assigns to your copy of the app (the app transaction id), linked to your account, so that a subscription can be matched to your account. See "Your subscription" |
| Feedback | Anything you send through the feedback form, including a diagnostic log if you choose to attach one (see "Feedback you send us") |
| Security records | A log of security-relevant actions on your account, such as sign-ins and friend changes, with your account id, IP address and user-agent. Kept 90 days. A few records (an account deletion, a moderation decision, a preserved photo) are kept longer without the IP address or user-agent |
| Rate-limit counters | Short-lived counters keyed to your account id or IP address, used to stop abuse. They expire within two days |

**What is not on our server.** No setting uploads your coach conversations, sleep, resting heart rate, HRV, body weight, injuries, goals, birth year or home coordinate. Your workouts and programs are uploaded only when you choose to send a program to a friend or share your workouts with a coach. Nothing on this list leaves your device by default.

---

## Notifications

**Workout reminders are local.** You choose the days and time in Settings, your phone schedules them, and nothing about them is sent anywhere.

**Notifications about other people are opt-in and come from our server.** These tell you someone invited you to a challenge or race, asked to be friends, cheered you on, or that a challenge has finished. They are **off until you turn them on**, and the app asks only after something has happened that one of them would have been about.

- **Turning them on registers your device with Apple**, and we store the device token against your account so we can address notifications to it. Nothing in the service looks up who a token belongs to. Tokens are deleted when you turn notifications off, sign out, delete your account, 90 days after you last opened the app, or when Apple tells us the device is gone.
- **We store your device's UTC offset** so that nothing arrives during your nighttime hours. It is a number of minutes, not a place. If it is missing, we skip quiet hours rather than guess your timezone from your IP address.
- **A notification contains** what happened, who did it, and which challenge or race it concerns. It does not contain anyone else's numbers, standings or location.
- **You choose which ones** you get, each has its own switch in Settings, and each has a daily cap.
- **We do not send marketing notifications**, and we do not hold your email address.

---

## Who can see what

- **Private by default.** Every metric starts private, and nobody sees your numbers until you change a setting.
- **Friends** see your display name, avatar, the metrics you share with friends, and standings in challenges you are both in. You add friends in only two ways: with an invite code you share yourself, or with a request to an email address you already know. **There is no directory and no user search.**
- **A declined friend request tells the sender nothing.** From their side, the request simply stays sent.
- **The friends board** shows, for each metric you set to Friends, your total for recent days, how many of those days had a total, and how much of your own daily goal you reached. It never shows your goal itself.
- **Live** is a separate setting, **off by default**, and limited to friends; there is no public version. With it on, friends see that you are mid-workout, the kind of activity, and one of a small set of effort bands: easy, steady, moderate, hard or peak. It does not include your heart rate, any number, or your location. With it off, nothing about your session is sent at all. Each update lasts only a short while, turning Live off deletes what is stored, and no history is kept.
- **Cheers.** A friend can send you one of a fixed set of cheers we provide (never free text), and the first one each day adds a small XP bonus to your Adventure profile. The bonus is worked out on your phone and is left out of anything ranked, so cheers cannot change standings.
- **Challenges** are visible only to the people in them.
- **Global leagues** are opt-in and need a public handle first. Global boards show **only** your handle, avatar, score and rank, never your display name. They also carry your internal account id, which is a random string not derived from your Apple identifier, but it is stable and people in your league group can see it. Turning global sharing off removes you from leagues immediately.

### Programs shared between friends

- **A shared program is a copy.** When you adopt a program a friend sent, you get your own copy, and nothing you do to it reaches the author unless you turn on share-back.
- **What travels with a program** is its name, days, exercises, and prescribed sets, reps, loads, rest and notes. Nothing about you goes with it.
- **Share-back is off unless you turn it on**, separately for each program you adopt. When it is on, the author sees how many sessions you completed against the plan, what you lifted compared with what they wrote, which exercises you changed or skipped and who changed them, and your best sets on that program. They never see your other training, coach chat, health data, readiness, bodyweight or location. **Turning it off deletes the summary** from our server.
- **Text other people write is treated as untrusted.** When a program's name and notes are shown to your AI coach, they are marked as written by someone else, so the coach treats them as a label and never as an instruction.

### Sharing your workout history with a coach

You can give one specific friend permission to see the workouts you finish, which is what a personal trainer and client want.

- **It is per person, off by default, and only for friends.** You turn it on for a named person yourself.
- **It applies only from the moment you turn it on.** Each workout you finish after that is sent to that person as a summary: the exercises, the sets you completed with their weights, times and distances, and anything you skipped. Warm-ups, reps in reserve, notes and health data are never included. Earlier workouts are never sent, and our server refuses them.
- **Plan changes travel with the workout they happened in.** If you swapped, added or re-targeted an exercise, the summary shows what the plan asked for, what you did instead, and whether you or your coach made the change. If you change nothing, nothing about your plan is sent.
- **Turning it off deletes everything they were shown.** So does removing them as a friend, or either of you blocking the other. We keep only your most recent shared sessions per person.

---

## Races

A race is a route, a schedule, a roster, and the check-ins people make along the way. Check-ins are described under "Location".

### Photographs taken during a race

Race photographs are not yet switched on for everyone. When they are available, this is how they work.

**Who can add one, and when.** Only someone on the race's roster, while the race is running or for a short time after it ends. Anyone who can see a photo can download it.

**Your phone checks the photo before it sends anything.** It reads the photo's embedded time and location **on your device**, compares the location with the course, and sends only the verdict: on the course, off the course, or no location. It then removes all embedded data. **Our server never receives the photo's coordinates**, and it rejects an upload that tries to include them. The time the photo was taken is sent, and the server checks that it falls within the race. A photo with no location is not treated as suspicious. It goes to the organizer to approve, and if the organizer does not review photos, it is refused.

**Every photo is screened automatically**, including the organizer's, by an automated classifier from Amazon Web Services that checks for nudity, violence and similar content. Route stop photos are screened the same way. **A photo that fails screening is never stored.** It is checked in memory, nobody (including us) ever sees it, and there is no appeal queue. We keep only a note of the broad category, whose upload it was, when, and how many times that account has had a photo blocked. The organizer is told that it happened, but never sees the image.

**You choose who sees your photo:** your friends in that race (the default) or every attendee. If the organizer turned on review, your photo is visible only to you and the organizer until they approve it, and it is deleted after two weeks if nobody does. If an organizer removes you from a race, the photos you added to it are deleted.

**Reporting.** Anyone who can see a photo can report it by choosing one of a small set of broad reasons. There is nowhere to type. A reported photo is **hidden from everyone immediately** until the organizer decides whether to restore it or take it down. **The organizer is never told who reported it.** While a report is open, the photo's file is kept, hidden from everyone, even if a deletion schedule would otherwise remove it. That is because the law can require content connected to a report to be preserved. This is the one exception to the photo-deletion promises on this page.

**Blocking.** You can block someone from their photo in a race, and unblock them in **Settings > Blocked people**. Blocking works in both directions and everywhere: each of you stops seeing the other's photos, cheers, shared programs, shared workouts, routes and friend requests, any workout sharing between you ends and what was shared is deleted, and a friendship ends (unblocking does not restore it). On leaderboards and rosters, the blocked person appears as a nameless "Hidden participant", with scores intact, so rankings stay true. **Nobody is told they have been blocked.**

**Retention.** Photos are deleted six months after the race ends. **If you want to keep a picture, download it** within that time. Race results (who ran, who reached which stop, finishing order and standings) are kept as long as your account, so your history and trophies stay accurate.

**What screening does not do.** The automated screener **does not detect child sexual abuse material**, and nothing here claims that it does. If you ever see anything of that kind in this app, report it to the National Center for Missing and Exploited Children at **report.cybertip.org**, and do not download, screenshot or forward it.

### Being removed from a race, and what we record

**An organizer can remove anyone from their race** without giving a reason, and can keep their own list of people barred from every race they run. That list is visible only to them, and it is deleted when either account is deleted.

**We keep a minimal record of each removal:** the Apple identifier of the removed account, the race, the organizer and the time. It has no reason and no content. **Removals by several different organizers can get an account banned from WorkoutSmith.** Repeated removals by the same organizer count once. This rule is also in the community rules you accept in the app.

**This record outlives account deletion**, because a record that disappears when you delete your account and sign up again would protect nobody.

---

## If an account is suspended

**We can suspend an account from WorkoutSmith**, for example when a report of objectionable content or abuse turns out to be right. A suspended account cannot sign in, and any signed-in device stops working immediately. Its race photos are taken down, except that the organizer of the race can still see them and delete them. A suspension does not remove the account's name from past rosters or leaderboards, because those record a competition other people were in.

**We keep a record of the suspension**: the Apple identifier, the account id and handle at the time, a short internal note on why, who decided, and when. It holds nothing about what was posted. **It outlives account deletion**, so that deleting and signing up again does not undo it.

**A suspension can be lifted.** If you think yours is a mistake, the in-app feedback form still reaches us from a suspended account, or you can email the address at the end of this page.

### Reports about other content

Anyone can report something that is not a photo, such as a shared plan or route, a workout, a friend request, or the name on a challenge, group, race or person, by choosing one of the same small set of broad reasons. We store what kind of thing it was, which one, who reported it, whose it was, the reason, when, and what was decided. We also keep **a short copy of the reported text**, so the report still makes sense if the content is later changed or deleted. When reports need attention, the developer receives a shorter excerpt by email alert. **Nobody is ever shown who made a report**, including the person reported and whoever reviews it. **These reports outlive both accounts**, for the same reason as removal records.

---

## Feedback you send us

The in-app feedback form sends a category, your message, and a screenshot if you choose to attach one. It also sends technical details that the form lists before you send: app version and build, device model, iOS version, the screen you were on and the last few screens you visited, your locale and timezone, free disk space, uptime, and whether your AI key passed its checks (never the key itself).

**You can send feedback anonymously.** Our server makes that decision, not the app: no account id or name is written to an anonymous report.

**Where it goes.** Feedback, including any screenshot, is stored in our database and is never shown to other users. For triage, it is also copied to a private spreadsheet that only the developer can access, and screenshots are copied to a private Google Drive folder linked from it. Neither is shared by link or public. When you delete your account, your name and any screenshot are removed from our database straight away, and from the spreadsheet and the folder within 30 days.

**How long we keep it.** Feedback, including any screenshot or diagnostic log attached to it, is kept for 12 months after you send it and then deleted, from our database and from the triage copies.

### Diagnostic logs

The app keeps technical logs on your device to help find and fix problems. They are designed to leave out personal information, they stay on your device unless you send them, and sending them is always optional.

**What they contain.** Records of what the app did rather than what you entered, for example:
- screens opened, whether requests to our server succeeded and how long they took, sync results, and error codes;
- messages passed between your iPhone and Apple Watch, and which tools the AI coach asked to use;
- app launches, sign-ins, and App Store activity, such as the products and prices the app saw, which subscription tier you have and whether it is a trial, and shortened, scrambled forms of your account and transaction ids;
- whether location permission is granted and how accurate a position fix was, but never the coordinates themselves.

**What they are designed to exclude.** Names, handles, email addresses, passwords and sign-in tokens, health readings such as heart rate and body weight, coordinates, and anything you typed, including coach messages. Logs are filtered automatically to strip these.

**How much and how long.**
- A basic event log is kept in memory on your iPhone for up to 24 hours. Your Apple Watch keeps its own copy (the last 24 hours, plus your most recent workouts on the watch) and passes it to your iPhone automatically. It does not go anywhere else from the watch.
- A small core log of launches, sign-ins and App Store activity is always kept, whatever your settings, capped in size and kept for 7 days.
- **Diagnostic mode** adds more detail about workouts, location accuracy and network activity, kept up to 7 days and capped in size. It is **off by default in the App Store version** and on by default in TestFlight test builds. You can change it in Settings > Diagnostic mode, where you can also clear the log.
- The logs are kept in the app's own storage and excluded from device backups. The events are also written to iOS's own on-device system log.

**When a log leaves your device.** Only if you choose it:
- when you send feedback, by turning on **"Attach diagnostic log"** or **"Attach detailed log"** (both off each time you open the form; a capped number of lines is sent); or
- by exporting the log yourself from Settings > Diagnostic mode.

An attached log is stored with your feedback and copied to the triage spreadsheet. It stays with the feedback after you delete your account, and is deleted with the feedback 12 months after you sent it. **If you send feedback anonymously and attach the detailed log**, the log's scrambled account and transaction ids could let us link the report to your account, so leave the log off if that matters to you.

---

## Your subscription

WorkoutSmith offers two monthly subscriptions in the app, **WorkoutSmith Premium** and **WorkoutSmith Coach**. Both renew automatically, and neither can be shared through Family Sharing. The only difference is how many people you can coach: a small number with Premium, with no limit on Coach. A subscription unlocks starting a workout, building a program, and the competitive features. Your history and progress, the AI coach and voice trainer, Adventure, and everything in Settings (including data export and account deletion) stay available whether or not you subscribe.

**Apple takes the payment; we never see a card.** Purchases go entirely through Apple's in-app purchase system. No payment processor is built into the app, and no card number, billing address or payment credential is entered into, held by, or sent by WorkoutSmith. You manage or cancel the subscription in your Apple account settings. Apple's privacy policy covers what Apple does with the transaction.

**What we receive today.**
- Whether you are subscribed is checked on your device with Apple. So your plan keeps working when you are offline, the app keeps a small copy on your device in the iOS Keychain: which plan you have, when it renews or ends, and whether you are in a free trial. The on-device diagnostic log also records subscription events (see "Diagnostic logs"). None of this is sent to our server unless you attach a log to feedback.
- When you buy a subscription while signed in, the purchase carries an identifier derived from your WorkoutSmith account id. Apple includes it in its record of the transaction, so the purchase can be matched to your account.
- If you are signed in on iOS 18.4 or later, the app sends our server the app transaction id Apple assigns to your copy of the app, and we store it linked to your account.
- We do not currently store your subscription status, plan or expiry date on our server.
- If you attach a diagnostic log to feedback, it can include subscription details, as described under "Diagnostic logs".

**The free period is Apple's to grant.** Apple decides whether you are eligible for an introductory offer, based on your Apple ID. The app is told only whether your current subscription came from an introductory offer, so that it can show how many days are left.

**What is planned.** We are preparing to have our server keep your subscription status, received directly from Apple, so that a subscription you paid for is recognised even when your device cannot confirm it. This is not switched on yet. Before it is, this section will be updated to describe exactly what is stored and for how long (see "Features we may add, and changes to this policy").

---

## Your programs and history in a Google spreadsheet

This is an optional feature, off until you set it up. It works with files in **your own Google Drive, under your own Google account**, and it does three things:

1. **Get a blank template**, from the import screen: a spreadsheet with the columns already right, for you to fill in and import back into the app as a program.
2. **Export a program you already have**, from the Plan tab, so you can edit it or build from it in a spreadsheet, then import it back.
3. **Export your workout history**, from Settings, for example to share with a trainer. This direction only goes out: a history sheet is exported, never imported.

**You sign in to Google, not to us.** You give consent on Google's own page, in a private browser session, and we never see your Google password. The spreadsheet is created in your Drive, uses your storage, and is your file.

**One narrow permission.** The app asks Google only for access to files it creates (Google's `drive.file` permission). It cannot see or open anything else in your Drive, and it can import only spreadsheets it created itself.

**What goes out.** A history sheet has one row per set you logged: date, program, week and session, whether the session was completed, exercise and its prescription, set number, whether it was a warm-up, target and actual reps, weight, duration, distance, reps in reserve, and whether the set was completed. A program sheet, whether it started as a blank template or was exported from a program you already had, contains the plan only. **Neither sheet includes your body weight, height, birth year, home location, anything from Apple Health, measured heart rate, notes you typed, or coach conversations.** The heart-rate zone on a program sheet is a planned target, not a reading.

**What comes back.** You can import a program, whether it started as a blank template or was exported from one you already had. **You cannot import results**: a history sheet is refused. Imported text is cleaned, exercise names must match the app's catalogue, numbers are range-checked, and a program that came from a file is marked as untrusted before the AI coach sees it. The app does not record a link, file name or Google account with it.

**Our server is not involved.** Sign-in and every request to Google happen directly between your device and Google. Our server never receives the spreadsheet, its contents, its id, or your Google token. The permission gives us no access to your Google identity: we hold no Google email address, name or account id.

**Disconnecting.** Your Google token is stored in the Keychain, set not to sync to iCloud and not included in backups. Disconnecting erases it and asks Google to revoke it; if the revoke fails, you can remove the app in your Google account. **Disconnecting does not delete spreadsheets you already exported.** They are your files.

---

## What we do not do

This is how WorkoutSmith works today. If any of it changes, we will update this policy before the version that changes it is released.

- **No advertising.** No ad code, no advertising identifier, no IDFA.
- **No third-party analytics, crash reporting or tracking code.** No Firebase, Sentry, Amplitude, Mixpanel or similar. Today every part of the app is either Apple's own frameworks or our own code.
- **No tracking.** We do not link your activity with other companies' data for advertising or measurement, and we have no reason to ask for App Tracking Transparency permission.
- **No selling or renting your data**, no data brokers, and no sharing for cross-context advertising.
- **No chat, direct messages or social feed between users.** Encouragement is limited to fixed reactions.

---

## Getting your data out

Settings has an "Export workout history" option that writes your profile, programs and full workout history (every set, rep and weight) to a JSON file you can save or share. It does not include your chat history, body weight, birth year or home location. The file is written to a temporary folder on your device, which iOS clears periodically.

Your programs and history can also go to a Google spreadsheet (see above), and you can export your diagnostic log from Settings > Diagnostic mode.

To get a copy of the data our server holds about you, email **workoutsmithgeneralcontact@gmail.com** from the address associated with your account, and we will provide it within 30 days.

---

## Deleting your data

There are two separate controls, because they do different things.

**"Delete all data" (Settings)** returns your device to the state of a fresh install. It removes:
- your profile, programs and entire workout history;
- your coach chat and voice conversations;
- your XP, level and achievements;
- your saved home coordinate;
- every setting, including Health category toggles, reminders, streak history, and your AI disclaimer and data-sharing consent (so both are asked again before anything goes to a coach);
- your AI provider key, your Google tokens, and your sign-in tokens, from the Keychain;
- cached account details, sync bookkeeping, route photos, the cached friends list, the widget's snapshot, and any export file still in the temporary folder.

It also deletes the workouts this app wrote to Apple Health, leaving other apps' workouts alone.

It does not clear the diagnostic logs, which age out on their own within 7 days. You can clear them immediately in Settings > Diagnostic mode.

**It does not delete your account on our server.** It signs you out on this device, but your account survives, and signing in again brings it back.

**"Delete account" (Settings)** deletes your account on our server. Your on-device workouts are not affected. It removes your profile, handle, Apple identifier and email fingerprint records, sessions, sharing settings, friendships, invite codes, friend requests, metric values and daily totals, league and challenge participation, activity feed, the routes you shared, your places on race rosters with your check-ins and race photos, your shared programs and workouts, and your block list. Challenges you created are removed with their rosters and cheers.

**What survives account deletion, and why.**
- **Trophies stay, anonymized.** Your name is replaced with "Departed athlete" so other people's competition history stays correct.
- **Feedback you sent stays, de-identified.** Your account id, name and any screenshot are removed. The message, technical details and any diagnostic log you attached remain so that a reported bug is not lost, until the feedback is deleted 12 months after you sent it.
- **A record that an organizer removed you from a race stays, identified by your Apple identifier.** It holds the race, the organizer and the time, with no reason or content.
- **Reports someone made about something you posted stay, including a short copy of what you wrote** and an identifier for your account. They never show who reported you.
- **A record that we suspended your account stays**, as described under "If an account is suspended".
- **The link between your app transaction id and your account id stays**, so that a subscription Apple is still billing can be matched if you sign up again with the same Apple ID.
- **A record that the deletion happened** is kept, without your IP address or device details, as proof, along with the small number of moderation and security records described under "What we store on our server".

Records that survive do so because a record you could clear by deleting your account and signing up again would protect nobody. Security records otherwise expire after 90 days.

**Deleting the app** removes everything on the device, including the Keychain items. It does not delete your server account, so use "Delete account" first if you want both.

---

## Security

All traffic between the app and our servers uses HTTPS. Sign-in tokens, your AI key, and your Google tokens are stored in the iOS Keychain, set not to sync to iCloud and not to be included in backups. Our database stores a hash of your refresh token, not the token itself. Photos are stored in private, encrypted storage and served through short-lived links. Handles are cleaned of invisible and direction-reversing characters so nobody can impersonate someone on a leaderboard.

No system is perfectly secure, and this is a small independent app rather than a company with a security team. The design compensates by keeping your most sensitive data, your health data and training history, on your own device, where a breach of our server cannot reach it.

The server database keeps encrypted backups for up to 35 days for disaster recovery. Data you delete leaves those backups as they age out.

---

## Children

WorkoutSmith is not directed to children and is not intended for anyone under 13. We do not knowingly collect personal information from children under 13.

- **There is no messaging between users and no comments.** Encouragement is limited to a fixed set of reactions we provide, never free text.
- **Some text is visible to other people:** display names and handles; names of challenges, groups, routes and races; and short notes on route stops. All of it labels something rather than messaging a person, and names are checked against a list of offensive words and refused if they match.
- **Photographs.** Avatars are preset icons, not photos. Photos enter the app in three ways: attached to a route stop, added during a race (not switched on yet), or attached to feedback. Route and race photos have their embedded data removed, are screened automatically, and are shown only to people the route or race is shared with. Feedback screenshots go only to the developer. The screener **does not detect child sexual abuse material**. Report anything of that kind to the National Center for Missing and Exploited Children at **report.cybertip.org**.
- **Community rules are enforced.** Everyone accepts them before training. Anyone can report content or block another person, organizers can remove people from races, and we can suspend accounts.
- **There is no user search or directory**, and nothing is public by default. Global visibility needs a deliberate opt-in and a handle.
- **No birthday is collected.** An optional birth year stays on the device.

---

## Features we may add, and changes to this policy

This policy describes what WorkoutSmith does today. We keep improving the app, and some features we are considering would use data in new ways. For example:
- **Live location during a race or activity**, so that people in a race can follow each other's progress;
- **Keeping your subscription status on our server**, received directly from Apple (see "Your subscription");
- **Sending a complete diagnostic log with feedback** to private storage that deletes it automatically after 30 days, instead of the current capped excerpt;
- **Connecting to another third-party fitness or health service you choose to link**, on the same opt-in, your-own-account basis described in this policy;
- **Sharing more of your activity with friends**, such as cycling or walking distance, on the same per-metric opt-in you use for competitions today;
- **Reading new Health data in the background**, instead of only while you have the app open, for example to keep a journey or competition total current;
- **Revoking the app's Sign in with Apple access when you delete your account**, which means keeping a token Apple provides for that purpose.

None of these is active today. If we add one of them, or any other feature that collects a new kind of data or uses data for a new purpose, we commit to the following:
- **We will update this policy before the version that does it is released**, describing what is collected, why, who can see it, and how long it is kept, and we will update the App Store privacy details to match.
- **Anything that needs a new iOS permission**, such as continuous or background location, **will ask through the standard iOS permission prompt and will be off unless you turn it on.** Declining will not affect the rest of the app.
- **We will not use data you have already given us for a new purpose** that conflicts with what this policy says without first asking for your consent.

When this policy changes in a meaningful way, the "Last updated" date changes and the new version is posted at the same address. We do not hold your email address, so we cannot email you about changes; please check this page.

---

## Contact

Privacy and deletion requests: use **Send feedback** in the app (Settings > Feedback), or email **workoutsmithgeneralcontact@gmail.com** if you no longer have the app.

This policy is governed by the laws of the Commonwealth of Massachusetts, USA.

---
---

# Appendix: where each claim was verified

Every path is relative to the root of the app's source repository. A bare file name or short path means the app's file of that name. Line numbers were re-checked against the code on 2026-09-26.

### Apple Health
- Read types (steps, walking+running distance, cycling distance, heart rate, body mass, workouts with swimming distance, sleep analysis, resting heart rate, HRV SDNN), one toggle per category: `ios/AIWorkout/Core/Health/HealthStore.swift` (`readTypes(for:)`)
- Only one file in the app imports HealthKit: `ios/AIWorkout/Core/Health/HealthStore.swift:305`
- Write types requested (workouts, active energy, and on iOS 18+ workout effort score): `HealthStore.swift` (`shareTypes`); the phone mirrors a workout with `activeEnergyKcal: nil`: `ios/AIWorkout/Core/Health/HealthManager.swift` (`mirrorWorkout`); effort score linked to the workout when RIR was reported: `HealthStore.swift` (effort-score write)
- A standalone Apple Watch workout is saved through `HKLiveWorkoutBuilder` with an `HKLiveWorkoutDataSource`, with share types workouts and active energy: `ios/AIWorkoutWatch/WatchWorkoutSession.swift` (`shareTypes`, the `saving` branch); `STANDALONE_WATCH_ENABLED = YES` in `ios/Config.xcconfig`. The watch does no GPS: no `HKWorkoutRouteBuilder` and no CoreLocation in `ios/AIWorkoutWatch/`
- Deleting app-written workouts by stored UUID: `HealthStore.swift:878`, called through `HealthManager.deleteMirroredWorkout` from `ios/AIWorkout/Features/Workout/WorkoutView.swift:369` and `ios/AIWorkout/Features/Settings/SettingsView.swift:1023`
- Journey mileage read from the lifter's tracking start date (`TrackingWindow.Bounds.earningStart`, set in Settings): `ios/AIWorkout/Core/Health/HealthManager.swift` (`trackingBounds`, the journey read)
- The workout-history read is bounded in code, not unlimited, and the bound is a code constant rather than a policy commitment (it can change without notice to this page): `HealthStore.swift:494`, `HealthManager.swift:102, 108`
- No background delivery, no observer queries, no `UIBackgroundModes` in the iPhone app: no matches for `HKObserverQuery` / `enableBackgroundDelivery` / `HKAnchoredObjectQuery` in `ios/AIWorkout/`; `ios/AIWorkout/Info.plist`. The one anchored query in the project is the watch app's live heart-rate read during a workout the user started (`ios/AIWorkoutWatch/WatchWorkoutSession.swift:431`), under the watch's `workout-processing` background mode (`ios/AIWorkoutWatch/Info.plist:34-37`); it ends with the workout
- Usage strings (and the gap): `ios/AIWorkout/Info.plist:60-63`
- Health values in coach context: `ios/AIWorkout/Core/TrainerContextBuilder.swift:109-127, 396-415`, `ios/AIWorkout/Features/Chat/ChatView.swift:873-891`
- Live heart rate from the watch: measured in `ios/AIWorkoutWatch/WatchWorkoutSession.swift`, throttled by `ios/ProgressionEngine/Sources/WatchLink/HeartRateThrottle.swift`, held in memory only by `ios/AIWorkout/Core/CurrentWorkoutState.swift` (`recordHeartRate`, dropped past 90 seconds and on `clear()`), and reaching the coach at `TrainerContextBuilder.swift` `buildActiveSession`. It appears in no SwiftData model, no export, no widget snapshot, and no server payload
- Health metrics to the competition server, and the gate that reads nothing until you have opted a metric in: `ios/AIWorkout/Core/Competition/MetricSyncService.swift` (`activeMetrics()`, which fetches) calling `ios/ProgressionEngine/Sources/CompetitionKit/MetricUploadConsent.swift` (which decides, and is the single place the three opt-in routes are resolved). The rule is unit-tested case by case in `MetricUploadConsentTests.swift`, including that a private scope opts nothing in and that a metric keeps uploading until the *last* route to it closes.
- Upload window (a code constant, not a policy commitment): `MetricSyncService.swift` (`lookbackDays`, from `TrackingWindow.externalHistoryDays`)

### The AI coach
- Key in Keychain, `kSecAttrAccessibleWhenUnlockedThisDeviceOnly`, no iCloud sync: `ios/AIWorkout/Core/AICoachConfig.swift:122-171`
- Key sent only as a header, never logged: `ios/AIWorkout/Core/TrainerClient.swift:554-566`
- Relay uses the key per-request and does not persist it: `backend/src/app.ts:72-128`, `backend/src/providers/gemini.ts:41-47`
- Complete context struct: `ios/AIWorkout/Core/TrainerContextBuilder.swift` (whole file); rendered to prose at `backend/src/context.ts:713-777` (`renderClientContext`)
- Profile mapped to four fields only; name, sex, birth year, bodyweight, avatar, locations all withheld: `TrainerContextBuilder.swift` `buildProfile`, against the model at `ios/AIWorkout/Models/ProgramModels.swift:11`
- Consent gates before any send: `ChatView.swift:721-726, 919, 1001-1002`
- No conversation state on the server; no logging middleware: `backend/src/app.ts` (middleware list), all `console.*` calls in `backend/src`
- No message or model content in any log line: every `console.*` in `backend/src` carries a provider SDK error, a rate-limit decision, a token-verification reason, or a length/position, and none takes a message, a prompt, or a reply. The program route's failure diagnostics: `backend/src/app.ts:383-385, 424-436`; the content-free parse-failure text and why V8's own message cannot be used: `backend/src/program.ts:750-773`; validation errors are field paths and type expectations that quote no value: `backend/src/program.ts:436-748`; tests asserting nothing identifiable survives into the diagnostics: `backend/test/program-diagnostics.test.ts`
- 14-day log retention: `infra/template.yaml:1754-1760` (`TrainerProxyLogGroup`)
- Rate-limit counters keyed `u:<userId>` when signed in and `a:<ip>` otherwise, each window (minute and day) expiring shortly after it closes: `backend/src/limits.ts` (`subjectKey`, `enforceLimits`), `backend/src/ratestore.ts`; the user id appears in the refusal log line: `backend/src/guard.ts`
- On-device speech where supported: `ios/AIWorkout/Core/Speech/SpeechRecognizer.swift:69-85, 104-109`
- No server-side provider key and no path to one: `resolveRequestProvider` in `backend/src/app.ts` refuses a keyless request with `key_required` before any upstream call, and `buildProvider` cannot construct a provider without being handed a key, so there is nothing left to flag off; pinned by `backend/test/byo-key.test.ts`
- The retired shared coach, as the app now presents it: `ios/AIWorkout/Core/AICoachConfig.swift` (`AICoachChoiceStore`, read as a retirement marker), `ios/AIWorkout/Features/Settings/AICoachSettingsView.swift` (the retirement notice)
- Anthropic as a user-selectable provider: `backend/src/providers/anthropic.ts`, `ios/AIWorkout/Core/AICoachConfig.swift:12-68`

### Home location and journeys
- Typed address only: `ios/AIWorkout/Features/Adventure/HomeLocationEditor.swift`
- Geocoding call: `HomeLocationEditor.swift` `lookUp()`; in-app disclosure in `privacySection`; displayed rounded in `coordinateText`
- Only the coordinate persisted; address held in view state and cleared: `ios/AIWorkout/Models/AppSettings.swift:201-215`, `ios/AIWorkout/Features/Adventure/JourneyBridge.swift:38-51`
- Single consuming read site: `JourneyBridge.swift:28-29` (plus `onChange` observations at `ios/AIWorkout/Features/Adventure/AdventureView.swift:1264-1265` and `ios/AIWorkout/Features/Walk/WalkView.swift:500-501`, fed at `AdventureView.swift:197-198` and `WalkView.swift:155-156`, that do not forward the value)
- Absent from coach context (`TrainerContextBuilder.swift`), widget (`ios/AIWorkout/Core/WidgetSnapshotWriter.swift`), export (`ios/AIWorkout/Features/Settings/WorkoutDataExport.swift`), and all server payloads (no matches in `backend/`, `server/`, `ios/AIWorkout/Core/Competition/`)
- Recap reduces to name/place/distance before the engine: `AdventureView.swift:614-615, 640-646`

### The one-shot location read
- The only `CLLocationManager` in the repository, and the only file that owns one: `ios/AIWorkout/Core/LocationMoment.swift`
- One fix per request via `requestLocation()`, never `startUpdatingLocation()`, so the hardware stops itself and no session can be left running
- When-in-use only: `NSLocationWhenInUseUsageDescription` in `ios/AIWorkout/Info.plist`; there is no `NSLocationAlwaysAndWhenInUseUsageDescription`, no background location mode in `UIBackgroundModes`, and no location entitlement in `ios/AIWorkout/AIWorkout.entitlements`
- Refusal is a state and never an alert or a re-prompt: `LocationMoment.request()` returns early on `.denied`, covered by `testARefusalIsNeverAskedAgain`
- Nothing reads location unprompted: `testItAsksNothingUntilItIsAsked`, and the UI gate `testThePickerOffersLocationRatherThanDemandingIt`

There are three call sites for that one fix, and they end differently. The distinction is the whole of the location section above.

- **The map's centre button, which keeps nothing.** The coordinate lives only in `LocationMoment.state` and in the map screen's `@State`, both dropped in `AdventureMapScreen.onDisappear`. No key is added to `LocalDataWipe` because there is nothing to wipe: `ios/AIWorkoutTests/MapLocationTests.swift` `testTheWipeHasNothingNewToClear`. No call site passes this fix to the coach context, the widget snapshot, or the export
- **"Use where I am" in the route builder, which saves and transmits.** `ios/AIWorkout/Features/Adventure/CustomRouteBuilderScreen.swift` takes the fix and `AddRouteStopSheet.swift` turns it into a stop; it is persisted as `latitude`/`longitude` on the stop in `CustomRouteModels.swift`, put on the wire by `RoutePayloadMapping.swift`, and required server-side by `routeStopSchema` in `server/src/validation.ts`. This is a route's course geometry rather than a record of the author, but the coordinate is real and it does reach the server
- **A race check-in, which transmits a verdict and never a coordinate.** The client request is exactly five fields (`stopIndex`, `waypointId`, `at`, `verified`, `onBehalfOf`): `ios/ProgressionEngine/Sources/CompetitionKit/RaceDTOs.swift`, pinned by `ios/AIWorkoutTests/RaceWireCensusTests.swift`. Race photo uploads send `stopId`, `takenAt`, a one-word `gps` verdict and `audience`: `ios/ProgressionEngine/Sources/CompetitionKit/RaceSelfieDTOs.swift`, with the read-compare-strip order in `ios/AIWorkout/Features/Competition/RaceSelfie.swift`. `raceCheckinSchema` in `server/src/validation.ts` is `.strict()`, so a body carrying a latitude, longitude, accuracy or distance is rejected with a 400 rather than silently dropped, and no check-in row has a coordinate column. The comparison against the stop happens on the device
- **What a participant can join, and why the policy says so.** `getRaceDetail` in `server/src/races.ts` returns the route payload and the roster's check-ins in one response, and default race visibility is `participants`. `route.stops[checkin.stopIndex]` is therefore reconstructable by anyone in the race, up to the number of stops. Disclosed under "Checking in during a race"

### Map searches (Apple system services, not our server)
- Forward geocode of a typed address, discarded after use: `ios/AIWorkout/Features/Adventure/MapAddressSheet.swift`
- Nearby place lookup around the displayed region, on tap only, results held in view state and never stored: `ios/AIWorkout/Features/Adventure/NearbyPlaces.swift`
- Nothing is stored from a map search: a nearby-places result set is never written, and no place record is created from anybody's search. The landmark catalog the Adventure journeys run on is a bundled file rather than a server database: `ios/ProgressionEngine/Sources/JourneyEngine/Resources/landmarks.json`
- The places that DO reach the server are the stops on routes people author, described under "Building a route from where you are". They are stored as part of the route document that carries them and are reachable only to the people that route or race is shared with; they are not pooled, indexed, or searchable across users

### On-device storage
- The SwiftData models: `ios/AIWorkout/Core/AppSchema.swift:85-125` (`AppSchemaV1.models`, forwarded by `AppModelContainer.models`)
- Local-only container, no CloudKit argument and no CloudKit entitlement: `AppModelContainer.swift:85-92`; entitlements files
- Widget snapshot contents (no name, no identifier, no raw health values): `ios/Shared/WidgetSnapshot.swift:12-64, 164-170, 176-220`
- Four Keychain items in use: `AICoachConfig.swift:122-171` (`AICoachConfigStore`), `ios/AIWorkout/Core/Competition/TokenStore.swift:13-68`, `GoogleSheetsTokenStore.swift`, and `ios/AIWorkout/Core/Subscription/EntitlementCache.swift:81-143` (the remembered subscription tier, instantiated by `SubscriptionManager.swift:586`). The first three are this-device-only (`kSecAttrAccessibleWhenUnlockedThisDeviceOnly`); the entitlement cache deliberately is not (`kSecAttrAccessibleAfterFirstUnlock`, by design, so it survives a restore) and is not named in "Security" or cleared by "Delete all data," neither of which claims to be a complete Keychain inventory. A further this-device-only token store exists in the code for a third-party health-service integration that is hidden and cannot be connected in the shipped build, because its OAuth client id (`GOOGLE_HEALTH_CLIENT_ID`) is empty in `ios/Config.xcconfig`: `ios/AIWorkout/Features/Settings/IntegrationsSettingsView.swift:36-56`
- Install identifier is local and only hashed locally: `ios/AIWorkout/Core/AvatarIdentity.swift:17-37`
- Export contents: `ios/AIWorkout/Features/Settings/WorkoutDataExport.swift`
- Local reminders are scheduled by the device and nothing about them leaves it: `ios/AIWorkout/Features/Notifications/NotificationScheduler.swift`
- Remote notifications are opt-in, and the opt-in is our own flag rather than iOS's authorization status, so granting permission for reminders does not enrol anybody in push: `ios/AIWorkout/Features/Notifications/PushRegistrar.swift` (`OptIn`, and the invariant stated at the top of the file)
- Never asked at launch: the two ask moments are an invitation sent and a cheer received, both raised only from the Social tab: `PushRegistrar.consider(_:)` (`PushRegistrar.swift:145`), called with `.cheerArrived` from `CompetitionRootView.swift:385` and with `.sentInvitation` from `AddFriendView.swift:556`, `CreateChallengeView.swift:570`, `AddPeopleToChallengeSheet.swift:110` and `AddPeopleToRaceSheet.swift:164` in `ios/AIWorkout/Features/Competition/`
- The device token is stored keyed by a hash of itself and there is no lookup by token and no read across users: `server/src/push/tokens.ts`; the routes are scoped to the caller: `server/src/app.ts` (`/me/push-tokens`)
- Token expiry at 90 days, refreshed on each registration; dead tokens dropped when Apple reports them: `server/src/push/tokens.ts` (`TOKEN_TTL_MS`, `dropDeadToken`)
- Quiet hours applied from the device's own offset, never inferred: `server/src/push/categories.ts` (`isQuietHour`)
- Per-category switches and per-day caps: `server/src/push/categories.ts` (`CATEGORY_DEFAULT_ENABLED`, `CATEGORY_DAILY_CAP`), `server/src/push/prefs.ts`
- Every sentence that can reach a lock screen, in one file under a banned-vocabulary test: `server/src/push/copy.ts`, `server/test/push-copy.test.ts`
- No third-party packages at all: `ios/project.yml` (only the local `ProgressionEngine`), `ios/ProgressionEngine/Package.swift` (no remote dependencies)
- No ad identifier or tracking framework: no matches for `AppTrackingTransparency`, `ASIdentifierManager`, `advertisingIdentifier`, `NSUserTrackingUsageDescription` in `ios/`
- Delete-all-data implementation: `ios/AIWorkout/Features/Settings/SettingsView.swift:997-1063`; dialog copy at `:258-273`
- The stores outside SwiftData that the wipe reaches, each key named at the type that owns it: `ios/AIWorkout/Core/LocalDataWipe.swift`
- Every settings field returned to its default, including the home coordinate: `ios/AIWorkout/Models/AppSettings.swift:540-652` (`resetToDefaults()`)
- Tests: preference keys claimed and not claimed, and a settings row mutated field by field and reset: `ios/AIWorkoutTests/LocalDataWipeTests.swift`
- Delete-account implementation: `SettingsView.swift:274-301, 331-339`; token and cache clearing at `ios/AIWorkout/Core/Competition/AuthStore.swift:324-333` (`forceSignOut()`)

### The server
- Deployed store is DynamoDB, single table `aiworkout-prod`; SQLite is local development only: `server/src/lambda.ts`, `server/src/index.ts`, `infra/template.yaml:359-421, 367`
- Full entity and field list: `server/src/store/types.ts`, `server/src/store/dynamo.ts:223-896`
- Apple email kept only as a keyed HMAC under a server-side secret, never as an address; the hashing is the only thing done with it: `server/src/email-identity.ts`, `server/src/users.ts` (`upsertUserByAppleSub`, `recordEmailHash`), `server/src/store/types.ts` (`UserRow.email_hash`)
- No email address is written to any table, asserted by a test that reads every text column of every table after a request is sent: `server/test/friend-requests.test.ts` ("never stores an email address in any readable form")
- A friend request answers a match and a miss with identical bytes, an identical status and a padded identical response time: `server/src/friend-requests.ts`, `server/src/app.ts` (`POST /friends/requests`), tests in `server/test/friend-requests.test.ts` ("enumeration defence")
- An address with no account is kept only as a fingerprint, for 30 days, and converts to a request the new account may decline: `server/src/friend-requests.ts` (`convertPendingInvites`), `server/src/store/types.ts` (`PendingInviteRow`), tests "an invitation to somebody who has not joined yet"
- Declining notifies nobody and writes no change for the sender: `server/src/friend-requests.ts` (`declineFriendRequest`), test "decline is invisible to the requester"
- Global boards expose handle, avatar, score (with the total it is read from), rank, internal id, and the gap to the handle ranked just above, and no name or Apple id: `server/src/leagues.ts:790-820, 895-951`; test asserting no name or Apple id leaks: `server/test/handle-anonymity.test.ts`
- Handle required before global sharing or leagues: `server/src/app.ts:1437-1446, 3637-3646`
- Sharing private by default, structurally: `server/src/shares.ts:21-37, 63-66`, `server/src/app.ts:1385-1414`, `server/src/metrics.ts:52-57`
- Leaving global drops league enrolment: `server/src/app.ts:1456-1458` (`syncEnrollmentToScope`)
- Metric values stored per event plus daily rollups, no expiry: `server/src/metrics.ts:152-162`, `server/src/store/dynamo.ts:3315-3352`
- Cheers are a fixed preset set, no free text: `server/src/validation.ts:389-392` (`cheerSchema`)
- The free-text fields other users can see, each bounded and sanitized rather than absent: `challengeName` (optional on `createChallengeSchema` and `updateChallengeSchema`), the route and race label fields (`routeLabelText`) and stop notes (`routeNoteText`) in `server/src/validation.ts`, group names in `server/src/groups.ts`, and `display_name` and the handle on the user record. There is no message field anywhere: no route, race, challenge, group or cheer carries text addressed to a person
- Challenge detail hidden from non-participants: `server/src/challenges.ts:1222-1239`
- Avatars validated against a closed preset space: `server/src/avatars.ts`
- Handle sanitization: `server/src/handle.ts:23-41`, rationale in `server/SECURITY.md:22-43`
- Feedback fields, server-side anonymity decision, screenshot stored inline in DynamoDB (not in the route-photo bucket), attached diagnostics stored inline as the `diagnostics` attribute, line-capped: `server/src/feedback.ts`, `server/src/store/dynamo.ts` (feedback put), `server/src/validation.ts` (feedback schema, the `diagnostics` array's `.max()`). No TTL on feedback items yet: `server/src/retention.ts` (the retention-gap note). The 12-month feedback deletion stated in the policy is not yet automated and is tracked for a later build. The triage copy is written by `server/src/feedback-sheet-sync.ts`, which only appends; removing a deleted account's name and screenshot from the triage spreadsheet and folder is done by hand within 30 days until it is automated
- Account deletion: `server/src/app.ts:1313-1333`, `server/src/store/dynamo.ts:2769-2931`; trophy anonymization `server/src/trophies.ts:16`; screenshot deletion and its rationale `server/src/store/dynamo.ts:2828-2834`
- On account deletion, feedback keeps its message, context and `diagnostics`; only `user_id`, `user_label` and the screenshot go: `server/src/store/dynamo.ts` ("Anonymize feedback")
- Account deletion removes routes shared, race participation, check-ins and race photos by cascade (`server/src/db.ts`, `REFERENCES users(id) ON DELETE CASCADE`). `races.owner_id` carries no cascade, so a race an organizer created is not shown here as deleted with the organizer; not asserted in the policy
- Route stop notes are sanitized to a size cap: `server/src/route-payload.ts` (`STOP_NOTE_MAX`)
- Name fields are checked against a whole-word English blocklist and refused on a match: `server/src/text-filter.ts` (bugs #287)
- Moderation alert emails carry a size-capped snapshot: `server/src/moderation-alerts.ts` (`ALERT_SNAPSHOT_MAX`), delivered through the `ModerationAlertTopic` SNS topic in `infra/template.yaml`
- Cheers: a fixed set in challenges (`server/src/validation.ts`, challenge cheer schema) and between friends with the emote not stored and a `cheer` change-log row for the recipient: `server/src/friend-cheers.ts`
- The friends board reads only what each person volunteered, and omits a day nobody recorded rather than reporting it as zero: `server/src/friends-summary.ts`, `server/src/board-scoring.ts`, contract test `server/test/store-contract.ts` ("omits a day with no counting total rather than reporting it as zero")
- Your daily goal is never sent to anyone else: `server/src/friends-summary.ts` (`goal` is present only on the caller's own row), test `server/test/friends-summary.test.ts` ("never shows another person daily goal, only the caller own")
- Live status is not sent at all while it is off, rather than sent and hidden: `CompetitionKit/LiveRail.swift` (`PresenceGate.mayWrite`, which treats an unknown scope as private), `ios/AIWorkout/Core/Competition/PresenceService.swift` (which is the only caller), tests `LiveRailClientTests.testAnUnknownScopeIsTreatedAsPrivate` and `testPresenceIsWrittenOnlyWhenTheLiveScopeIsFriends`
- Live status carries an effort band and never a heart rate: `server/src/presence.ts` (`HR_ZONE_BANDS`), `CompetitionKit/FriendsHub.swift` (`HrZoneBand`), tests `LiveRailTests.testPresenceCarriesNoHeartRate` and `LiveRailUITests.testTheRailNeverPutsAHeartRateOnScreen`
- Turning Live off deletes what is stored in the same request: `server/src/app.ts` (`PUT /me/shares/:metric`, the `clearPresence` branch)
- Live status expires on its own after `PRESENCE_TTL_MS`: `server/src/presence.ts`, enforced from the stamp in both backends
- There is no public live rail to consent to: `server/src/presence.ts` (`LIVE_SHARE_SCOPES`), `CompetitionKit/LiveRail.swift` (`PresenceGate.scopes`), test `LiveRailClientTests.testThePickerOffersPrivateAndFriendsAndNotGlobal`
- A cheer's XP cannot move anybody's standing: `LevelEngine/XPEngine.swift` (`workoutXP` is recomputed with the boosts left out, and `workoutXP` is the only total `MetricSyncService` uploads), tests `CheerBoostXPTests.testACheerIsWorthNothingInAnyRankedTotal` and `testABoostDoesNotDisturbTheRankedTotalThroughTheDailyCapEither`
- Race photographs are held behind a server-enforced launch gate (`RACE_SELFIES_ENABLED`, `EnableRaceSelfies` in `infra/template.yaml`), recorded as `false` in prod in `CLAUDE.md`. Photo screening applies to route photos too: `server/src/route-photos.ts` (`screenOrRefuse`), `server/src/photo-screening.ts` (Rekognition `DetectModerationLabels`)
- Audit rows lack index keys, so the deletion fan-out cannot reach them; all except the `DURABLE_EVENTS` kinds expire after 90 days: `server/src/store/dynamo.ts:2029-2040` (`auditItem`), `server/src/retention.ts` (`AUDIT_RETENTION_MS`, `DURABLE_EVENTS`)
- Account suspension (Apple 1.2 "eject the user"), keyed on the Apple subject so it outlives account deletion, with no index keys for the same reason the kick record has none: `server/src/account-suspension.ts`, `server/src/db.ts` (`account_suspensions`), `server/src/store/dynamo.ts` (`accountSuspensionKey`); enforced at all three doors in `server/src/middleware.ts` (`requireAuth`), `server/src/sessions.ts` (`rotateSession`) and `server/src/users.ts` (`upsertUserByAppleSub`); tests in `server/test/account-suspension.test.ts` ("survives the account being deleted and made again with the same Apple ID") and `server/test/store-contract.ts` ("SURVIVES ACCOUNT DELETION, which is the entire point of it")
- Suspension is reachable only by the operator, never from the app: `POST /ops/moderation` behind a secret that ships in no client and lives in SSM, guarded by one prefix-mounted middleware that fails closed when the secret is unset, compares it in constant time, rate-limits per address before comparing, and audits every action durably: `server/src/middleware.ts` (`requireOps`), `server/src/moderation.ts`, `server/src/app.ts` (`/ops/moderation`), tests in `server/test/account-suspension.test.ts` ("POST /ops/moderation"). The IAM-gated break-glass path for a leaked secret is `server/src/moderation-lambda.ts` and `infra/template.yaml` (`ModerationFunction`, which has no `Events`)
- IP and user-agent captured for rate limiting and audit: `server/src/middleware.ts:24-57`, user-agent read at `server/src/app.ts:858, 947, 997`
- No analytics or telemetry SDKs; the server's dependencies are the AWS SDK, `@apple/app-store-server-library`, `hono`, `jose` and `zod`: `server/package.json`
- No bulk export route: full route list in `server/src/app.ts`
- 14-day CloudWatch retention for the world, maintenance, feedback-sync, alert-digest and proxy functions (the break-glass moderation function keeps 90 days); no API Gateway access logging; DynamoDB point-in-time recovery ON (35 days): `infra/template.yaml` (`PointInTimeRecoverySpecification`, the `LogGroup` resources)
- Development sign-in: absent from production. The deployed stack runs `EnableDevAuth=false` (`NODE_ENV=production`), under which the route at `server/src/app.ts:939-990` is never mounted; verified 2026-07-30 (`/auth/dev` returns 404, `/health` reports `devMode:false`)

### Transport and general
- HTTPS to both AWS endpoints: `infra/template.yaml:2804` and the Lambda Function URL output
- App Transport Security has only `NSAllowsLocalNetworking`, with no arbitrary-loads exception: `ios/AIWorkout/Info.plist`
- Cryptography limited to SHA-256 for PKCE and the Sign in with Apple nonce, and HMAC-SHA256 for a spreadsheet's control code (the unavailable health-service integration above has its own PKCE): `ios/AIWorkout/Core/Integrations/GoogleSheets/GoogleSheetsOAuth.swift`, `ios/AIWorkout/Features/Account/AccountSignInView.swift:193-197`, `ios/ProgressionEngine/Sources/ProgramBuilder/SheetProvenance.swift:239-243`
- Refresh tokens hashed server-side: `server/src/crypto.ts`
- No birthday collected; optional birth year is local only: `ios/AIWorkout/Features/Settings/ProfileEditorView.swift:70-78`, `ios/AIWorkout/Models/ProgramModels.swift:37`, used at `ios/AIWorkout/Features/Tracks/TracksBridge.swift:66`

### The subscription
- Two monthly products and the only difference between them: `ios/AIWorkout/Core/Subscription/SubscriptionManager.swift` (`SubscriptionTier`, `SubscriptionProduct.allIDs`: `com.mig1278.aiworkout.user.monthly`, `com.mig1278.aiworkout.coach.monthly`), `ios/AIWorkout/Core/Subscription/CoachingAllowance.swift` (`baseTierLimit`)
- What a subscription gates and what stays open regardless: `ios/AIWorkout/Core/Subscription/EntitlementStatus.swift` (`GatedSurface`, `GatedSurface.openWhenLocked`), applied by `ios/AIWorkout/Features/Paywall/PaywallGate.swift`. `MONETIZATION_ENABLED = YES` in `ios/Config.xcconfig`
- Purchase and restore are Apple's own, with no payment processor in the project: `SubscriptionManager.swift` (`PurchaseAction` via `ios/AIWorkout/Features/Paywall/SubscriptionManager+PurchaseAction.swift`, `AppStore.sync()`, `Transaction.currentEntitlements`, `Transaction.updates`)
- The purchase carries an `appAccountToken` that is the account id reformatted as a UUID: `SubscriptionManager.swift` (purchase options), `ios/AIWorkout/Core/Subscription/SubscriptionAccountToken.swift`
- The app transaction id is sent at launch when signed in on iOS 18.4+: `SubscriptionManager.swift` (`reportAppTransaction`), `ios/AIWorkout/Core/Competition/CompetitionAPIClient.swift` (`me/apple-transaction`). The server stores an `APPTXN#<id>` link row to the user id whether or not `AppleSubscriptionsEnabled` is on: `server/src/app.ts` (`POST /me/apple-transaction`), `server/src/subscriptions.ts` (`linkAppTransaction`). Link rows are deliberately outside the user partition and survive account deletion: `server/src/store/dynamo.ts` (`appleLinkKey`)
- Server-side subscription status (bugs #300) is built but dark: `AppleSubscriptionsEnabled` defaults to `'false'` in `infra/template.yaml`, and `docs/held-builds.tsv` records the live stack at `false` on 2026-09-19. What it would store: `server/src/store/types.ts` (subscription row). `GET /me/subscription` is advisory and can only widen what the device concluded: `server/src/app.ts`
- The entitlement the app gates on is not persisted: `EntitlementStatus` is a plain struct, absent from `ios/AIWorkout/Features/Settings/WorkoutDataExport.swift`, `ios/AIWorkoutWidgets/` and `ios/AIWorkout/Core/TrainerContextBuilder.swift`
- The introductory period is read off the live product: `SubscriptionManager.swift` (`IntroductoryOffer`, `refreshIntroductoryOffer()`, `isEligibleForIntroOffer`)

### Diagnostic logs
- Basic event log: fixed vocabulary, no text or values, one-word subscription state `unknown`/`entitled`/`trial`/`locked`: `ios/ProgressionEngine/Sources/DiagnosticLog/DiagEvent.swift` (`DiagEntitlementState`), `DiagScalar.swift`, enforced by `DiagVocabularyTests.swift`. Memory only on iPhone, 24 hours: `DiagRecorder.swift`, `DiagRetention.swift`. Also mirrored to the unified system log: `DiagRecorder.swift`
- Watch copy: on disk in the watch container, 24 hours plus a floor of complete sessions kept whole regardless of age (`DiagRetention.watch`, `sessionFloor`), sent to the phone over WatchConnectivity and deleted once delivered: `DiagRetention.swift`, `DiagRing.swift`, `DiagStore.swift`, `WatchLinkClient.swift`, `ios/AIWorkout/Core/WatchLinkBridge.swift`
- Diagnostic mode core (always on): launch, store and account sections, capped by launch count and size, kept 7 days, excluded from backup: `DeepLog.swift`, `DeepLogStore.swift`. Store context and hashed ids: `ios/AIWorkout/Core/Subscription/StoreDiagnostics.swift`, `SubscriptionManager.swift`, `ios/AIWorkout/Core/Competition/AuthStore.swift`
- Diagnostic mode heavy sections (workouts, running/GPS accuracy bands, network): capped in size, kept 7 days: `DeepLogStore.swift`; GPS lines carry permission, precise flag, accuracy band and fix age only: `ios/AIWorkout/Core/LocationMoment.swift`
- Default on for TestFlight (sandbox app transaction), off for the App Store, the user's choice wins: `ios/AIWorkout/Core/Diagnostics/DiagnosticModeLaunch.swift`, `DeepLog.swift`; Settings row and toggles: `ios/AIWorkout/Features/Settings/SettingsView.swift`, `ios/AIWorkout/Features/Diagnostics/DiagnosticModeView.swift` (export and clear)
- Redaction by field name and by pattern (emails, tokens, JWTs, long digit runs, 4+ decimal numbers, health readings): `DeepLogRedactor.swift`, tests in `DeepLogTests.swift`. Ids are hashed with unsalted 32-bit FNV-1a for correlation, not secrecy: `DeepLogRedactor.swift`
- Feedback attachment: two toggles, both off per report; line- and width-capped: `ios/AIWorkout/Features/Feedback/FeedbackFormView.swift`, `DeepLogAttachment.swift`, `server/src/validation.ts`. Copied to the triage sheet's Diagnostics column: `server/src/feedback-sheet-sync.ts`
- "Delete all data" does not clear either Diagnostic mode file: `ios/AIWorkout/Core/LocalDataWipe.swift` has no DeepLog call; the only clear is `DiagnosticModeView.swift`
- No log upload code exists on main; backlog #601 is status Designed: `docs/tracker-ids.json`

### Google Sheets
- Three export surfaces, one call: a blank starting template from the import screen, a program from the Plan tab, and the workout history from Settings, all going through the same `SheetExportService.export`, which differs only in the `WorkoutSheet` handed in: `ios/AIWorkout/Core/Integrations/GoogleSheets/SheetExportService.swift` (header comment), called from `ios/AIWorkout/Features/Program/SheetImportView.swift` (`exportBlankTemplate`), `ios/AIWorkout/Features/Program/ProgramView.swift`, and `ios/AIWorkout/Features/Settings/SettingsView.swift` (`exportHistoryToSheets`). A blank template and an exported program are both a `SheetKind.program`/`.template` pair read by the same importer: `ios/ProgressionEngine/Sources/ProgramBuilder/SheetProvenance.swift`
- The only scope requested is `https://www.googleapis.com/auth/drive.file`: `ios/AIWorkout/Core/Integrations/GoogleSheets/GoogleSheetsConfig.swift` (`scopes`); the `spreadsheets` constant remains only to read older grants. Narrowed 2026-09-08 (`8e9edd38`); import locked to sheets the app created and the paste box removed 2026-09-09 (`09511c90`): `SheetImportService.swift`, `ExportedSheetStore.swift`
- Its own OAuth client and its own keychain item: `GoogleSheetsConfig.swift`, `ios/AIWorkout/Core/AppConfig.swift`
- Consent is on Google's own page in an ephemeral session, as a public client with PKCE and no client secret: `GoogleSheetsOAuth.swift` (`PKCEPair`, `exchange`, `prefersEphemeralWebBrowserSession`)
- The sheet is created on the user's account with the user's token, with no folder id, no service account and no sharing call: `GoogleSheetsAPI.swift` (`create`)
- Exactly which columns leave, and the absence of body metrics, measured heart rate and free text: `ios/ProgressionEngine/Sources/ProgramBuilder/HistorySheetExport.swift` (`HistorySheet.columnHeaders`), `ProgramSheetExport.swift` (`ProgramSheet.columnHeaders`)
- Results cannot come back: `ios/AIWorkout/Core/Integrations/GoogleSheets/SheetImportService.swift` is the only import path and creates a program only; a history sheet is refused at the first cell by `ios/ProgressionEngine/Sources/ProgramBuilder/SheetProvenance.swift`
- Imported cells are sanitized and imported programs are fenced before the coach sees them: `ios/ProgressionEngine/Sources/ProgramBuilder/WorkoutSheet.swift` (`SheetText.sanitize`), `ios/AIWorkout/Core/TrustFence.swift` (`importedSheet`), `ios/AIWorkout/Core/TrainerContextBuilder.swift` (`fenceSources`); drift between the two sanitizers is pinned by `ios/AIWorkoutTests/SheetSurfacesTests.swift`
- The server has no part in it: no route or client in `server/` touches a lifter's sheet, sheet id or Google token. The developer's own triage sync is a different account and a different file: `server/src/google-clients.ts`, `server/src/feedback-sync-lambda.ts`
- Token storage, non-syncing and this-device-only, with revoke on disconnect and clearing on wipe: `GoogleSheetsTokenStore.swift` (`kSecAttrAccessibleWhenUnlockedThisDeviceOnly`), `GoogleSheetsManager.swift` (`disconnect()`), `GoogleSheetsOAuth.swift` (`revoke(token:)`), `ios/AIWorkout/Core/LocalDataWipe.swift`
- No Google identity is obtainable or stored: no `openid` or `userinfo` scope, no `id_token` handling in `GoogleSheetsOAuth.swift`, and no identity field in the stored token payload
