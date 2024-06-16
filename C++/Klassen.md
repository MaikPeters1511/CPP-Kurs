
```cpp
#include <iostream>  
#include <memory>  
  
struct Beispiel  
{  
    const char* text;  
    int zahl1;  
    double zahl2;  
};  
  
class BeispielClass  
{  
public:  
    const char* text; // das sind Attribute der Klasse  
    int zahl1;  
    double zahl2;  
  
    void was_bin_ich() const   // Das sind Methoden der Klasse  
    {  
        std::cout << "Methode ich gehöre: " << this << std::endl;  
    }  
    void info() const  
    {  
        std::cout << "Die Instanz der Klasse BeispielClass an Speicheradresse " << this << " hat folgende Werte: \n";  
        std::cout << "text = " << this->text << '\n';  
        std::cout << "zahl1 = " << this->zahl1 << '\n';  
        std::cout << "zahl2 = " << zahl2 << '\n'; // Geht auch ohne this  
    }  
};  
  
int main() {  
    Beispiel ein = {};  
    Beispiel zwe = {};  
    Beispiel drei = {};  
  
    ein.text =R"(Hallo Welt)";  
    zwe.zahl1 = 12;  
    drei.zahl2 = 3.12;  
  
    BeispielClass eins{};  
    std::cout << "eins hat den Pointer: " << &eins << std::endl;  
    eins.text = "EINS";  
    eins.zahl1 = 12;  
    eins.zahl2 = 3.12;  
  
    BeispielClass zwei{};  
    zwei.text = "Hello, World!";  
    zwei.zahl1 = 5;  
    zwei.zahl2 = 10.5;  
    zwei.info();  
  
    // BeispielClass* vier = nullptr; // Pointer am Anpfang auf nichts zeigen lassen  
    // vier = new BeispielClass();    
    
    const auto* fuenf = new BeispielClass(); // Pointer erzeugen und direk eine neue Instanz der Klasse zeigen lassen  
  
    std::unique_ptr<BeispielClass> vier(nullptr);  
    vier = std::make_unique<BeispielClass>();  
    vier->text = "Hi";  
    vier->zahl1 = 42;  
    vier->zahl2 = 1.23;  
    vier->info();  
  
    // delete(vier); // Löschen der Pointer am Schluss  
    delete(fuenf);  
    return 0;  
}
```

