# Trading 

## Maximum units traders are willing to sell

In addition to the annual trade limit, traders will only sell goods while the 
city's warehouse stock remains below a certain level.

Only goods stored in warehouses are counted for this calculation. Goods kept in 
production buildings or granaries do not count toward the total stock.

### Food and finished Goods (Wheat, Fruit, Pottery, ...)

| Population | Max. Stock |
|------------|------------|
| < 2000     | 10         |
| < 4000     | 20         |
| < 6000     | 30         |
| ≥ 6000     | 40         |

### Marble and Weapons

Max. Stock: 10.

### Resources for processing (Iron, Vines, ...)

Max. Stock is based on the following formula:

$$
\begin{flalign}
& 2 + 2 \times Active \ Industries &
\end{flalign}
$$

[Source: Julius /src/empire/empire.c#L183](https://github.com/bvschaik/julius/blob/016d5254c2b734dac5c56abccac05c0ba74cb934/src/empire/empire.c#L183)