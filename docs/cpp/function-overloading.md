---
title: Funktionsüberladung
ms.date: 03/27/2019
helpviewer_keywords:
- function overloading [C++], about function overloading
- function overloading
- declaring functions [C++], overloading
ms.assetid: 3c9884cb-1d5e-42e8-9a49-6f46141f929e
ms.openlocfilehash: 6cc432e404a7a66de63cf87f0fe87f0ccdcb5d70
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565973"
---
# <a name="function-overloading"></a>Funktionsüberladung

C++ lässt die Angabe mehrerer Funktionen mit dem gleichen Namen im gleichen Gültigkeitsbereich zu. Diese Funktionen aufgerufen werden *überladen* Funktionen. Überladene Funktionen ermöglichen Ihnen das Bereitstellen anderer Semantiken für eine Funktion in Abhängigkeit von die Art und Anzahl von Argumenten.

Z. B. eine `print` -Funktion, akzeptiert eine `std::string` Argument möglicherweise sehr unterschiedliche Aufgaben als eines, das ein des Typs Argument durchführen **doppelte**. Überladen von erspart Ihnen, Namen zu verwenden, z. B. `print_string` oder `print_double`. Zum Zeitpunkt der Kompilierung wählt der Compiler an, welche Überladung verwendet abhängig von den Typ der Argumente, die durch den Aufrufer übergeben.  Wenn Sie aufrufen `print(42.0)`, und klicken Sie dann die `void print(double d)` -Funktion wird aufgerufen werden. Wenn Sie aufrufen `print("hello world")`, und klicken Sie dann die `void print(std::string)` Überladung aufgerufen werden.

Sie können sowohl Memberfunktionen und nicht-Memberfunktionen überladen. Die folgende Tabelle zeigt, welche Teile einer Funktionsdeklaration von C++ verwendet werden, um zwischen Gruppen von Funktionen mit dem gleichen Namen und dem gleichen Gültigkeitsbereich zu differenzieren.

### <a name="overloading-considerations"></a>Überlegungen zur Überladung

