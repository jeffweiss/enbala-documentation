# The Battery Model

Bidding is a fairly complicated process that needs to run fast. In order to simplify and speed up bidding, enbala represents all of the various asset types \(water heater, EV chargers, etc.\) as batteries. A battery is a very simple device and is a perfect device for solving needs.

A battery has only 3 properties

* The maximum amount of energy it can store \(minimum is always zero\)
* The amount of energy it is storing right now
* The rate at which it can charge or discharge energy

All other asset types have very different real world parameters. For example a water heater has:

* The total volume of its tank
* The amount of water currently in the tank
* The temperature of the water currently in the tank
* The maximum temperature that the water in the tank could be
* The minimum water the tank is allowed to have
* The minimum temperature of the water in the tank

In order to support our bidding process we must convert these values into the battery model. Conversely, when bidding produces a control record, the control record will be for a battery and we must convert this control record to work for a water heater.

This 3 step system:

* Convert asset to battery
* Use battery in bidding
* Convert control record for battery into control record for asset

Is a crucial time saving simplification that enbala employs to solve needs and is the heart of our value proposition to customers.

