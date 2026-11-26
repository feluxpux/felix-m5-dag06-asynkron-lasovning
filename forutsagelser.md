# Förutsägelser: asynkron kod

Regler:

1. Titta på snutten i `snuttar/sNN.js` (eller på sidan `index.html`). **Kör den inte än.**
2. Skriv din gissning i tabellen: utskrifterna i den ordning du tror att de kommer, separerade med `|`.
3. Kör snutten (knappen _Kör_). Skriv vad som faktiskt skrevs ut.
4. Hade du rätt? Skriv en regel med egna ord för varje snutt du gissade fel på.

| Snutt | Min gissning (i ordning)            | Faktisk utskrift                   | Rätt? | Min regel om jag hade fel |
| ----- | ----------------------------------- | ---------------------------------- | ----- | ------------------------- |
| 1     | 1: Beställer kaffe                  | 1: Beställer kaffe                 | ja    |                           |
|       | 2: Läser tidningen                  | 2: Läser tidningen                 |       |                           |
|       | 3: Kaffet är klart                  | 3: Kaffet är klart                 |       |                           |
| 2     | "A"                                 | A                                  | ja    |                           |
|       | "C"                                 | C                                  |       |                           |
|       | "B"                                 | B                                  |       |                           |
| 3     | start                               | start                              | ja    |                           |
|       | noll                                | noll                               |       |                           |
|       | kort                                | kort                               |       |                           |
|       | lång                                | lång                               |       |                           |
| 4     | inuti promise                       | inuti promise                      | ja    |                           |
|       | efter                               | efter                              |       |                           |
|       | then: klart                         | then: klart                        |       |                           |
| 5     | sync                                | sync                               | ja    |                           |
|       | promise                             | promise                            |       |                           |
|       | timeout                             | timeout                            |       |                           |
| 6     | först?                              | först?                             | 67ja  |                           |
|       | 6                                   | 6                                  |       |                           |
|       | 7                                   | 7                                  |       |                           |
| 7     | fel: slut på mjölk                  | fel: slut på mjölk                 | ja    |                           |
|       | städar                              | städar                             |       |                           |
|       |                                     |                                    |       |                           |
| 8     | beställer                           | beställer                          | ja    |                           |
|       | sätter mig                          | sätter mig                         |       |                           |
|       | bullen klar                         | bullen klar                        |       |                           |
|       | kaffet klart                        | kaffet klart                       |       |                           |
| 9     | väntar på båda                      |                                    |       |                           |
|       | "kaffe","bulle"                     |                                    |       |                           |
|       |                                     |                                    |       |                           |
| 10    | 163245, fast neråt siffraför siffra | 163245, fast neråt siffraförsiffra | ja    |                           |
|       |                                     |                                    |       |                           |
| 11    | c                                   | c                                  | ja    |                           |
|       | ab                                  | ab                                 |       |                           |

## Tre meningar med egna ord

1. JavaScript väntar inte på `setTimeout`,
2. En promise har tre tillstånd: ...
3. `then` körs alltid ...