|Funktionsdeklarationselement|Wird zum Überladen verwendet?|
|----------------------------------|---------------------------|
|Funktionsrückgabetyp|Nein|
|Anzahl der Argumente|Ja|
|Typ der Argumente|Ja|
|Vorhandensein oder Abwesenheit von Auslassungszeichen|Ja|
|Verwenden von **Typedef** Namen|Nein|
|Nicht angegebene Arraygrenzen|Nein|
|**const** oder **volatile**|Ja, wenn auf den gesamten Funktion angewendet|
|[Ref-qualifiers](#ref-qualifiers)|Ja|

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht, wie das Überladen verwendet werden kann.

```cpp
// function_overloading.cpp
// compile with: /EHsc
#include <iostream>
#include <math.h>
#include <string>

// Prototype three print functions.
int print(std::string s);             // Print a string.
int print(double dvalue);            // Print a double.
int print(double dvalue, int prec);  // Print a double with a
                                     //  given precision.
using namespace std;
int main(int argc, char *argv[])
{
    const double d = 893094.2987;
    if (argc < 2)
    {
        // These calls to print invoke print( char *s ).
        print("This program requires one argument.");
        print("The argument specifies the number of");
        print("digits precision for the second number");
        print("printed.");
        exit(0);
    }

    // Invoke print( double dvalue ).
    print(d);

    // Invoke print( double dvalue, int prec ).
    print(d, atoi(argv[1]));
}

// Print a string.
int print(string s)
{
    cout << s << endl;
    return cout.good();
}

// Print a double in default precision.
int print(double dvalue)
{
    cout << dvalue << endl;
    return cout.good();
}

//  Print a double in specified precision.
//  Positive numbers for precision indicate how many digits
//  precision after the decimal point to show. Negative
//  numbers for precision indicate where to round the number
//  to the left of the decimal point.
int print(double dvalue, int prec)
{
    // Use table-lookup for rounding/truncation.
    static const double rgPow10[] = {
        10E-7, 10E-6, 10E-5, 10E-4, 10E-3, 10E-2, 10E-1,
        10E0, 10E1,  10E2,  10E3,  10E4, 10E5,  10E6 };
    const int iPowZero = 6;

    // If precision out of range, just print the number.
    if (prec < -6 || prec > 7)
    {
        return print(dvalue);
    }
    // Scale, truncate, then rescale.
    dvalue = floor(dvalue / rgPow10[iPowZero - prec]) *
        rgPow10[iPowZero - prec];
    cout << dvalue << endl;
    return cout.good();
}
```

Der vorhergehende Code zeigt das Überladen der `print`-Funktion im Dateigültigkeitsbereich an.

Das Standardargument wird nicht als Teil des Funktionstyps betrachtet. Aus diesem Grund ist es nicht verwendet, beim Auswählen überladener Funktionen. Zwei Funktionen, die sich nur bei den Standardargumenten unterscheiden, werden als mehrfache Definitionen und nicht als überladene Funktionen betrachtet.

Standardargumente können nicht für überladene Operatoren angegeben werden.

## <a name="argument-matching"></a>Argumentübereinstimmung

Überladene Funktionen werden für die beste Übereinstimmung von Funktionsdeklarationen im aktuellen Bereich für Argumente ausgewählt, die im Funktionsaufruf angegeben werden. Wenn eine passende Funktion gefunden wird, wird diese Funktion aufgerufen. "Passend" in diesem Kontext bedeutet entweder:

- Ein exakte Übereinstimmung wurde gefunden.

- Eine triviale Konvertierung wurde ausgeführt.

- Eine ganzzahlige Heraufstufung wurde ausgeführt.

- Eine Standardkonvertierung zum gewünschten Argumenttyp ist vorhanden.

- Eine benutzerdefinierte Konvertierung (entweder Konvertierungsoperator oder Konstruktor) auf den gewünschten Argumenttyp ist vorhanden.

- Es wurden durch Ellipsen dargestellte Argumente gefunden.

Der Compiler erstellt einen Satz Kandidatenfunktionen für jedes Argument. Kandidatenfunktionen sind Funktionen, in denen das tatsächliche Argument an dieser Position in den Typ des formalen Arguments konvertiert werden kann.

Ein Satz von „am besten passenden Funktionen“ wird für jedes Argument erstellt, und die ausgewählte Funktion ist die Schnittmenge aller Sätze. Wenn die Schnittmenge mehr als eine Funktion enthält, ist das Überladen mehrdeutig und generiert einen Fehler. Die letztendlich ausgewählte Funktion stimmt stets besser überein als jede andere Funktion in der Gruppe für mindestens ein Argument. Ist kein deutlicher Sieger auszumachen, generiert der Funktionsaufruf einen Fehler aus.

Berücksichtigen Sie die folgenden Deklarationen (Funktionen sind zur Identifikation der folgenden Erläuterung als `Variant 1`, `Variant 2` und `Variant 3` gekennzeichnet):

```cpp
Fraction &Add( Fraction &f, long l );       // Variant 1
Fraction &Add( long l, Fraction &f );       // Variant 2
Fraction &Add( Fraction &f, Fraction &f );  // Variant 3

Fraction F1, F2;
```

Betrachten Sie folgende Anweisung:

```cpp
F1 = Add( F2, 23 );
```

Die vorhergehende Anweisung erstellt zwei Sätze:

|Legen Sie 1 fest: Kandidatenfunktionen, die erstes Argument vom Typ Anteil haben.|Legen Sie 2: Kandidat Funktionen, deren zweites Argument konvertiert werden können Typ **Int**|
|--------------------------------------------------------------------------|-----------------------------------------------------------------------------------|
|Variant 1|Variant 1 (**Int** konvertiert werden kann, um **lange** mithilfe einer standardkonvertierung)|
|Variant 3||

Funktionen in Satz 2 sind Funktionen, für die sind implizite Konvertierungen vom tatsächlichen Parametertyp in den formalen Parametertyp und zwischen diesen Funktionen es gibt eine Funktion, die für die "Kosten" des tatsächlichen Parametertyps in den formalen Parametertyp konvertiert ist die kleinste.

Die Schnittmenge dieser beiden Sätze ist "Variant 1". Ein Beispiel für einen mehrdeutigen Funktionsaufruf ist:

```cpp
F1 = Add( 3, 6 );
```

Der vorhergehende Funktionsaufruf erstellt die folgenden Sätze:

|Legen Sie 1 fest: Möglichen Funktionen, deren erste Argument vom Typ **Int**|Legen Sie 2: Kandidat Funktionen, deren zweites Argument vom Typ **Int**|
|---------------------------------------------------------------------|----------------------------------------------------------------------|
|Variant 2 (**Int** konvertiert werden kann, um **lange** mithilfe einer standardkonvertierung)|Variant 1 (**Int** konvertiert werden kann, um **lange** mithilfe einer standardkonvertierung)|

Da die Schnittmenge dieser beiden Sätze leer ist, generiert der Compiler eine Fehlermeldung angezeigt.

Für die argumentübereinstimmung wird eine Funktion mit *n* Standardargumente behandelt, als *n*+ 1 unterschiedliche Funktionen, jeweils eine unterschiedliche Anzahl von Argumenten.

Die Ellipse (...) dient als Platzhalter; sie stimmt mit jedem tatsächlichen Argument überein. Dies kann zu vielen mehrdeutigen Gruppen führen, wenn Sie Ihre überladene Funktion legt mit größter Sorgfalt entwerfen nicht.

> [!NOTE]
>  Mehrdeutigkeit von überladenen Funktionen kann nicht bestimmt werden, bis ein Funktionsaufruf gefunden wird. An diesem Punkt werden die Sätze für jedes Argument im Funktionsaufruf erstellt, und Sie können bestimmen, ob eine eindeutige Überladung vorhanden ist. Dies bedeutet, dass Mehrdeutigkeiten im Code vorhanden sein dürfen, bis sie durch einen bestimmten Funktionsaufruf eindeutig deklariert werden.

## <a name="argument-type-differences"></a>Unterschiede bei Argumenttypen

Überladene Funktionen unterscheiden zwischen Argumenttypen, die verschiedene Initialisierer erfordern. Daher gelten ein Argument eines angegebenen Typs und ein Verweis auf diesen Typ für den Zweck des Überladens als identisch. Sie gelten als identisch, weil sie die gleichen Initialisierer erfordern. `max( double, double )` wird beispielsweise identisch mit `max( double &, double & )` betrachtet. Das Deklarieren von zwei solcher Funktionen verursacht einen Fehler.

Aus demselben Grund Funktionsargumente eines Typs geändert, indem **const** oder **flüchtige** nicht anders als der Basistyp für den Zweck des Überladens behandelt.

Allerdings kann die Funktion überladen Mechanismus zwischen verweisen, die von qualifiziert sind unterscheiden **const** und **flüchtige** und Verweise auf den Basistyp. Es ist Code wie den folgenden:

```cpp
// argument_type_differences.cpp
// compile with: /EHsc /W3
// C4521 expected
#include <iostream>

using namespace std;
class Over {
public:
   Over() { cout << "Over default constructor\n"; }
   Over( Over &o ) { cout << "Over&\n"; }
   Over( const Over &co ) { cout << "const Over&\n"; }
   Over( volatile Over &vo ) { cout << "volatile Over&\n"; }
};

int main() {
   Over o1;            // Calls default constructor.
   Over o2( o1 );      // Calls Over( Over& ).
   const Over o3;      // Calls default constructor.
   Over o4( o3 );      // Calls Over( const Over& ).
   volatile Over o5;   // Calls default constructor.
   Over o6( o5 );      // Calls Over( volatile Over& ).
}
```

### <a name="output"></a>Output

```Output
Over default constructor
Over&
Over default constructor
const Over&
Over default constructor
volatile Over&
```

Zeiger auf **const** und **flüchtige** -Objekte gelten auch als sich von Zeigern auf den Basistyp für den Zweck des Überladens.

## <a name="argument-matching-and-conversions"></a>Argumentübereinstimmung und Konvertierungen

Wenn der Compiler versucht, die tatsächlichen Argumente mit den Argumenten in Funktionsdeklarationen abzugleichen, kann er Standardkonvertierungen oder benutzerdefinierte Konvertierungen bereitstellen, um den korrekten Typ zu erhalten, wenn keine genaue Übereinstimmung gefunden wird. Die Anwendung von Konvertierungen unterliegt diesen Regeln:

- Sequenzen von Konvertierungen, die mehr als eine benutzerdefinierte Konvertierung enthalten, werden nicht berücksichtigt.

- Sequenzen von Konvertierungen, die gekürzt werden können, indem Konvertierungen im Zwischenformat entfernt werden, werden nicht berücksichtigt.

Das Ergebnis der Konvertierungssequenz, falls vorhanden, ist die am besten passende Sequenz. Es gibt mehrere Möglichkeiten, um ein Objekt vom Typ konvertieren **Int** eingeben **unsigned long** mithilfe von standardkonvertierungen (beschrieben [Standardkonvertierungen](../cpp/standard-conversions.md)):

- Konvertieren von **Int** zu **lange** und klicken Sie dann **lange** zu **unsigned long**.

- Konvertieren von **Int** zu **unsigned long**.

Die erste Sequenz, obwohl sie das erwünschte Ziel erreicht, ist nicht die am besten passende Sequenz – eine kürzere Sequenz.

Die folgende Tabelle zeigt eine Gruppe von Konvertierungen, die als triviale Konvertierungen bezeichnet werden, die eine begrenzte Auswirkung auf die Bestimmung haben, welche Sequenz die größte Übereinstimmung hat. Die Instanzen, in denen triviale Konvertierungen sich auf die Sequenzwahl auswirken, werden in der Liste nach der Tabelle behandelt.

### <a name="trivial-conversions"></a>Triviale Konvertierungen

|Konvertieren von Typ|Konvertiert in Typ|
|-----------------------|---------------------|
|*type-name*|*type-name* **&**|
|*type-name* **&**|*type-name*|
|*Typname* **]**|*type-name* __\*__|
|*type-name* **(** *argument-list* **)**|**(** __\*__ *Typname* **) (** *Argumentliste* **)**|
|*type-name*|**const** *type-name*|
|*type-name*|**volatile** *type-name*|
|*type-name* __\*__|**const** *type-name* __\*__|
|*type-name* __\*__|**volatile** *type-name* __\*__|

