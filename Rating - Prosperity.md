# Prosperity

## Cap

The prosperity cap is calculated from the quality of a city's [housing](/Housing.md).
Every housing type has a prosperity rating. Let's assume we have a city with 100
Small Casas and 10 Medium Palaces. Small Casas have a prosperity rating of 35, Medium
Palaces have a prosperity rating of 900. To calculate our prosperity cap, we multiply
the number of buildings of any given building type with its prosperity rating and 
add them together. Then we divide the result by the overall number of houses.

In our example:

$$
\frac{35 \times 100 + 900 \times 10}{100 + 10} = 113.\overline{63}
$$

This will then be rounded down to 100, the maximum possible prosperity value.

[Source: Julius /src/city/ratings.c#L449](https://github.com/bvschaik/julius/blob/016d5254c2b734dac5c56abccac05c0ba74cb934/src/city/ratings.c#L449)

## Gain Rate

Prosperity is calculated once a year in January.<sup>1</sup> A maximum number of 10 prosperity 
points can be gained per year. To calculate the points, the following table can be 
used. The values are added up and represent the number of prosperity points awarded for 
the past year.

### Determinants

| Determinants                                   | Value |
|------------------------------------------------|-------|
| ≤ 4% unemployment                              | +1    |
| ≥ 15% unemployment                             | -1    |
| City made a profit                             | +5    |
| City made a loss                               | -1    |
| At least 2 food types eaten                    | +1    |
| Wages ≥ 2 Dn higher than Rome's **on average** | +1    |
| Wages lower than Rome's **on average**         | -1    |
| \> 10% of population are patricians            | +1    |
| \> 30% of population lives in shacks or lower  | -1    |
| Failure to pay tribute                         | -1    |
| Active Hippodrome                              | +1    |

[Source: Julius /src/city/ratings.c#L398](https://github.com/bvschaik/julius/blob/016d5254c2b734dac5c56abccac05c0ba74cb934/src/city/ratings.c#L398)

<sup>1</sup> There is an additional "used bailout" modifier of -3 that is applied immediately
when the bailout money from Caesar is used. This is not included in the table above, since it is
not used for the prosperity calculation at the end of the year.   
[Source: Julius /src/city/ratings.c#L58](https://github.com/bvschaik/julius/blob/016d5254c2b734dac5c56abccac05c0ba74cb934/src/city/ratings.c#L58)