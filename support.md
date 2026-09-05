# WorkoutSmith — Support

**Last updated:** 2026-09-05

WorkoutSmith is built and supported by one person. If something is broken, or if
you cannot work out how something is meant to work, the routes below reach him
directly.

---

## How to get help

**If you have the app installed, the fastest route is the in-app feedback form:
Settings → Send feedback.** There is also a speech-bubble button in the
navigation bar on the main tabs that opens the same form. It is better than
email for a bug report, because it carries the context a fix needs and an email
cannot: your app version and build, your device model, your iOS version, the
screen you were on and the last few screens you visited, your language, time
zone, free storage, and how long since the phone was restarted. The form shows
you that list before you send it. You can attach a screenshot, and you can
attach the app's diagnostic log, which is the last 24 hours of what the app and
your watch were doing and which stays on your device unless you choose to send
it. No workouts, lifts, or health data are ever attached.

No account is needed to send feedback, and you can send it without your name.

Feedback is copied once a day into a private spreadsheet that only the developer
reads. **What it does not have is a reply channel** — the form sends one way, so
if you need an answer, use email.

**By email: mignet1278@gmail.com.** It is read by the developer personally. Use
it if you do not have the app installed, if you cannot get into it, or if you
want a reply.

If you are writing about a bug, the two things that make it fixable are what you
expected to happen and what happened instead. A screenshot is worth more than a
description of a screen.

---

## Google Sheets: what the app can reach in your Drive

**WorkoutSmith asks Google for two permissions when you connect Sheets, and they
are not equally narrow.** Google's consent screen shows you both, so it is worth
knowing which is which.

`drive.file` is the narrow one. Google describes it as "only the specific Google
Drive files you use with this app", and that is exactly what it does. It is what
lets the app put a new spreadsheet into your Drive, and it gives no view of
anything else in there.

`spreadsheets` is the wider one, and Google classes it as sensitive. It covers
seeing, editing, creating and deleting your Google Sheets spreadsheets, and it
is **not** limited to the files the app made. It is asked for because there is
no narrower permission that can read and write cell values, and reading and
writing cell values is the whole feature: without it there is no export to edit
and no import to bring back.

What the app does with it is a good deal narrower than what it is allowed to do.
**It never lists, searches, or browses your Drive, and there is no file picker in
it.** It touches the spreadsheets it creates for you and the ones whose links you
paste in yourself, and nothing else. It has no way to find a sheet you have not
handed it, and it never asks Google for one.

If that is more than you want to give, do not connect Google Sheets. Nothing
else in the app depends on it, and **Settings → App integrations → Google
Sheets** disconnects it later and tells Google to revoke the grant.

**What the importer cares about is the layout, not which file it is.** It reads
the sheet your link points to and checks that the columns and rows are the ones
the export laid down, so keep that shape intact when you edit. If you made a
copy of the exported sheet and edited the copy, import the copy's link rather
than the original's. If the app says it could not find that spreadsheet, the
link is wrong, or you are connected with a different Google account from the one
that owns the sheet.

**How the round trip works.** From the Plan tab you can **Export this program to
Google Sheets**, edit it in Google Sheets, and then **Import a program from
Google Sheets** to bring your changes back. The sheet has to be one the app made
for you: either an export of a program, or the starting sheet the import screen
can create for you. **A blank spreadsheet you built yourself cannot be
imported**, because the exported sheet is what establishes the format.

**Workout history goes out and does not come back.** In Settings, **Export
workout history to Google Sheets** makes a spreadsheet of every set you have
logged, in your own Drive, to keep, chart, or send to somebody. There is no
import for it, and that is deliberate rather than missing: your logged history
is the record of what you actually did, and a path that let it be overwritten
from a spreadsheet would make every number in the app worth less.

If the Sheets rows say Google Sheets is not set up, or Google refuses a
permission, disconnect and reconnect under **Settings → App integrations →
Google Sheets**, and allow both boxes on Google's screen.

---

## The AI coach is optional, and it runs on your own key

WorkoutSmith does not sell, host, or provide AI. Everything else in the app
works with no AI configured at all: logging, progression, the program builder,
walking and running, Adventure, and Compete.

The optional coaching conversation runs on **an API key you fetch yourself and
paste into Settings → AI coach**, either a Google Gemini key from Google AI
Studio or an Anthropic Claude key from the Anthropic Console. The app walks you
through getting one. Requests are billed to your own account with that company,
not to WorkoutSmith. Your key is stored only on your device, in the Keychain,
and is never stored on the server or written to logs.

So if the coach is asking you for a key, nothing has gone wrong. That is the
design. You can also choose **No AI coach** and keep everything else.