Die Reihenfolge für Konvertierungen lautet wie folgt:

1. Genaue Übereinstimmung. Ein genaue Übereinstimmung zwischen den Typen, mit denen die Funktion aufgerufen wird und den Typen, die im Funktionsprototyp deklariert werden, ist immer die beste Übereinstimmung. Sequenzen von trivialen Konvertierungen werden als exakte Übereinstimmungen klassifiziert. Allerdings sind Sequenzen, die jede dieser Konvertierungen stellen nicht besser als Sequenzen berücksichtigt, die konvertiert:

   - Von Zeiger in Zeiger auf **const** (`type` <strong>\*</strong> zu **const** `type` <strong>\*</strong> ).

   - Von Zeiger in Zeiger auf **flüchtige** (`type` <strong>\*</strong> zu **flüchtige** `type` <strong>\*</strong>).

   - Von Verweis in Verweis auf **const** (`type` **&** zu **const** `type` **&**).

   - Von Verweis in Verweis auf **flüchtige** (`type` **&** zu **flüchtige** `type` **&**).

1. Übereinstimmung mithilfe von Erweiterungen. Eine beliebige Sequenz, die nicht als genaue Übereinstimmung, die nur ganzzahlige Erweiterungen, Konvertierungen von enthält klassifiziert **"float"** zu **doppelte**, und triviale Konvertierungen wird als Übereinstimmung mithilfe von Erweiterungen klassifiziert. Obwohl eine Übereinstimmung mit Erweiterungen besser ist als eine Übereinstimmung, die Standardkonvertierungen verwendet, ist sie nicht so gut wie eine genaue Übereinstimmung.

