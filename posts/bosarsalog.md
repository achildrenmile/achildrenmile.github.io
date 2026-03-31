## BOS-ARSA Log — Building an Emergency Communications Exercise Tool
2025-09-22 [#Blog](/index) | [#HamRadio](/posts/bosarsalog) | [#EmergencyComms](/posts/bosarsalog) | [#Tools](/posts/bosarsalog)

[BOS-ARSA](https://bos-arsa.at) is an Austrian organization running weekly emergency communications exercises via amateur radio. Operators across multiple districts check in via different repeaters, and someone has to log all of it. Previously that someone used Excel spreadsheets. Which works until it doesn't — multiple operators logging at the same time, real-time updates needed, merging files after the exercise. We've all been there.

### What BOS-ARSA Log does

A web-based QSO logging tool optimized for the exercise workflow:

* **Keyboard-only entry** — no mouse needed during the exercise. Enter a callsign, hit Enter, it auto-populates name, QTH and district from the pre-loaded operator database. Enter the report (59, 5930, etc.), save. The whole flow is a few keypresses.
* **Multi-user real-time support** via Socket.IO — multiple logging stations see updates live. No more merging spreadsheets afterwards.
* **Statistics view** — operators by Bundesland, Bezirk heatmap, participation rates. The kind of overview that used to require an afternoon of pivot tables.
* **Callsign database** — data sourced from the BOS-ARSA callsign list, so lookups are fast and accurate.

### Why build this

Honestly? The Excel situation was just that bad. Building a multi-user real-time web app is maybe overkill for a volunteer emergency radio exercise. But once you've watched someone try to merge three Excel files with conflicting timestamps while 20 operators are still checking in, the engineering effort starts to look reasonable.

The tool is in active use for the weekly BOS-ARSA exercises and has made the logging process significantly less painful for everyone involved.

[GitHub](https://github.com/achildrenmile/bosarsalog)