The AI is not what a WorkoutSmith subscription buys. It is your own purchase
from Google or Anthropic, and it works the same whether you subscribe or not.

---

## Subscriptions, cancelling, and refunds

There are two monthly subscriptions, in one subscription group, so you can move
between them:

| | |
|---|---|
| **WorkoutSmith Premium** | $4.99 per month |
| **WorkoutSmith Coach** | $24.99 per month |

**Which one you want.** Premium is for your own training, and it lets you coach
**up to 2 people at a time**. That is a concurrent limit, not a lifetime one: if
you take back a program you shared with somebody, the place is free again.
WorkoutSmith Coach is for people who coach others and need more than two, and it
includes everything in Premium. If you do not coach anybody, Premium is the one.

**There is a free introductory period**, and its length is shown to you on the
purchase screen before you pay. It is available **once per Apple ID across both
tiers**, so moving between Premium and Coach does not start a second one.

The prices above are in US dollars. The App Store shows the price in your own
currency, including any tax, before you confirm.

**Apple handles the billing, not us.** Every subscription is bought through your
Apple ID, so cancellations and refunds go through Apple and cannot be done from
inside the app or by emailing the developer.

- **To cancel, or to switch tiers:** on your iPhone, open **Settings → [your
  name] → Subscriptions**, choose WorkoutSmith, and cancel or change your plan
  there. Cancelling stops the next renewal; you keep what you paid for until the
  end of the current period.
- **To ask for a refund:** go to
  [reportaproblem.apple.com](https://reportaproblem.apple.com), sign in with the
  same Apple ID, and choose the purchase. Apple decides refunds, not us.
- **If a purchase did not unlock:** open the subscription screen in the app and
  use **Restore purchases**, which asks the App Store what your Apple ID owns.
  If that does not fix it, email the address above.

You can see where you stand at any time under **Settings → Subscription**.

---

## Privacy and your data

The full policy is here: **[Privacy Policy](privacy)**.

The short version, for a support question: your workouts, your health data, and
your entire training history **live on your iPhone**, not on a server. There is
one server and it exists only for the social features. There are no ads, no
analytics SDKs, and no tracking.

**You can delete everything yourself, from inside the app, without emailing
anybody.** There are two separate controls in Settings, because they do
different things:

- **Delete all data** returns the phone to the state a fresh install starts in:
  your profile, programs, workout history, chat with the coach, XP and
  achievements, your saved home, your settings, and your saved keys. It signs
  you out of your competition account without deleting it.
- **Delete account** deletes your account on the server, with your friends and
  challenges. Your workouts on the phone survive it.

Both ask twice, and neither can be undone. What survives each one, and the one
narrow exception to deletion, is set out in full in the privacy policy. You can
export your data before you delete anything.

---

## Reporting somebody, or something they wrote

WorkoutSmith carries things other people write, such as handles, display names,
challenge and group names, and the labels and notes on a race course. If you see
something that does not belong in the app, or somebody behaving badly, report
it.

**How to report:** use **Settings → Send feedback**, or email
**mignet1278@gmail.com**. Both go straight to the developer, who reads every
one. Say what you saw, where you saw it, and the handle or name involved. A
screenshot helps more than anything else. Content that breaks the rules is
removed, and an account can be removed from a race or from the service.

**The person you report is never shown who reported them.** A report is not
visible to the person it is about.

**Blocks** are listed under **Settings → Blocked people**, where you can also
lift one. A block is enforced on the server rather than merely hidden on your
phone: neither of you sees the other anywhere in the app, cheers stop in both
directions, and on race boards and standings a blocked person appears to you as
a hidden participant. If you were friends, that ends. The person you block is
not told.

If you need somebody blocked and cannot do it yourself, email the address above
and say who.

---

## A few other things people ask

**Do I need an account?** Not to train. Logging, programs, progression, Apple
Health, Adventure, and the walking and running tab all work signed out. Signing
in is only for the social features: friends, challenges, leagues, and races.

**Where did my session go?** It did not go anywhere. If you close the app
mid-set, or the battery dies, the session is waiting where you left it when you
reopen the app.

**Apple Health is not showing my workouts.** Health access is granted per
category, and iOS remembers a refusal. Check **iOS Settings → Health → Data
Access & Devices → WorkoutSmith** and confirm the categories are switched on.

**Can I use kilograms?** Not yet.

---

## Contact

**mignet1278@gmail.com**, or **Settings → Send feedback** inside the app.

WorkoutSmith is published by Michael Lee, an individual developer based in
Massachusetts, USA.
