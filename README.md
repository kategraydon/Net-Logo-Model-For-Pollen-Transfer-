Logic for drinking and returning.

There are four main breeds that the foragers can be:

[foraging bee]
contains all the logic for moving and searching for food.

if lands on flower, likelihood it will stop.

has timer for patience.

[drinking bee]
contains eating logic:

transfer of nectar

transfer of pollen

contains all the logic to say how long it will stay [drinking time]

  Is the bee's crop (stomach) full yet?

[called at the end of a visit/ at the beginning of being a drinking bee]
if *energy the bee currently holds* is smaller than *energy the bee could hold* then the bee must drink.
  <if forager-energy > crop-capacity * 5.814
[set breed drinking-bee]]>

if *energy the bee currently holds* is larger or equal to *energy the bee could hold* then the bee must 
become [return forager]

Code:
  <if forager-energy > crop-capacity * 5.814
[set breed return-forager]>

[return forager]
unloads pollen and nectar


There are two breeds that the flowers can be:
[flower]

[empty flower]
have just been visited

contains logic for refilling *flower-refilling-time* which goes down by one every tick
