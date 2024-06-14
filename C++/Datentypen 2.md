## Datentypen

### Integer-Daten

Für ganzzahlige Daten, auch Integer-Daten genannt, stehen die in der nachfolgenden Tabelle aufgeführten Datentypen zur Verfügung. Die Wertebereiche der Datentypen bei Verwendung des MinGW-Compilers sowie des Visual Studios sind ebenfalls aufgeführt.

| Datentyp    | Wertebereich             |
| ----------- | ------------------------ |
| char        | -128...127               |
| short       | -32768...32767           |
| long (=int) | -2147483648...2147483647 |
|             |                          |





long long

-9223372036854775808...9223372036854775807

unsigned char

0...255

unsigned short

0...65535

unsigned long (=unsigned int)

0...4294967295

unsigned long long

0...18446744073709551615

### Gleitkomma-Daten

Für die Verarbeitung von Gleitkommazahlen stehen 3 Datentypen zur Verfügung. Diese Datentypen unterscheiden sich zum einen ebenfalls im Wertebereich und zum anderen durch die Anzahl der Stellen, mit denen der Datentyp rechnet.

Datentyp

Min/Max

Berechnung 1./3.

float

-/+ 3.403e+38

0.3333333432674407959

double

-/+ 1.798e+308

0.33333333333333331483

long double

-/+ 1.190e+4932

0.33333333333333333334

Beim Visual Studio Compiler sind die Datentypen _long double_ und _double_ identisch!

### Zeichen

Zum Abspeichern von Zeichen wird in der Regel der Datentyp _char_ verwendet. Er dient zur Aufnahme eines 1 Byte großen Zeichens.

### Sonstige Datentypen

Der Datentyp _bool_ kann nur die beiden Zustände (Werte) _true_ und _false_ annehmen.

Und der Datentyp _void_ ist ein unvollständiger Datentyp, der hauptsächlich als Returntyp bei (Member-)Funktionen oder im Zusammenspiel mit Zeigern verwendet wird. Auf ihn werden wir später zurückkommen.

Es sei an dieser Stelle darauf hingewiesen, dass es noch weitere Datentypen gibt, die erst später behandelt werden.

## Variablen

### Definition

Veränderbar Daten werden in sogenannten Variablen abgelegt. Bei der Definition einer Variable wird zuerst deren Datentyp und anschließend der Name der Variable angegeben. Für den Augenblick ist es noch nicht relevant, ob die Definition einer Variable vor oder innerhalb der _main()_-Funktion erfolgt.

Der Name der Variable muss eindeutig sein und unterliegt folgenden Einschränkung:

- Er muss mit einem Buchstaben oder Unterstrich _ beginnen,
- darf nicht mit einem reservierten Schlüsselwort übereinstmmen und
- darf keine Umlaute oder ß enthalten. 

`// Header-Datei einbinden   #include <iostream>   #include <format>      // Definition einer char- und unsigned long Variable   char cvar;   unsigned long ulvar;      ``   int main()   {      // Definition einer bool und float Variable      bool bvar;      float fvar;      // Ausgabe der Variablen      std::cout << std::format("char: {:x}, unsigned long: {}\n"                               "bool: {}, float: {:8.2f}\n",                                cvar, ulvar, bvar, fvar);   }   `

char: 0, unsigned long: 0  
bool: false, float:      0.00

Mehrere Variablen desselben Datentyps können in einer Anweisung definiert werden, wobei die Variablennamen durch Komma getrennt werden.

`short svar1, svar2;  // Zwei short-Variablen   float fvar1, fvar2;  // und zwei float-Variablen   `

### Initialisierung von Variablen

Variablen können bei ihrer Definition mit einem Datum initialisiert werden. Dies erfolgt in der Art, dass nach dem Variablenname der Zuweisungsoperator = folgt und anschließend der Initialwert.

`short svar1=1, svar2=10;       // Zwei short-Variablen   float fvar1=1.2f, fvar2=3.14f; // und zwei float-Variablen initialisieren`