1. Übereinstimmung mithilfe von Standardkonvertierungen. Jede beliebige Sequenz, die nicht als genaue Übereinstimmung klassifiziert wird, oder eine Übereinstimmung mithilfe von Erweiterungen, die nur Standardkonvertierungen und triviale Konvertierungen enthält, wird als Übereinstimmung mithilfe von Standardkonvertierungen klassifiziert. In dieser Kategorie gelten die folgenden Regeln:

   - Konvertierung von einem Zeiger auf eine abgeleitete Klasse, in einen Zeiger auf eine direkte oder indirekte Basisklasse empfiehlt sich, die zum Konvertieren von `void *` oder `const void *`.

   - Die Konvertierung von einem Zeiger auf eine abgeleitete Klasse in einen Zeiger auf eine Basisklasse erzeugt eine bessere Übereinstimmung, je näher die Basisklasse der direkten Basisklasse ist. Angenommen, die Klassenhierarchie folgt der in der folgenden Abbildung dargestellten Klassenhierarchie.

![Diagramm der bevorzugte Konvertierungen](../cpp/media/vc391t1.gif "Diagramm der bevorzugte Konvertierungen") <br/>
Diagramm mit bevorzugten Konvertierungen

Die Konvertierung von Typ `D*` in Typ `C*` ist der Konvertierung von Typ `D*` in Typ `B*` vorzuziehen. Entsprechend ist die Konvertierung von Typ `D*` in Typ `B*` der Konvertierung von Typ `D*` in Typ `A*` vorzuziehen.

