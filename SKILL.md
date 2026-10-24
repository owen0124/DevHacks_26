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

1. Where they usually leave from (for example their dorm or apartment). Default: ask each time. Look up its street
   address, confirm it in one line ("Tempe Transportation Center, 200 E 5th St, Tempe, AZ?") and remember the address.
2. How they get around: walking, bike, bus or car. Default: walking.
3. How much extra buffer they want before the event. Default: 5 minutes.
4. Their preferred map app: Apple Maps or Google Maps. Default: Apple Maps.

## Steps

1. Find the event. Read the student's class schedule from **Canvas** or their **Google Calendar**, or use the
   time and place they texted. Get the name, start time, building or room, and whether it is in person or on
   Zoom (look for a Zoom link in the calendar event, Canvas course page or announcement).
   If neither account is connected and the student gave no time, ask for the event name, day, time and location.
   Never guess a time or building.
   Look up the building's street address on the **web**. If it cannot be found, ask the student for it.
   If the event is at the student's starting point, say no trip is needed and do not set a leave reminder.
2. Work out the travel time from the starting address to the building's address. Use the **web** to find the
   distance, then estimate: walking about 12 min per km (20 min per mile), bike about 4 min per km, bus or car:
   the typical trip time plus 5 minutes. Round up to the next 5 minutes and say "about".
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
   - put on its own line the directions link from "Building the map link" below, or the Zoom link for a Zoom event.

## Building the map link

Build the link yourself from the template for the student's map app. Do not search the web for a link and do not
try to verify it: these URLs work for any address. Never send another kind of link instead (a building's web page,
Street View, a search results page) and never add a note about the link.

- Google Maps:
  `https://www.google.com/maps/dir/?api=1&origin=<start>&destination=<place>&travelmode=<mode>`
  with mode `walking`, `bicycling`, `transit` or `driving`.
- Apple Maps: `https://maps.apple.com/?saddr=<start>&daddr=<place>&dirflg=<flag>`
  with flag `w` for walking, `r` for bus, `d` for car (use `w` for bike).

Fill in the full street addresses, URL-encoded: spaces as `+`, commas as `%2C`. Example, walking from Tempe
Transportation Center to ASU's Memorial Union in Google Maps:

```text
https://www.google.com/maps/dir/?api=1&origin=200+E+5th+St%2C+Tempe%2C+AZ&destination=301+E+Orange+St%2C+Tempe%2C+AZ&travelmode=walking
```

## Test runs

If the student asks for a test or a fake class, use a real building near their starting point that is a different
place and at least a 5-minute trip away. Set the start time so the reminder fires in about 3 minutes. Say "test" in
the reminder text and do not add the event to their calendar.

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
class-to-map: time to head to CHEM 101 (10:00 am, Memorial Union). About 15 min walk.
Go now? Reply go, snooze 5, snooze 15, snooze 30, or skip
https://www.google.com/maps/dir/?api=1&origin=200+E+5th+St%2C+Tempe%2C+AZ&destination=301+E+Orange+St%2C+Tempe%2C+AZ&travelmode=walking
```

## What this Skill cannot do

Cubbie talks over iMessage, so it cannot show buttons, open apps or sign in to Zoom on the phone, and it does not
know the student's live location. It sends tappable links and uses the starting point the student gave. Say so
plainly if the student asks for any of these.

## When something fails

- Canvas or Google not connected and no time given: ask for the event details, or offer to connect the account.
- Building not found: ask for the address or a nearby landmark.
- A reminder could not be created: say which one and offer to retry once. Do not retry silently.