## Konstanten

Konstanten sind Daten, die nach ihrer Definition nicht mehr geändert werden können.

### Literale (unbenannte Konstanten)

Ein Literal ist die direkte Angabe eines Wertes, wie z.B. die Zahl 5 oder der String "Dies ist ein Literal".

Ganzzahl-Literale besitzen standardmäßig den kleinsten Datentyp, in dem ihr Wert dargestellt werden kann, aber mindestens den Datentyp _int_. Um ein Ganzzahl-Literal explizit einem Datentyp zuzuordnen, wird der Wert mit einem Präfix oder Suffix erweitert. Die Groß-/Kleinschreibung spielt hier ausnahmsweise keine Rolle

Datentyp

Präfix

Suffix

Beispiel

Binär-Literal

0b

0b1011'0011

Oktal-Literal

0

0123

Hex-Literal

0x

0xFE12'12C2

unsigned

u

10U

long

l

1'000'000L

unsigned long

ul

1'000'000UL

long long

ll

1'000'000LL

unsigned long long

ull

1'000'000ULL

Schreiben Sie niemals 0010, wenn Sie ein Dezimal-Literal definieren! Diese Zahl entspricht der Oktalzahl 10 und ist dezimal 8!

Gleitkomma-Literale bestehen aus Ziﬀern und einem Dezimalpunkt. Optional kann ein Gleitkomma-Literal einen Exponenten enthalten. Standardmäßig sind Gleitkomma-Literale vom Datentyp _double_.

Um einem Gleitkomma-Literal einen von _double_ abweichenden Datentyp zuzuweisen, wird das Literal mit einem Suffix laut nachfolgender Tabelle erweitert. Auch hier spielt die Groß-/Kleinschreibung keine Rolle

Datentyp

Suffix

Beispiel

float

f

1.2e+3f oder 3.14f

double

1.2E+3 oder 3.14

long double

l

1.2E-4L oder 3.14L

Zeichen-Literale sind einzelne Buchstaben oder auch Escape-Sequenzen, die in Hochkomma eingeschlossen werden. Sie besitzen den Datentyp _char_.

String-Literale werden in Anführungszeichen eingeschlossen und haben den Datentyp _const char[n]_ (_char_-Feld mit _n_ konstanten Zeichen). Das letzte Zeichen eines String-Literals ist immer eine abschließende 0 (Null).

### Benannte Konstanten

Benannte Konstanten werden prinzipiell wie Variablen definiert, d. h., sie haben einen Datentyp und einen Namen. Zusätzlich wird jedoch vor dem Datentyp das Schlüsselwort _const_ gestellt. Benannte Konstanten müssen bei ihrer Definition initialisiert werden.

`const int SIZE=10;        // int-Konstante   const double PI=3.1416;   // double-Konstante   `

### constexpr Spezifizierer

Der Spezifizierer _constexpr_ weist den Compiler an, den Initialisierungsausdruck zum Zeitpunkt des Übersetzungsvorgangs auszuwerten. Kann der Ausdruck während des Übersetzungsvorgangs nicht berechnet werden, erzeugt dies einen Fehler.

`int main()   {       int anyVar = 10;               // Variable def./init.       const int anyConst = anyVar;   // Konstante definieren       constexpr int anyCExpr1 = 10;  // Ok       constexpr int anyCExpr2 = anyVar; // Fehler! anyVar ist kein konstanter Ausdruck   }   `

## auto Datentyp

Werden Daten bei ihrer Definition initialisiert, kann der Compiler aufgrund des Datentyps des Initialisierungsausdrucks den Datentyp der Variable bestimmen. Hierzu wird der explizite Datentyp bei der Definition des Datums durch das Schlüsselwort _auto_ ersetzt.

Das obige Beispiel mit auto-Variablen sieht dann wie folgt aus:

