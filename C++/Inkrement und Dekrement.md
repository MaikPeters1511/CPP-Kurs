
| `i++;`    | Postinkrement              |
| --------- | -------------------------- |
| `++i;`    | Präinkrement               |
| `i += j;` | _i_ wird um _j_ erhöht     |
| `i--;`    | Postdekrement              |
| `--i;`    | Prädekrement               |
| `i -= j;` | _i_ wird um _j_ verringert |


Wird eine Inkrement- oder Dekrement-Operation in einer Anweisung innerhalb eines anderen Ausdruckes verwendet, muss unterschieden werden, ob die Werterhöhung oder - verminderung vor oder nach der Auswertung des übergeordneten Ausdrucks stattfindet. Beim Prädekrement wird dem übergeordneten Ausdruck der bereits verringerte, beim Postdekrement hingegen der ursprüngliche Wert übergeben.

|                  |                             | Erklärung                           | Beispiel in C++ -Code               |
| ---------------- | --------------------------- | ----------------------------------- | ----------------------------------- |
| **Inkrement**    | Postinkrement               | Nachherige Werterhöhung.            | int i = 5;<br>int c = i++; // c = 5 |
| **Präinkrement** | Vorherige Werterhöhung      | int i = 5;<br>int d = ++i; // d = 6 |                                     |
| **Dekrement**    | Postdekrement               | Nachherige Wertverkleinerung.       | int i = 5;<br>int e = i--; // e = 5 |
| **Prädekrement** | Vorherige Wertverkleinerung | int i = 5;<br>int f = --i; // f = 4 |                                     |