Die gleiche Regel gilt für Verweiskonvertierungen. Die Konvertierung von Typ `D&` in Typ `C&` ist der Konvertierung von Typ `D&` in Typ `B&` usw. vorzuziehen.

Die gleiche Regel gilt für pointer-to-member-Konvertierungen. Die Konvertierung von Typ `T D::*` in Typ `T C::*` ist der Konvertierung von Typ `T D::*` in Typ `T B::*` und so weiter vorzuziehen (wobei `T` der Typ des Members ist).

Die vorhergehende Regel gilt nur für einen bestimmten Ableitungspfad. Betrachten Sie das Diagramm, das in der folgenden Abbildung dargestellt wird.

![Mehrere&#45;Vererbung, die bevorzugten Konvertierungen](../cpp/media/vc391t2.gif "mehrere&#45;Vererbung, die bevorzugten Konvertierungen") <br/>
Mehrfachvererbungsdiagramm zur Verfügung, die bevorzugten Konvertierungen

Die Konvertierung von Typ `C*` in Typ `B*` ist der Konvertierung von Typ `C*` in Typ `A*` vorzuziehen. Der Grund liegt darin, dass sie sich auf dem gleichen Pfad befinden, und `B*` näher liegt. Allerdings Konvertierung von Typ `C*` eingeben `D*` ist besser als die Konvertierung in den Typ nicht `A*`; keine Einstellung vorhanden ist, da die Konvertierungen verschiedenen Pfaden folgen.

1. Übereinstimmung mit benutzerdefinierten Konvertierungen. Diese Sequenz kann nicht als eine genaue Übereinstimmung, Übereinstimmung mithilfe von Erweiterungen oder als Übereinstimmung mithilfe von standardkonvertierungen klassifiziert werden. Die Reihenfolge darf nur benutzerdefinierte Konvertierungen, Standardkonvertierungen oder triviale Konvertierungen enthalten, um die Übereinstimmung mit benutzerdefinierten Konvertierungen zu erreichen. Eine Übereinstimmung mit benutzerdefinierten Konvertierungen gilt als eine bessere Übereinstimmung als eine Übereinstimmung mit einem Auslassungszeichen, jedoch als nicht so gut wie eine Übereinstimmung mit Standardkonvertierungen.

1. Übereinstimmung mit einem Auslassungszeichen. Jede beliebige Sequenz, die Auslassungszeichen in der Deklaration entspricht, wird als Übereinstimmung mit einem Auslassungszeichen klassifiziert. Es ist die schwächste Übereinstimmung angesehen.

Benutzerdefinierte Konvertierungen werden angewendet, wenn keine integrierte Erweiterung oder Konvertierung vorhanden ist. Diese Konvertierungen werden auf der Grundlage des Typs des Arguments ausgewählt, das abgeglichen wird. Betrachten Sie folgenden Code:

```cpp
// argument_matching1.cpp
class UDC
{
public:
   operator int()
   {
      return 0;
   }
   operator long();
};

void Print( int i )
{
};

UDC udc;

int main()
{
   Print( udc );
}
```

Die verfügbaren benutzerdefinierten Konvertierungen für die Klasse `UDC` sind vom Typ **Int** und **lange**. Deshalb berücksichtigt der Compiler Konvertierungen für den Typ des Objekts, das abgeglichen wird: `UDC`. Eine Konvertierung in **Int** vorhanden ist, und diese Option ausgewählt ist.

Während des Prozesseses zum Zuordnen von Argumenten können Standardkonvertierungen sowohl auf das Argument als auch auf das Ergebnis einer benutzerdefinierten Konvertierung angewendet werden. Daher funktioniert der folgende Code:

```cpp
void LogToFile( long l );
...
UDC udc;
LogToFile( udc );
```

Im vorherigen Beispiel, die eine benutzerdefinierte Konvertierung **Operator long**, wird aufgerufen, um die Konvertierung `udc` eingeben **lange**. Wenn keine benutzerdefinierte Konvertierung in den Typ **lange** war definiert, die Konvertierung würde wie folgt fortgesetzt: Typ `UDC` würde wurden so konvertiert, geben Sie **Int** mit der eine benutzerdefinierte Konvertierungsfunktion. Klicken Sie dann die standardkonvertierung vom Typ **Int** eingeben **lange** würde angewendet wurde, um das Argument in der Deklaration übereinstimmen.

Wenn eine benutzerdefinierte Konvertierung erforderlich sind, Übereinstimmung mit einem Argument, werden nicht die standardkonvertierungen verwendet, wenn der besten Übereinstimmung. Auch wenn mehr als eine kandidatenfunktion eine benutzerdefinierte Konvertierung erfordert, werden die Funktionen als gleich betrachtet. Zum Beispiel:

```cpp
// argument_matching2.cpp
// C2668 expected
class UDC1
{
public:
   UDC1( int );  // User-defined conversion from int.
};

class UDC2
{
public:
   UDC2( long ); // User-defined conversion from long.
};

void Func( UDC1 );
void Func( UDC2 );

int main()
{
   Func( 1 );
}
```

Beide Versionen der `Func` erfordern eine benutzerdefinierte Konvertierung Typen konvertiert **Int** dem Typargument der Klasse. Mögliche Konversionen sind:

- Konvertieren vom Typ **Int** eingeben `UDC1` (benutzerdefinierte Konversion).

- Konvertieren vom Typ **Int** eingeben **lange**; anschließende Konvertierung in den Typ `UDC2` (zweistufige-Konvertierung).

Auch wenn das zweite Argument eine standardkonvertierung, und die benutzerdefinierte Konvertierung erfordert, sind die zwei Konvertierungen noch immer als gleich.

> [!NOTE]
>  Benutzerdefinierte Konvertierungen gelten als Konvertierung durch Konstruktion oder als Konvertierung durch Initialisierung (Konvertierungsfunktion). Beide Methoden werden als gleich betrachtet, wenn die beste Übereinstimmung berücksichtigt wird.

## <a name="argument-matching-and-the-this-pointer"></a>Argumentübereinstimmung und der this-Zeiger

Klassenmemberfunktionen werden unterschiedlich behandelt, je nachdem, ob sie, als deklariert werden **statische**. Da nicht statische Funktionen über ein implizites Argument verfügen, die bereitstellt der **dies** -Zeiger ist, nicht statische Funktionen als mit einem weiterem Argument als statische Funktionen haben; andernfalls werden sie genauso deklariert.

Diese nicht statischen Memberfunktionen erfordern, dass der implizite **dies** Zeiger überein, die den Objekttyp, der über die die Funktion aufgerufen wird, oder für überladene Operatoren, sie erfordern, dass das erste Argument das Objekt, für das übereinstimmen der Operator wird angewendet. (Weitere Informationen zu überladenen Operatoren finden Sie unter [überladene Operatoren](../cpp/operator-overloading.md).)

Im Gegensatz zu anderen Argumenten in überladenen Funktionen, werden keine temporären Objekte eingeführt und keine Konvertierungen angestrebt, wenn versucht wird, entsprechend der **dies** -Zeigerargument übereinzustimmen.

Wenn die `->` Objektmember-auswahloperators greift auf eine Memberfunktion der Klasse `class_name`, **dies** -Zeigerargument eine Art von `class_name * const`. Wenn die Member, als deklariert werden **const** oder **flüchtige**, die Typen sind `const class_name * const` und `volatile class_name * const`bzw.

Der Memberauswahloperator `.` funktioniert genau auf die gleiche Weise, außer dass ein impliziter `&`-Operator (address-of) dem Objektnamen vorangestellt ist. Im folgenden Beispiel wird gezeigt, wie dies funktioniert:

```cpp
// Expression encountered in code
obj.name

// How the compiler treats it
(&obj)->name
```

Der linke Operand der Operatoren `->*` und `.*` (Zeiger auf Member) wird hinsichtlich der Argumentübereinstimmung genauso wie der `.`-Operator und der `->`-Operator (Memberauswahl) behandelt.

## <a name="ref-qualifiers"></a> REF-Qualifizierer für Memberfunktionen

REF-Qualifizierer können sie eine Memberfunktion gibt an, ob das Objekt, zeigt auf der Grundlage überladen **dies** ist ein Rvalue-Wert oder einen l-Wert.  Dieses Feature kann verwendet werden, zu vermeiden unnötiger Kopiervorgänge in Szenarien, in denen Sie wählen nicht Zeiger auf die Daten zugegriffen. Nehmen wir beispielsweise an die Klasse `C` einige Daten in seinem Konstruktor initialisiert und gibt eine Kopie der Daten in Memberfunktion `get_data()`. Wenn ein Objekt des Typs `C` ist ein Rvalue-Wert, der gelöscht werden soll, der Compiler wählen, wird die `get_data() &&` überladen, wodurch die Daten verschoben werden, anstatt Sie zu kopieren.

```cpp
#include <iostream>
#include <vector>

using namespace std;

class C
{

public:
    C() {/*expensive initialization*/}
    vector<unsigned> get_data() &
    {
        cout << "lvalue\n";
        return _data;
    }
    vector<unsigned> get_data() &&
    {
        cout << "rvalue\n";
        return std::move(_data);
    }

private:
    vector<unsigned> _data;
};

int main()
{
    C c;
    auto v = c.get_data(); // get a copy. prints "lvalue".
    auto v2 = C().get_data(); // get the original. prints "rvalue"
    return 0;
}
```

## <a name="restrictions-on-overloading"></a>Einschränkungen beim Überladen

Mehrere Einschränkungen steuern eine akzeptable Gruppe von überladenen Funktionen:

- Zwei beliebige Funktionen in einer Gruppe von überladenen Funktionen müssen unterschiedliche Argumentlisten haben.

- Das Überladen von Funktionen mit Argumentlisten der gleichen Typen auf alleiniger Grundlage des Rückgabetyps ist ein Fehler.

     **Microsoft-spezifisch**

Sie können überladen **new-Operator** ausschließlich auf Grundlage der Rückgabetyp – insbesondere auf der Grundlage der angegebenen Modifizierers.

**Ende Microsoft-spezifisch**

- Memberfunktionen können nicht allein auf der Grundlage eine statisch und die andere nicht statisch überladen werden.

- **TypeDef** -Deklarationen definieren keine neue Typen; sie führen Synonyme für vorhandene Typen. Der Mechanismus zum Überladen davon nicht betroffen. Betrachten Sie folgenden Code:

    ```cpp
    typedef char * PSTR;

    void Print( char *szToPrint );
    void Print( PSTR szToPrint );
    ```

   Die vorhergehenden zwei Funktionen verfügen über identische Argumentlisten. `PSTR` ist ein Synonym für den Typ `char *`. Im Memberbereich generiert dieser Code einen Fehler.

- Aufgelistete Typen sind verschiedene Typen und können verwendet werden, um zwischen überladenen Funktionen zu unterscheiden.

- Die Typen "Array von" und "Zeiger auf" gelten als identisch zum Zweck der unterscheiden zwischen überladenen Funktionen, jedoch nur für einzeln Arrays dimensioniert. Daher diese überladenen Funktionen in Konflikt stehen, und eine Fehlermeldung generiert:

    ```cpp
    void Print( char *szToPrint );
    void Print( char szToPrint[] );
    ```

   Für mehrdimensionale Arrays gelten die zweite und alle nachfolgenden Dimensionen als Teil des Typs. Deshalb werden sie beim Unterscheiden zwischen überladenen Funktionen verwendet:

    ```cpp
    void Print( char szToPrint[] );
    void Print( char szToPrint[][7] );
    void Print( char szToPrint[][9][42] );
    ```

## <a name="overloading-overriding-and-hiding"></a>Überladen, überschreiben und ausblenden

Zwei beliebige Funktionsdeklarationen des gleichen Namens im gleichen Bereich können auf die gleiche Funktion oder zwei einzelne Funktionen, die überladen werden, verweisen. Wenn die Argumentlisten der Deklarationen Argumente äquivalenter Typen enthalten (wie im vorherigen Abschnitt beschrieben), beziehen sich die Funktionsdeklarationen auf die gleiche Funktion. Andernfalls beziehen sie sich auf zwei separate Funktionen, die mithilfe des Überladens ausgewählt werden.

Klassenbereich wird strikt beachtet; aus diesem Grund befindet sich eine Funktion, die in einer Basisklasse deklariert nicht im gleichen Bereich wie eine Funktion, die in einer abgeleiteten Klasse deklariert. Wenn eine Funktion in einer abgeleiteten Klasse, mit dem gleichen Namen wie eine virtuelle Funktion in der Basisklasse, die abgeleitete Klassenfunktion deklariert wird *überschreibt* die Funktion der Basisklasse. Weitere Informationen finden Sie unter [virtuelle Funktionen](../cpp/virtual-functions.md).

Wenn die Funktion der Basisklasse ist nicht als "virtual" deklariert, und klicken Sie dann die Funktion der abgeleiteten Klasse gilt als *ausblenden* es. Sowohl überschreiben und Ausblenden von unterscheiden sich von überladen.

Blockbereich wird strikt beachtet; aus diesem Grund befindet sich eine Funktion, die im Dateibereich deklariert nicht im gleichen Bereich wie eine Funktion lokal deklariert werden. Wenn eine lokal deklarierte Funktion den gleichen Namen wie eine Funktion besitzt, die im Dateibereich deklariert wird, blendet die lokal deklarierte Funktion die Funktion im Dateibereich aus, und es erfolgt keine Überladung. Zum Beispiel:

```cpp
// declaration_matching1.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
void func( int i )
{
    cout << "Called file-scoped func : " << i << endl;
}

void func( char *sz )
{
   cout << "Called locally declared func : " << sz << endl;
}

int main()
{
   // Declare func local to main.
   extern void func( char *sz );

   func( 3 );   // C2664 Error. func( int ) is hidden.
   func( "s" );
}
```

Der vorhergehende Code zeigt zwei Definitionen der Funktion `func`. Die Definition, die ein des Typs Argument `char *` lediglich auf `main` aufgrund der **"extern"** Anweisung. Daher wird die Definition, die ein Argument des Typs akzeptiert **Int** ausgeblendet, und der erste Aufruf von `func` ist fehlerhaft.

Für überladene Memberfunktionen können verschiedenen Versionen der Funktion unterschiedliche Zugriffsrechte zugewiesen werden. Sie werden weiterhin als im Gültigkeitsbereich der einschließenden Klasse betrachtet und sind somit überladene Funktionen. Betrachten Sie den folgenden Code, in dem die Memberfunktion `Deposit` überladen wird. Eine Version ist öffentlich, die andere privat.

Der Zweck dieses Beispiels ist es, eine `Account`-Klasse bereitzustellen, in der ein korrektes Kennwort erforderlich ist, um Eingaben vorzunehmen. Dies erfolgt mithilfe der Überladung.

Der Aufruf von `Deposit` in `Account::Deposit` die Private Memberfunktion aufruft. Dieser Aufruf ist korrekt da `Account::Deposit` ist eine Memberfunktion und Zugriff auf die privaten Member der Klasse.

```cpp
// declaration_matching2.cpp
class Account
{
public:
   Account()
   {
   }
   double Deposit( double dAmount, char *szPassword );

private:
   double Deposit( double dAmount )
   {
      return 0.0;
   }
   int Validate( char *szPassword )
   {
      return 0;
   }

};

int main()
{
    // Allocate a new object of type Account.
    Account *pAcct = new Account;

    // Deposit $57.22. Error: calls a private function.
    // pAcct->Deposit( 57.22 );

    // Deposit $57.22 and supply a password. OK: calls a
    //  public function.
    pAcct->Deposit( 52.77, "pswd" );
}

double Account::Deposit( double dAmount, char *szPassword )
{
   if ( Validate( szPassword ) )
      return Deposit( dAmount );
   else
      return 0.0;
}
```

## <a name="see-also"></a>Siehe auch

[Funktionen (C++)](../cpp/functions-cpp.md)