Headerdateien haben als Endung .h oder .hpp

.h / .hpp => Declaration
.cc / .cpp => Definition

Bsp: Game.cpp => Game.h

Eine Header-Datei ist eine Datei, die in C oder C++ üblicherweise Deklarationen von Funktionen, Variablen und/oder Klassen enthält. Diese Deklarationen dienen dazu, dem Compiler Informationen über diese Elemente zu geben, bevor sie tatsächlich im Code definiert oder verwendet werden. Header-Dateien haben in der Regel die Endung ".h" oder ".hpp" und werden häufig mithilfe der Präprozessor - Anweisungen #include in andere Quellcodedateien eingefügt.

Hier ein einfaches Beispiel für eine Header-Datei in C++:
```cpp
// MeineFunktionen.hpp
#ifndef MEINEFUNKTIONEN_HPP
#define MEINEFUNKTIONEN_HPP

void meineFunktion();

#endif // MEINEFUNKTIONEN_HPP
```

In der obigen Datei wird die Funktion meineFunktion() deklariert, aber nicht definiert. Die Definition der Funktion würde dann in einer separaten Quellcodedatei (z. B. MeineFunktionen.cpp) erfolgen.
Header-Dateien sind ein grundlegendes Element der Struktur in größeren C++-Projekten und helfen dabei, den Code zu organisieren und wiederverwendbar zu machen.