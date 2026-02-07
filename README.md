Logic for empty flowers / refilling
Is the flower empty or full?

- In create flowers <setup procedure>
bees are given an empty-flower-time (time in ticks that the flower must remain empty after being eaten) that is the same as flower-refilling-time (determined by slider)

- In ask <empty-red-flowers> and ask <empty-blue-flowers>
flowers have a full empty-flower-time. every tick, empty flowers are asked *do you have an empty-flower-time greater than 1? if so, reduce this by one each tick*. if empty-flower-time is 0, set breed to <red-flower> or <blue-flower> and call reset-empty-time.

- In the bottom of the code in <reset-empty-time>
  make set empty-flower-time = flower-refilling-time .

  <voilà!>
  





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
