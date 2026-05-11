# Change scenario settings in Caesar 3 savegames via hex editing

## Instructions

1. Open your save file with [C3GameExplorer](https://caesar3.heavengames.com/downloads/showfile.php?fileid=914)
2. Save your file as an uncompressed C3 format (.c3u format)
3. Open your .c3u file with the hex editor of your choice
4. Locate the offsets listed below and change to your liking
5. Save the .c3u file from your hex editor
6. Load the .c3u file in C3GameExplorer (actually reload it)
7. Save it as a .sav file
8. Load your new .sav file in Caesar 3 and enjoy

## Offsets

* 0x126140 – Set to `01` for favour locked at 50 and removal of all win conditions. Lets you play forever.
* 0x126244 – Gladiator Revolt.  `01` is ON, `00` is OFF
* 0x126248 – Year of gladiator revolt
* 0x12624c – Change of Emperor (resets favour to 50) `01` is ON, `00` is OFF
* 0x126250 – Year change of Emperor occurs
* 0x126254 – Sea trade problems. `01` is ON, `00` is OFF
* 0x126258 – Land trade problems. `01` is ON, `00` is OFF
* 0x12625c – Rome raises wages. `01` is ON, `00` is OFF
* 0x126260 – Rome lowers wages. `01` is ON, `00` is OFF
* 0x126264 – Rats Contaminate Water. `01` is ON, `00` is OFF
* 0x126268 – Iron Mine Collapses. `01` is ON, `00` is OFF
* 0x12626c – Clay Pit Floods. `01` is ON, `00` is OFF
* 0x126384 – End date. Set to `00` to disable the game over after a certain date

Information by courtesy of [DDRJake](https://www.twitch.tv/ddrjake).

## Changing the month, an invasion takes place

The months are indexed from 0 to 11. 0 is January, 1 is February, etc.

The game only plans invasions for the months 2 to 9, so March to October. Other values 
are possible, though.

* 0x1262A4 – invasion[0].month
* 0x1262A5 – invasion[1].month
* 0x1262A6 – invasion[2].month
* 0x1262A7 – invasion[3].month
* 0x1262A8 – invasion[4].month
* 0x1262A9 – invasion[5].month
* 0x1262AA – invasion[6].month
* 0x1262AB – invasion[7].month
* 0x1262AC – invasion[8].month
* 0x1262AD – invasion[9].month
* 0x1262AE – invasion[10].month
* 0x1262AF – invasion[11].month
* 0x1262B0 – invasion[12].month
* 0x1262B1 – invasion[13].month
* 0x1262B2 – invasion[14].month
* 0x1262B3 – invasion[15].month
* 0x1262B4 – invasion[16].month
* 0x1262B5 – invasion[17].month
* 0x1262B6 – invasion[18].month
* 0x1262B7 – invasion[19].month