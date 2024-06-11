##### Schleife mit Ternärer ?:-Operator

```cpp
#include <iostream>  
  
using namespace std;  
  
int main() {  
  
    u_int32_t number;  
    cout << "Gib eine Zahl ein: ";  
    cin >> number;  
  
    cout << (number == 5 ? "Du hast richtig geraden" : "Rate nochmal");  
  
    return 0;  
}
```

```cpp
#include <iostream>  
  
using namespace std;  
  
int main() {  
  
    u_int32_t number;  
    cout << "Gib eine Zahl ein: ";  
    cin >> number;  
  
    if (number == 5)  
    {  
        cout << "Du hast richtig geraden";  
    }  
    else  
    {  
        cout << "Rate nochmal";  
    }  
  
    return 0;  
}
```

##### Ternärer ?:-Operator

Als Einschub und der Vollständigkeit halber soll hier der ternäre Operator ?: behandelt werden. Ternär bedeutet, dass der Operator drei Argumente benötigt. Dieser kann dazu dienen, innerhalb von Ausdrücken Teilausdrücke bedingt auszuwerten.

```cpp
inline int abs(int number) {
  // compute absolute value 
  return number > 0 ? number : -number;
}
```

Ist der vor dem Fragezeichen stehende Ausdruck true, so wird der Teilausdruck vor dem Doppelpunkt, sonst derjenige nach dem Doppelpunkt ausgewertet. Der resultierende Typ der beiden alternativen Ausdrücke muss gleich sein. Aufgrund der geringen Priorität dieses Operators und zur Verdeutlichung der Zusammengehörigkeit der Teilausdrücke sollte man sich angewöhnen, großzügig Klammern zu setzen.

```cpp
  int i1   =       3 > 4 ? 0 : 1;    //  i1   is 1
  int i2   = 3 * ( 3 > 4 ? 0 : 1 );  //  i1_3 is 3
  int i3   = 3 *   3 > 4 ? 0 : 1;    //  i2_3 is 0
```

Dieser Operator kann immer durch eine if-Anweisung vermieden werden, kann aber in vereinzelten Situationen klarer sein. Da er anderenfalls eine der zahlreichen Möglichkeiten in C/C++ ist, seine Programme für andere erfolgreich unlesbar zu gestalten, sollte man ihn sparsam einsetzen.

