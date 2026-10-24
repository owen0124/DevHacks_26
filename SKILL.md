---
name: class-to-map
description: Texts the student a "Go now?" reminder before a class or office hours, with how long the trip takes and a one-tap map or Zoom link. Use when the student says they lose track of time, keeps showing up late, or asks to be reminded to leave for a class, lecture, lab or office hours.
---

# Class to Map

This Skill uses only Cubbie's built-in abilities. It has no scripts.

## When to use

- "I always lose track of time, remind me when to leave for CHEM 101."
- "Text me before office hours Thursday at 3 so I'm not late."
- "Can you tell me when I need to head to my lab?"
- "Remind me before my Zoom office hours."

Do not use it for assignment due dates, study plans or emailing a professor.

## Setup (first time only)

Ask one question at a time, offer a default the student can accept with "yes", and remember each answer with
Cubbie's **memory** so it is never asked twice:

1. Where they usually leave from (for example their dorm or apartment). Default: ask each time.
2. How they get around: walking, bike, bus or car. Default: walking.
3. How much extra buffer they want before the event. Default: 5 minutes.
4. Their preferred map app: Apple Maps or Google Maps. Default: Apple Maps.

## Steps

1. Find the event. Read the student's class schedule from **Canvas** or their **Google Calendar**, or use the
   time and place they texted. Get the name, start time, building or room, and whether it is in person or on
   Zoom (look for a Zoom link in the calendar event, Canvas course page or announcement).
   If neither account is connected and the student gave no time, ask for the event name, day, time and location.
   Never guess a time or building.
2. Work out the travel time. Use the **web** to estimate the trip from the student's usual starting point to the
   building by their way of getting around. If the building cannot be found, ask the student for the address.
   For a Zoom event, travel time is zero; plan the reminder 5 minutes before the start instead.
3. Pick the reminder time: start time minus travel time minus buffer. If that time has already passed, tell the
   student right away to leave now and include the link from step 5.
4. Show the plan in one or two lines and ask before creating anything, for example:
   "CHEM 101 in Hall 204 at 10 am, about 12 min walk. I'll text you at 9:43 to go. OK?"
   Offer to repeat it for every meeting of that class. Create nothing until the student says yes.
5. After the yes, create the reminder with Cubbie's **reminders** ability. Word it so it makes sense on its own
   later. The reminder text must:
   - name the Skill (class-to-map), the event, its start time and the place;
   - say about how long the trip takes;
   - end with "Go now? Reply go, snooze 5, snooze 15, snooze 30, or skip";
   - put on its own line a directions link to the building in the student's map app
     (Apple Maps: `https://maps.apple.com/?daddr=<address>`, Google Maps:
     `https://www.google.com/maps/dir/?api=1&destination=<address>`), or the Zoom link for a Zoom event.

## When the reminder fires and the student replies

- "go" (or "yes", "confirm", "leaving"): reply with the directions link on its own line and one encouraging line.
  For Zoom, send the Zoom link on its own line and say tapping it opens Zoom and puts them in the waiting room.
- "no" or "deny" without a time: ask "Remind you again in 5, 15 or 30 min, or skip today?"
- "snooze 5", "snooze 15", "snooze 30" (or just "15"): create a one-time reminder that many minutes from now with
  the same text and link, and confirm in one line. If the new time is after the event starts, say they would be
  late and ask if they still want it.
- "skip" or "decline": confirm that today's reminder is skipped and that any repeating reminder still runs next time.

## Replies

Plain text, no Markdown. Keep each reply to two or three short lines. Lead with the time to leave. Put every map or
Zoom link on its own line so it becomes a tappable preview.

Example reminder:

```text
Time to head to CHEM 101 (10:00 am, Hall 204). About 12 min walk.
Go now? Reply go, snooze 5, snooze 15, snooze 30, or skip
https://maps.apple.com/?daddr=Hall+204
```

## What this Skill cannot do

Cubbie talks over iMessage, so it cannot show buttons, open apps or sign in to Zoom on the phone, and it does not
know the student's live location. It sends tappable links and uses the starting point the student gave. Say so
plainly if the student asks for any of these.

## When something fails

- Canvas or Google not connected and no time given: ask for the event details, or offer to connect the account.
- Building not found: ask for the address or a nearby landmark.
- A reminder could not be created: say which one and offer to retry once. Do not retry silently.
