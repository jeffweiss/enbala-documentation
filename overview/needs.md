# Needs

A Need represents a projected difference between energy generation and energy consumption that our customers want us to balance.

A need consist of only 3 things:

* A start date and time, ie 14:30:00 2018-12-22 America/Denver
* A duration, ie 2 hours
* A power value, ie 200watts or -300watts

This is the meat and potatoes of our system. Our customers schedule these needs and we control assets to meet them. When we meet our customers' needs, we say the system works and that we have balanced the grid. When we don't meet our customers needs, either they were impossible to meet or our system has not worked.

Needs get sent to our **bidding** system along with assets that are available for control \(assets that have not been filtered out because of their **constraints**\), and our bidding system generates control records which are sent back to the assets and command the assets to change their operation, ether to use more energy or use less energy.

When a need is underway, we call the need **active**. Otherwise we call the need either a future need or a past need. 

