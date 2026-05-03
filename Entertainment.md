# Entertainment

| Coverage Index | Advisor reports |
|----------------|-----------------|
| 100%           | Perfect         |
| ≥ 90%          | Excellent       |
| ≥ 80%          | Very Good       |
| ≥ 70%          | Good            |
| ≥ 60%          | Above Average   |
| ≥ 40%          | Average         |
| ≥ 30%          | Below Average   |
| ≥ 20%          | Poor            |
| ≥ 10%          | Very Poor       |
| ≥ 0%           | None            |

[Source: Heaven Games](https://caesar3.heavengames.com/cgi-bin/caeforumscgi/display.cgi?action=st&fn=2&tn=2859)

## Points Provided by Walkers

These are applied to a house when a walker passes by.

| Venue        | No. of Shows | Points   | 
|--------------|--------------|----------|
| Theatre      | 0-1          | 10       |
| Amphitheatre | 0-1<br>2     | 10<br>15 |
| Colosseum    | 0-1<br>2     | 15<br>25 |
| Hippodrome   | n/a          | 30       |

## Base Entertainment Coverage

Additionally, each type of venue can generate a bonus of up to 5 points scaling 
to coverage. These work globally.

To calculate the overall base entertainment value, you can use the following 
formula where `HC` equals the hippodrome coverage, `CC` the colosseum coverage, 
and so forth.  
Note: Hippodrome coverage is always perfect.

$$
\begin{aligned}
& \frac{TC + AC + CC + HC}{20} &
\end{aligned}
$$

[Source: Julius /src/building/house_service.c#L69](https://github.com/bvschaik/julius/blob/016d5254c2b734dac5c56abccac05c0ba74cb934/src/building/house_service.c#L69)
[Source: Julius /src/city/culture.c#L45](https://github.com/bvschaik/julius/blob/016d5254c2b734dac5c56abccac05c0ba74cb934/src/city/culture.c#L45)
