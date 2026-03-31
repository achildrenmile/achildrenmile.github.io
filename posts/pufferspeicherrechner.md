## Pufferspeicher Heizstab Rechner - PV Buffer Tank Heating Calculator
2026-03-31 [#Blog](/index) | [#Solar](/posts/pufferspeicherrechner) | [#Tools](/posts/pufferspeicherrechner)

Most online calculators for PV-powered buffer tank heating get the energy flow wrong. They assume sequential operation: first charge the battery, then heat the water. In reality, a PV system works in parallel — the inverter splits power between the heating rod and battery charging simultaneously during sun hours.

### The correct parallel model

The calculator uses a two-phase model:

**Phase 1 (sun hours):** PV output is split between the heating rod and battery charging at the same time. The heater runs at its rated power while excess solar energy flows into the battery.

**Phase 2 (after sunset):** The battery powers the heating rod until it reaches the configured minimum SOC. No sun, no split — just battery to heater until the limit is hit.

### What does the tool do?

The [Pufferspeicher Heizstab Rechner](https://achildrenmile.github.io/pufferspeicher-rechner/) has three tabs:

* **Aufladung** — How much energy goes into the buffer tank per day
* **Entladung Sommer** — Summer discharge and hot water usage
* **Übergangszeit** — Transition season calculations

### Example with real numbers

Setup: ~3 kWp PV, ~8 kWh LiFePO4 battery, 1.3 kW heating rod, 800L hygiene buffer tank. Result: ~16 kWh/day heat output in summer — enough hot water for 4 persons. The pellet boiler stays off from spring to autumn.

### Tech

Single HTML file, no dependencies, vanilla JS. MIT licensed.

[Live Tool](https://achildrenmile.github.io/pufferspeicher-rechner/) | [GitHub Repo](https://github.com/achildrenmile/pufferspeicher-rechner)


