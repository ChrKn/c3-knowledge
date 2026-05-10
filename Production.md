# Production

All production rates assume perfect transportation. That means the cart pusher is back
at the production building the moment the next load is ready. 

## Cartloads vs. Units

$1\ cartload = 100\ units$. Units are being used by markets and houses, while cartloads
are being used by production buildings / warehouses. 

## Food

Be aware that food is being eaten in order: `Wheat > Vegetables > Fruit > Meat`.
Meaning if a house that requires only one type of food has wheat and meat, 
the inhabitants will only eat wheat until it is used up, then eat the meat. 
The same goes for markets. They will always try to get the highest food type on 
the list with priority.

### Wheat Farms

Food for about `320 people (or 19.2 cartloads)` on dessert and mediterran 
maps and `160 (9.6 cartloads)` on northern.

### Fruit, Meat, Vegetables

Food for about `160 people (or 9.6 cartloads)` regardless of map climate.

### Fishing

Short: It's complicated and involves counting of tiles and estimations. You can
[read up on it here](https://caesar3.heavengames.com/cgi-bin/caeforumscgi/display.cgi?action=st&fn=2&tn=3266).  

The following formulas apply. First, we calculate the time in in-game ticks per 
cartload ($T_{cl}$) using the distance in tiles ($D_t$) from the wharf to the fishing 
point.  
This value is then used to calculate the fish production in cartloads per year 
($F_{cl/y}$) with the second formula.  
And since cartloads are quite hard to grasp, 
we also calculate the people fed per year ($P_{f/y}$) based on the assumption 
that every person eats six units of food per year.

$$
\begin{flalign}
& T_{cl} = 50 \times \left\lceil \frac{30 \times D_t + 211}{50} \right\rceil &
\end{flalign}
$$

$$
\begin{flalign}
& F_{cl/y} = \frac{800}{T_{cl}} \times 12 & 
\end{flalign}
$$

$$
\begin{flalign}
& P_{f/y} = \left\lfloor \frac{F_{cl/y} \times 100}{6} \right\rfloor &
\end{flalign}
$$

This gives us the following results:

| $D_t$ | $F_{cl/y}$ | $P_{f/y}$ |
|-------|------------|-----------|
| 0     | 38.400     | 640       |
| 1     | 38.400     | 640       |
| 2     | 32.000     | 533       |
| 3     | 27.428     | 457       |
| 4     | 27.428     | 457       |
| 5     | 24.000     | 400       |
| 6     | 24.000     | 400       |
| 7     | 21.333     | 355       |
| 8     | 19.200     | 320       |
| 9     | 19.200     | 320       |
| 10    | 17.454     | 290       |
| 11    | 17.454     | 290       |
| 12    | 16.000     | 266       |
| 13    | 14.769     | 246       |
| 14    | 14.769     | 246       |
| 15    | 13.714     | 228       |
| 16    | 13.714     | 228       |

## Resources and Goods

### Olives, Vines, Iron, Timber, Clay

`9.6 cartloads` per year.

### Oil, Wine, Weapons, Furniture, Pottery, Marble

`4.8 cartloads` per year.

## Military

One barracks produces $21.\overline{3}$ Soldiers per year given perfect weapon availability.

[Source: Heaven Games (Brugle)](https://caesar3.heavengames.com/cgi-bin/caeforumscgi/display.cgi?action=st&fn=2&tn=7508)