`// Header-Datei einbinden   #include <iostream>   #include <format>      // Definition einer char Variable und unsigned long Konstante   auto cvar = 'A';   const auto ulvar= 1'000'000UL;      int main()   {      // Definition einer bool Variable und float Konstante      auto bvar = false;      const auto fvar = 1.8888f;      // Ausgabe der Daten      std::cout << std::format("char: {:x}, unsigned long: {}\n"                               "bool: {}, float: {:8.2f}\n",                                cvar, ulvar, bvar, fvar);   }   `

char: 41, unsigned long: 1000000  
bool: false, float:        1.89

## Referenz-Variablen

Referenz-Variablen enthalten Verweise auf bereits definierte Daten. Um eine Referenz-Variable zu definieren, folgt nach dem Datentyp das Symbol _&_, dann der Name der Referenz-Variable und anschließend der Zuweisungsoperator sowie der Name des Datums, auf die die Referenz verweisen soll.

`int iVar;              // int-Variable definieren   int& refVar = iVar;    // Referenz-Variable definieren, verweist auf iVar`

Referenz-Variablen unterliegen folgenden Einschränkungen:

- Referenz-Variablen müssen immer einen Verweis enthalten, d.h. sie müssen bei ihrer Definition initialisiert werden.
- Nach der Initialisierung kann der Verweis nicht mehr geändert werden. Wird einer Referenz-Variable ein Datum zugewiesen, so wird das Datum in die Variable übernommen, auf die die Referenz-Variable verweist.
- Der Datentyp der Referenz-Variable muss mit dem Datentyp der Variable übereinstimmen, auf die verwiesen wird.

Vielleicht mag im Augenblick die Verwendung von Referenz-Variablen noch etwas merkwürdig erscheinen. Später aber werden Sie den Einsatz von Referenzen noch zu schätzen wissen.

## decltype Spezifizierer

Mit Hilfe des Spezifizierers _decltype()_ kann der Datentyp eines Ausdrucks bestimmt und damit unter anderem der Datentyp eines Datums indirekt festlegt werden. Die allgemeine Syntax lautet:

`decltype (AUSDRUCK)`

Wird für _AUSDRUCK_ ein Datum eingesetzt, liefert _decltype()_ den Datentyp des Datums zurück. Wird für _AUSDRUCK_ ein Funktionsaufruf eingesetzt, liefert _decltype()_ den Returntyp der Funktion. Es gibt für _AUSDRUCK_ noch weitere Möglichkeiten, auf die in dieser Einführung aber nicht weiter eingegangen werden soll.

`// Header-Datei einbinden   #include <iostream>   #include <format>      ``   int main()   {      // float-Variable definieren      float var1;      // Variable mit demselben Datentyp wie var1 definieren      decltype(var1) var2;      // Variable definieren, die einen von main()      // zurueckgegebenen Wert aufnehmen koennte      decltype(main()) retVal;      // Datentyp der Variablen ausgeben      // Der verwendete Operator typeid wird spaeter noch behandelt      // In diesem Beispiel gibt typeid(x).name() den Namen des      // Datentyps x aus.       std::cout << std::format("Datentyp var1: {}, Datentyp var2: {}\n",                               typeid(var1).name(), typeid(var2).name());      std::cout << std::format("Returntyp main(): {}, Datentyp retVal: {}\n",                               typeid(int).name(),typeid(retVal).name());   }   `

Datentyp var1: float, Datentyp var2: float  
Returntyp main(): int, Datentyp retVal: int

Der Name eines Datentyps ist nicht standardisiert. So liefert der MinGW-Compiler z.B. anstelle von float den Buchstaben f und anstelle von int den Buchstaben i.

## sizeof Operator

Um die von einem Datentyp oder Datum benötigte Anzahl von Bytes zu bestimmen, wird der _sizeof_-Operator verwendet.

`auto intBytes = sizeof(int);   short sVar;   auto shortBytes = sizeof(sVar);   `

Damit wollen wir die Behandlung von Daten abschließen und wenden uns den Operatoren zu.