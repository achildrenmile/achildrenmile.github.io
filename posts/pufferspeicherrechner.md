## DIY Solar Buffer Tank Heating - Pufferspeicher Heizstab Rechner
2026-03-31 [#Blog](/index) | [#Solar](/posts/pufferspeicherrechner) | [#DIY](/posts/pufferspeicherrechner)

We had 4 older LiFePO4 batteries, a second-hand inverter, 8 solar panels and some used MPPT trackers lying around. So the idea was born: build a DIY solar system to heat up our buffer tank (Pufferspeicher), reduce pellet consumption and have some fun along the way.

### The setup

The system uses a heating rod (Heizstab) — originally a 3-phase unit, now wired to run on a single phase at around 1.3 kW — to heat an 800L hygiene buffer tank. The solar panels feed through the MPPT trackers and the LiFePO4 batteries provide storage for heating after sunset. It's a DIY playground, all built from parts we already had.

In summer this produces enough hot water for 4 persons and the pellet boiler stays off from spring to autumn.

### The calculator

To plan the energy flow, I built a small calculator tool: the [Pufferspeicher Heizstab Rechner](https://achildrenmile.github.io/pufferspeicher-rechner/). It has three tabs:

* **Aufladung** — How much energy goes into the buffer tank per day
* **Entladung Sommer** — Summer discharge and hot water usage
* **Übergangszeit** — Transition season calculations

Single HTML file, no dependencies, vanilla JS. MIT licensed.

[Live Tool](https://achildrenmile.github.io/pufferspeicher-rechner/) | [GitHub Repo](https://github.com/achildrenmile/pufferspeicher-rechner)

### Test phase

<iframe width="560" height="315" src="https://www.youtube.com/embed/nxTsm-T0kuU" frameborder="0" allowfullscreen></iframe>


