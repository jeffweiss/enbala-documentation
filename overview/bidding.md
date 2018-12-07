# Bidding

The bidding process combines a few pieces of information input and generates **Control Records** for assets as output. When the bidding process can produce control records that will meet the need, we say that the need is **Solved**. If bidding cannot produce control records to mee the need, we say the need is **Unsolved.** The information the bidding system requires is:

* A Need
* The Power output of the VPP for the need
* The current energy available for every asset that can participate in solving the need.
* The power \(charge / discharge rate\) of each asset

Essentially, if the power output of the VPP is different from the power requirement of the Need at any time during the duration of the need, bidding will attempt to split the difference up between all of the available assets. This process generates **Control Records** which are sent to the assets to tell them how to change their operation. We then receive telemetry from back from the assets in a continual feedback loop of, solve the Need, tell the asset how to behave, see how the asset is behaving. This process is continual, and semi-realtime throughout the entire duration of the need. When the need is over, bidding stops.

One quirk of bidding, and a value proposition of Enbala, is that bidding doesn't know about individual asset types. Bidding treats every different type of asset as though it were a **Battery** and is ignorant to more specific asset types such as water heater. This greatly simplifies bidding but of course requires we convert all asset types into a battery which is not always straigt forward. We call this representation the **Battery Model.**

