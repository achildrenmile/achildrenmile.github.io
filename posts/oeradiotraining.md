## QBlitz, MorseFleet and FunkPilot — When AI Meets Ham Radio Training
2025-06-10 [#Blog](/index) | [#HamRadio](/posts/oeradiotraining) | [#AI](/posts/oeradiotraining) | [#Learning](/posts/oeradiotraining)

The [oeradio.at](https://oeradio.at) toolbox keeps growing. This time it's the learning and training tier — tools to help you get better at the hobby, or at least less embarrassed during a QSO.

### The training tools

* **[QBlitz](https://qblitz.oeradio.at)** — Q-code rapid trainer with spaced repetition. Q-codes are the one thing every ham needs to know and nobody enjoys memorizing. QBlitz makes the pain slightly more structured.
* **MorseFleet** — Morse code trainer. Yes, CW is no longer required for licensing in most countries. No, that doesn't stop certain OMs from judging you for not knowing it.
* **PrefixPlay** — Country prefix quiz. For those moments when you hear a callsign and want to know where it's from without reaching for the prefix list.
* **FirstContact** — A lighter quiz/game format for getting started with ham radio basics.

### FunkPilot — the big one

**[FunkPilot](https://funkpilot.oeradio.at)** is an AI-powered assistant for amateur radio operators. It can answer questions about band conditions, help with CQ phrasing, explain regulations, assist with SOTA/POTA planning, and more. Built on top of Claude via API, with the oeradio MCP server providing live ham radio data as context — band plans, repeater data, ICNIRP limits, you name it.

It's essentially "what if you could ask an Elmer who never gets tired of questions and doesn't give you a lecture about how QRP was better in 1987."

### The MCP Server

The **[OERadio MCP Server](https://oeradio-mcp.oeradio.at)** powers FunkPilot and can be used by other AI assistants. It makes all the ham radio calculators and data queryable by LLMs. If you want your own AI setup to know about Austrian repeaters or ICNIRP safety distances, this is how.

There's a certain irony in using AI to help with a hobby that has plenty of established culture around self-sufficiency and figuring things out yourself. But if the alternative is spending 20 minutes searching through PDFs for a band plan detail, I'll take the AI.

### GitHub repos

[QBlitz](https://github.com/achildrenmile/qblitz) | [MorseFleet](https://github.com/achildrenmile/morsefleet) | [FunkPilot](https://github.com/achildrenmile/funkpilot) | [OERadio MCP Server](https://github.com/achildrenmile/oeradio-mcp) | [PrefixPlay](https://github.com/achildrenmile/prefixplay) | [FirstContact](https://github.com/achildrenmile/firstcontact)


