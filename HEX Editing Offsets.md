# Change scenario settings in Caesar 3 savegames via hex editing

By courtesy of [DDRJake](https://www.twitch.tv/ddrjake)

**Instructions**

1. Open your save file with [C3GameExplorer](https://caesar3.heavengames.com/downloads/showfile.php?fileid=914)
2. Save your file as an uncompressed C3 format (.c3u format)
3. Open your .c3u file with the hex editor of your choice
4. Locate the offsets listed below and change to your liking
5. Save the .c3u file from your hex editor
6. Load the .c3u file in C3GameExplorer (actually reload it)
7. Save it as a .sav file
8. Load your new .sav file in Caesar 3 and enjoy

**Offsets**

0x126140 – Set to `01` for favour locked at 50 and removal of all win conditions. Lets you play forever.
0x126244 – Gladiator Revolt.  `01` is ON, `00` is OFF
0x126248 – Year of gladiator revolt
0x12624c – Change of Emperor (resets favour to 50) `01` is ON, `00` is OFF
0x126250 – Year change of Emperor occurs
0x126254 – Sea trade problems. `01` is ON, `00` is OFF
0x126258 – Land trade problems. `01` is ON, `00` is OFF
0x12625c – Rome raises wages. `01` is ON, `00` is OFF
0x126260 – Rome lowers wages. `01` is ON, `00` is OFF
0x126264 – Rats Contaminate Water. `01` is ON, `00` is OFF
0x126268 – Iron Mine Collapses. `01` is ON, `00` is OFF
0x12626c – Clay Pit Floods. `01` is ON, `00` is OFF
0x126384 – End date. Set to `00` to disable the game over after a certain date