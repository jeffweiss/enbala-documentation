# Topology

## Assets

Also called either **Devices** or by their device name, such as Water Heater or EV Charger, these are the physical devices that we **receive telemetry** from and **send control records** to in order to run a Demand Response program.

## Sites

Sites exist to group assets together for **Payout** purposes. Our customers run a **Demand Response Program** that their customers participate in. When any of their customers' assets gets used in a Demand Response Event, the asset owner must get paid out according to their **Program Contract.** Sites _typically_ are representitive of a physical location, typically consisit of assets owned by one company, and are always associated with a payout structure called a **Customer Baseline**. More on customer baselines later.

## Virtual Power Plants

The Virtual Power Plant is a grouping of assets to be used to respond to **Grid Needs** also called simply **Needs**. In our system a customer may have _many_ virtual power plants and each of them can have many needs scheduled. It is at the Virtual Power Plant level that actual control of assets is scheduled and it is the _only_ place that control of assets can be scheduled. The sum of the energy usage of all the assets _in_ a VPP is considered the energy usage _of_ the VPP and needs are scheduled against a VPPs energy usage. This is another reason why this is considered a "Power Plant" as we can abstract away the assets entirely and think of them as 1 energy "source" that we can "curtail" in order to effectively "generate" electricity.

