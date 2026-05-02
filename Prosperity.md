# Prosperity

## Cap

The prosperity cap is calculated from the quality of a city's [housing](/Housing.md).
Every type of housing has a prosperity rating. Let's assume we have a city with 100
Small Casas and 10 Medium Palaces. Small Casas have a prosperity rating of 35, Medium
Palaces have a prosperity rating of 900. To calculate our prosperity cap, we multiply
the number of buildings of any given building type with its prosperity rating and 
add them together. Then we divide the result by the overall number of houses.

In our example:

$$
\frac{35 \times 100 + 900 \times 10}{100 + 10} = 113.\overline{63}
$$

This will then be rounded down to 100, the maximum possible prosperity value.

## Gain Rate

Prosperity is calculated once a year in January. A maximum number of 10 prosperity 
points can be gained per year. To calculate the points gained, the following table can 
be used. The values are added together and represent the number of prosperity points
for the year.

### Determinants

| Determinants                                 | Value |
|----------------------------------------------|-------|
| Base gain rate                               | 2     |
| City made a profit                           | 2     |
| ≥ 10% of population are patricians           | 1     |
| < 30% of population lives in shacks or lower | 1     |
| < 5% unemployment                            | 1     |
| ≥ 2 Dn more than Rome's wage                 | 1     |
| 2 food types for citizens < Grand Insula     | 1     |
| Active Hippodrome                            | 1     |
| City made a loss                             | -1    |
| \> 15% unemployment                          | -1    |
| Wages are below Rome's                       | -1    |
| Failure to pay tribute                       | -3    |
| Receive Bailout from Caesar                  | -3    |
