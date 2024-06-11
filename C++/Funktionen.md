```cpp
#include <iostream>  
  
using namespace std;  
  
int main() {  
    char zeichenkette[] = "Hallo";  
  
// Bestimmung der Stringlänge  
    int laenge = 0;  
    while (zeichenkette[laenge] != '\0') {  
        laenge++;  
    }  
  
// Ausgabe der Stringlänge und des Inhalts  
    std::cout << "Länge des Strings: " << laenge << std::endl;  
    std::cout << "Stringinhalt: " << zeichenkette << std::endl;  
	  is_even(4); // true
	  is_even(3); // false
    return 0;  
}  
  
bool is_even(int32_t number) {  
    if(number % 2) { return true; }  
    else { return false;}  
}
```