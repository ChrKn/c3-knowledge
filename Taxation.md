# Taxation

## Simplified Formula

We can always calculate the tax a house's population is supposed to pay, given perfect 
tax collector coverage, by using the following formula:

$$
\begin{flalign}
& \frac{TaxMultiplier \times Population \times TaxRate \times DifficultyMultiplier}{20000} &
\end{flalign}
$$

Assuming a tax rate of 25%, 'very hard' difficulty and a Luxurious Palace (tax multiplier 
of 16) with 200 inhabitants, we end up with: 

$$
\begin{flalign}
& \frac{16 \times 200 \times 25 \times 75}{20000} = 300 &
\end{flalign}
$$

Note: You can obviously factor in the tax rate and difficulty multiplier as decimals if you prefer, 
and divide by 2 instead of 20,000. Internally, all calculations are done with integers.

$$
\begin{flalign}
& \frac{16 \times 200 \times 0.25 \times 0.75}{2} = 300 &
\end{flalign}
$$

## How it works

Every housing level has a tax multiplier (tm). These can be found [here](/Housing.md). 
Additionally, the amount of money the player earns is modified by a difficulty 
multiplier (dm).

| Difficulty | Multiplier |
|------------|------------|
| Very Easy  | 300%       |
| Easy       | 200%       |
| Normal     | 150%       |
| Hard       | 100%       |
| Very Hard  | 75%        |

[Source: Julius /src/game/difficulty.c#L6](https://github.com/bvschaik/julius/blob/016d5254c2b734dac5c56abccac05c0ba74cb934/src/game/difficulty.c#L6)

When calculating the tax amount a house's population (pop) pays, the game first calculates
the difficulty-adjusted tax rate multiplier (trm):

$$
\begin{flalign}
& trm = \frac{tm \times dm }{100} &
\end{flalign}
$$

Example (Luxurious Palace):

$$
\begin{flalign}
& trm = \frac{16 \times 75}{100} = 12 &
\end{flalign}
$$

[Source: Julius /src/city/finance.c#L188](https://github.com/bvschaik/julius/blob/016d5254c2b734dac5c56abccac05c0ba74cb934/src/city/finance.c#L188)

Then factors in the population to calculate their payments if the tax rate was 100%:

$$
\begin{flalign}
& max = pop \times trm &
\end{flalign}
$$

Example (Luxurious Palace):

$$
\begin{flalign}
& max = 200 \times 12 = 2400 &
\end{flalign}
$$

[Source: Julius /src/city/finance.c#L192](https://github.com/bvschaik/julius/blob/016d5254c2b734dac5c56abccac05c0ba74cb934/src/city/finance.c#L192)

The resulting number is then halved (why?) and multiplied by the tax rate (tr):

$$
\begin{flalign}
& tax = \frac{max}{2} \times \frac{tr}{100} &
\end{flalign}
$$

Example (Luxurious Palace):

$$
\begin{flalign}
& tax = \frac{2400}{2} \times \frac{25}{100} = 300 &
\end{flalign}
$$

[Source: Julius /src/city/finance.c#L213](https://github.com/bvschaik/julius/blob/016d5254c2b734dac5c56abccac05c0ba74cb934/src/city/finance.c#L213)
