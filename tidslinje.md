# Tidslinje: rita vad som händer

Välj snutt 5 och snutt 10. Fyll i tabellerna steg för steg. Skriv vad som ligger i varje del **efter** varje steg.

Förklaring:

- **Anropsstacken** är den kod som körs just nu.
- **Microtask-kön** är promise-callbacks som väntar på att få köra.
- **Task-kön** är timer-callbacks och liknande som väntar på att få köra.
- Regel: när stacken är tom körs först ALLA microtasks, sedan EN task, sedan tomma microtasks igen, och så vidare.

## Snutt 5

| Steg | Vad händer                          | Stacken                                  | Microtask-kön    | Task-kön         | Utskrift hittills      |
| ---- | ----------------------------------- | ---------------------------------------- | ---------------- | ---------------- | ---------------------- |
| 1    | setTimeout anropas                  | setTimeout                               | tom              | timeout-callback | inget                  |
| 2    | Promise.resolve().then(...) anropas | Promise.resolve().then                   | promise-callback | timeout-callback | inget                  |
| 3    | console.log("sync")                 | console.log("sync")                      | tom              | timeout-callback | sync                   |
| 4    | Stacken tom: vad körs först?        | promise-callback, console.log("promise") | tom              | timeout-callback | sync, promise          |
| 5    | Nästa                               | timeout-callback, console.log("timeout") | tom              | tom              | sync, promise, timeout |

## Snutt 10

| Steg | Vad händer                       | Stacken                                              | Microtask-kön | Task-kön               | Utskrift hittills |
| ---- | -------------------------------- | ---------------------------------------------------- | ------------- | ---------------------- | ----------------- |
| 1    | console.log("1")                 | console.log("1")                                     | tom           | tom                    | 1                 |
| 2    | första setTimeout                | setTimeout                                           | tom           | callback 2             | 1                 |
| 3    | Promise.resolve().then(3)        | Promise.resolve().then                               | callback 3    | callback 2             | 1                 |
| 4    | andra setTimeout                 | setTimeout                                           | callback 3    | callback 2, callback 4 | 1                 |
| 5    | console.log("6")                 | console.log("6")                                     | callback 3    | callback 2, callback 4 | 1,6               |
| 6    | stacken tom, microtask-kön först | callback 3, console.log("3")                         | tom           | callback 2, callback 4 | 1,6,3             |
| 7    | första tasken                    | callback 2, console.log("2")                         | tom           | callback 4             | 1,6,3,2           |
| 8    | andra tasken                     | callback 4, console.log("4"), Promise.resolve().then | callback 5    | tom                    | 1,6,3,2,4         |
| 9    | microtask 5                      | callback 5, console.log("5")                         | tom           | tom                    | 1,6,3,2,4,5       |

## Min förklaring i en mening

Varför kommer en promise-callback före en timer med 0 ms?
Promise-callbacks hamnar i microtask-kön, som töms först när stacken är tom.
Timern hamnar i task-kön, som körs efter microtasks
