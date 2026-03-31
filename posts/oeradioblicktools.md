## Building Ham Radio Tools With AI Assistance — The -Blick Toolbox
2025-02-20 [#Blog](/index) | [#HamRadio](/posts/oeradioblicktools) | [#AI](/posts/oeradioblicktools) | [#Tools](/posts/oeradioblicktools)

After [BandBlick](https://bandblick.oeradio.at) kicked things off, the tool ecosystem on [oeradio.at](https://oeradio.at) grew. The naming convention "-Blick" (German for "view/glance") started with BandBlick and then became a brand by accident. By the fifth tool I was committed.

### The -Blick family

* **[BandBlick](https://bandblick.oeradio.at)** — IARU Region 1 band plan viewer. The one that started it all.
* **[StrahlBlick](https://strahlblick.oeradio.at)** — RF safety distance calculator per ICNIRP limits. Useful before you transmit with high power and want to know if your neighbours should be worried.
* **[AkkuBlick](https://akkublick.oeradio.at)** — Battery capacity planner for portable/SOTA operation. Calculates how long your battery lasts given your rig's TX/RX duty cycle.
* **[KabelBlick](https://kabelblick.oeradio.at)** — Coax cable loss calculator. Because every dB counts, especially the ones you lose before the signal reaches the antenna.
* **[RelaisBlick](https://relaisblick.oeradio.at)** — Interactive map of all Austrian amateur radio repeaters. Data courtesy of ÖVSV UKW Referat and OE8VIK Michi.
* **[AntennenBlick](https://antennenblick.oeradio.at)** — Antenna calculator for dipole, ground plane and more.

### How they were built

All of these were built AI-assisted, primarily with Claude. I'm a .NET/enterprise architect by trade. Writing vanilla JS UIs is not my natural habitat. AI assistance made it possible to ship these fast without fighting CSS for 3 days.

### Beyond the -Blick tools

The platform also runs [OpenWebRX](https://openwebrx.oeradio.at) (SDR receiver), OpenHamClock, [Wavelog](https://wavelog.oeradio.at) (logbook), and a propagation/DX dashboard. It's growing into a full ham radio workbench — mostly because every time I think "wouldn't it be nice if..." I end up building it instead of going on the air.


