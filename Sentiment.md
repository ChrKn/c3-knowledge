# Sentiment (Mood)

Sentiment is represented as a value between 0 (lowest) and 100 (highest)<sup>1</sup>. It is 
evaluated on a per-lodging level, as in every house has its own sentiment which is then 
aggregated for the city as a whole. It is calculated twice a month if the population has 
reached 300 people or more.

<sup>1</sup> [Julius: /src/city/sentiment.c#L239](https://github.com/bvschaik/julius/blob/016d5254c2b734dac5c56abccac05c0ba74cb934/src/city/sentiment.c#L239)     

## Starting Sentiment by Difficulty

| Difficulty | Sentiment |
|------------|-----------|
| Very Easy  | 80        |
| Easy       | 70        |
| Normal     | 60        |
| Hard       | 50        |
| Very Hard  | 40        |

[Julius: /src/game/difficulty.c#L11](https://github.com/bvschaik/julius/blob/016d5254c2b734dac5c56abccac05c0ba74cb934/src/game/difficulty.c#L11)

## Cutoffs

These values were found by extracting the translation files from the game and comparing them
with the function call that displays the actual message. To make the `.eng` files containing the 
translations human-readable, [this converter](https://github.com/bvschaik/citybuilding-tools) 
was used. The values we needed were found in `c3.eng`.

| Description                           | Value |
|---------------------------------------|-------|
| You are loathed throughout the city   | ≤ 0   |
| People are very angry with you        | ≤ 10  |
| People are angry with you             | ≤ 20  |
| People are very upset with you        | ≤ 30  |
| People are upset with you             | ≤ 40  |
| People are annoyed with you           | ≤ 50  |
| People are indifferent to you         | ≤ 60  |
| People are pleased with you           | ≤ 70  |
| People are very pleased with you      | ≤ 80  |
| People are extremely pleased with you | ≤ 90  |
| People love you                       | ≤ 99  |
| People idolize you as a god           | ≥ 100 |

[Julius: /src/window/advisor/chief.c#L203](https://github.com/bvschaik/julius/blob/016d5254c2b734dac5c56abccac05c0ba74cb934/src/window/advisor/chief.c#L203)

## Taxes

| Tax       | Sent. Change |
|-----------|--------------|
| 0%        | +3           |
| 1% - 3%   | +2           |
| 4% - 6%   | +1           |
| 7% - 8%   | ±0           |
| 9%        | -1           |
| 10% - 11% | -2           |
| 12% - 14% | -3           |
| 15% - 18% | -5           |
| 19% - 25% | -6           |

[Julius: /src/city/sentiment.c#L14](https://github.com/bvschaik/julius/blob/016d5254c2b734dac5c56abccac05c0ba74cb934/src/city/sentiment.c#L14)

## Unemployment

| Rate   | Sent. Change |
|--------|--------------|
| \> 25% | -3           |
| \> 17% | -2           |
| \> 10% | -1           |
| \> 4%  | 0            |
| ≤ 4%   | 1            |

[Julius: /src/city/sentiment.c#L150](https://github.com/bvschaik/julius/blob/016d5254c2b734dac5c56abccac05c0ba74cb934/src/city/sentiment.c#L150)

## Wages

| Difference to Rome | Sent. Change                     |
|--------------------|----------------------------------|
| \> 7 Dn            | +4                               |
| \> 4 Dn            | +3                               |
| \> 1 Dn            | +2                               |
| \> 0 Dn            | +1                               |
| = 0 Dn             | ±0                               |
| < 0 Dn             | $truncate(\frac{difference}{2})$ |

Note: The formula for a negative difference is integer-division, if the result is zero, -1 is applied. 

[Julius: /src/city/sentiment.c#L128](https://github.com/bvschaik/julius/blob/016d5254c2b734dac5c56abccac05c0ba74cb934/src/city/sentiment.c#L128)
 
## Festivals 

Festivals bring an immediate boost to your people's happiness in accordance with the following table:

| Time since last festival | ≥ 12 months  | < 12 months |
|--------------------------|--------------|-------------|
| Small Festival           | +7           | +2          |
| Large Festival           | +9           | +3          |
| Grand Festival           | +12          | +5          |

[Julius: /src/city/festival.c#L92](https://github.com/bvschaik/julius/blob/016d5254c2b734dac5c56abccac05c0ba74cb934/src/city/festival.c#L92)

## Tent Penalties

The game penalizes the player for having too many tents in their city. The penalty amount depends
on how far developed the city otherwise is. The following tables show the penalty for each case. The
first table that applies is used.

### Case 1: The city has patricians (villa or palace dwellers)

| Percentage of Tents | Sent. Penalty |
|---------------------|---------------|
| ≥ 57%               | ±0            |
| ≥ 40%               | -3            |
| ≥ 26%               | -4            |
| ≥ 10%               | -5            |
| < 10%               | -6            |

### Case 2: The city has Large Insulae or above

| Percentage of Tents | Sent. Penalty |
|---------------------|---------------|
| ≥ 57%               | ±0            |
| ≥ 40%               | -2            |
| ≥ 26%               | -3            |
| ≥ 10%               | -4            |
| < 10%               | -5            |

### Case 3: The fallback case if the first two cases don't apply

| Percentage of Tents | Sent. Penalty |
|---------------------|---------------|
| ≥ 40%               | 0             |
| ≥ 26%               | -1            |
| ≥ 10%               | -2            |
| < 10%               | -3            |

[Julius: /src/city/sentiment.c#L79](https://github.com/bvschaik/julius/blob/016d5254c2b734dac5c56abccac05c0ba74cb934/src/city/sentiment.c#L79)