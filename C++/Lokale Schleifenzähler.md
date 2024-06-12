Lokale Schleifenzählerdeklaration in FOR

In C++ können Sie einen Zähler direkt in einer FOR-Schleifen-Deklaration initialisieren, wie im folgenden Beispiel gezeigt:

```cpp
#include <iostream>  
  
int main() {  
  
    for (int i = 0; i < 100; ++i)  
    {  
        std::cout << i << std::endl;  
    }  
  
    for (int i = 0; i < 4; ++i)  
    {  
        std::cout << i << std::endl;  
    }  
    return 0;  
}
```

In diesem Beispiel wird der Variable i beim Start der Schleife ein Wert von 0 zugewiesen. Nach jedem Durchlauf der Schleife wird i mit i++ inkrementiert, bis i schließlich 10 erreicht, woraufhin die Schleife beendet wird. Der Zähler i ist nur in dem Bereich gültig, der von dieser bestimmten FOR-Schleife definiert wird. Dies wird als lokale Schleifenzähler-Deklaration bezeichnet.