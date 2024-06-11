
```cpp
#include <iostream>  
#include <cstdlib>  
  
// Funktion mit einem Werteparameter  
void erhoehe_um_zehn_w(int zahl) {  
    std::cout << "Vor dem Aufruf der Erhöhung hat zahl den Wert " << zahl << std::endl;  
    zahl += 10;  
    std::cout << "Nach dem Aufruf der Erhöhung hat zahl den Wert " << zahl << std::endl;  
};  
// Vorteil: Das Orginal aus dem Hauptprogramm kann nicht verändert werden  
//          Kann Parameter lokal verändert, falls erwünscht  
// Nachteil: Das Orginal aus dem Hauptprogramm kann nicht verändert werden  
//           Es wird eine Kopie erzeugt, je nach Datentypen das nicht besonders effizient.  
  
// Funktion mit einem Pointer  
void erhoehe_um_zehn_p(int* zahl) {  
    std::cout << "Vor dem Aufruf der Erhöhung hat zahl den Wert " << *zahl << std::endl;  
    *zahl += 10;  
    std::cout << "Nach dem Aufruf der Erhöhung hat zahl den Wert " << *zahl << std::endl;  
};  
// Vorteil: Man kann den Inhalt, auf welchen der Pointer zeigt, verändern  
// Nachteil: Man kann den Inhalt, auf welchen der Pointer zeigt, verändern  
//           Bei Aufruf muss der Benutzer dran denken eine Referenz zu übergeben  
//           Dereferenz innerhalb der Funtion nötig  
  
// Funktion mit Übergabe einer Referenz  
void erhoehe_um_zehn_r(int &zahl) {  
    std::cout << "Vor dem Aufruf der Erhöhung hat zahl den Wert " << zahl << std::endl;  
    zahl += 10;  
    std::cout << "Nach dem Aufruf der Erhöhung hat zahl den Wert " << zahl << std::endl;  
};  
// Vorteil: Es wirk keine Kopie erzeugt. Sehr effizient  
//          Handhabung wie klassischer Werteparameter; also keine Dereferenzierung nötig  
//          Orginal kann verändert werden.  
// Nachteil: Orginal kann verändert werden, evtl. weiss der Aufrufer es noch nicht einmal  
  
// Funktion mit Überabe einer Const Referenz  
void erhoehe_um_zehn_rc(const int &zahl) {  
    std::cout << "Vor dem Aufruf der Erhöhung hat zahl den Wert " << zahl << std::endl;  
    //zahl += 10; //weil geht nicht  
    std::cout << "Nach dem Aufruf der Erhöhung hat zahl den Wert " << zahl << std::endl;  
};  
  
int main() {  
    int i = 42;  
    std::cout << "Vor dem Aufruf der Funktion hat i den Wert " << i << std::endl;  
    erhoehe_um_zehn_r(i);  
    erhoehe_um_zehn_w(i);  
    erhoehe_um_zehn_p(&i);  
    std::cout << "Vor dem Aufruf der Funktion hat i den Wert " << i << std::endl;  
}
```