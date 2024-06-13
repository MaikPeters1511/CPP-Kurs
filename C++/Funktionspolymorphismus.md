### **Polymorphismus zur Kompilierungszeit**

Polymorphismus zur Kompilierungszeit findet statt, wenn ein Programm kompiliert wird. C++-Polymorphismus tritt in dieser Phase auf, wenn entweder eine Funktion oder ein Operator überladen ist. Diese Art von Polymorphismus wird auch als statische oder frühe Bindung bezeichnet.

Polymorphismus zur Kompilierungszeit gibt es in C++ in zwei Formen: Funktionsüberladung und Operatorüberladung.

**Funktionsüberladung**

Wie bereits erwähnt, können wir durch Funktionsüberladung dieselbe Funktion mehrfach verwenden, wobei die Aktion oder Ausgabe dieser Funktion vom zugewiesenen Datentyp abhängt. So funktioniert die Funktionsüberladung im Code:

```cpp
void Ausgabe(int Dessertnummer) {
    cout << "Die Anzahl der Desserts ist " << dessert_num << endl;
}
void Ausgabe(Float-Vorbereitung) {
    cout << "Vorbereitungszeit ist " << prep << " Minuten" << endl;
}
void Ausgabe(Zeichenfolge Dessert) {
    cout << "Der Nachtisch ist " << Nachtisch << endl;
}
int main() {
    int x; float y; Zeichenfolge z;
    cout << "Geben Sie eine Anzahl Desserts ein:" << endl;
    cin >> x;
    cout << "Geben Sie die AA-Vorbereitungszeit auf zwei Dezimalstellen genau ein:" << endl;
    cin >> y;
    cout << "Geben Sie den Namen eines Desserts ein:" << endl;
    cin >> z;
   
    Ausgabe(x);
    Ausgabe(y);
    Ausgabe(z);
    gebe 0 zurück;
}
```

Wir verwenden dieselbe _Ausgabe()-_ Funktion, um je nach Datentyp der Funktionseingabe ein anderes Ergebnis auszugeben. Das Programm fordert den Benutzer zur Eingabe einer Reihe von Werten auf und gibt diese Werte mit der richtigen Zeichenfolge zurück. Mit 6, 30,25 und Cookie erhalten wir 

Folgendes:
```output
Die Anzahl der Desserts beträgt 6
Die Vorbereitungszeit beträgt 30,25 Minuten
Der Nachtisch sind Kekse
```


Das Programm gibt basierend auf den Eingaben die richtigen Ausgaben zurück.