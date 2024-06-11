```cpp
#include <iostream>

#define ANTWORT 42
#define PI 3.1415

int main()
{
	const int konstante_zahl = 21;
	std::cout << ANWORT << std:endl;
	std::cout << PI << std:endl;
}
```

Präcompiler wird über #define definiert. Es wird zu Begin im Code alles wo die Konstante steht ersetzt.

Eine Konstante ist ein Immutable Values.