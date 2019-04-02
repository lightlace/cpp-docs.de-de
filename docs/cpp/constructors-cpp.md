---
title: Konstruktoren (C++)
ms.date: 04/06/2018
helpviewer_keywords:
- constructors [C++]
- objects [C++], creating
- instance constructors
ms.assetid: 3e9f7211-313a-4a92-9584-337452e061a9
ms.openlocfilehash: cad88af9e81a60857fbbd6c90cf81cdcafbd7a12
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781470"
---
# <a name="constructors-c"></a>Konstruktoren (C++)

Zum Anpassen, wie die Klasse, Elemente initialisiert werden, oder zum Aufrufen von Funktionen, wenn ein Objekt der Klasse erstellt wird, definieren eine *Konstruktor*. Ein Konstruktor hat den gleichen Namen wie die Klasse und weist keinen Rückgabewert auf. Sie können beliebig viele überladene Konstruktoren, die nach Bedarf, um die Initialisierung auf verschiedene Weise anzupassen definieren. Konstruktoren ist in der Regel öffentliche zugreifbarkeit besitzen, sodass Code außerhalb der Klassenhierarchie Definition oder Vererbung Objekte der Klasse erstellen kann. Aber Sie können auch einen Konstruktor als deklarieren **geschützt** oder **private**.

Konstruktoren können optional ein Element Init Liste übernehmen. Dies ist eine effizientere Methode zum Initialisieren von Klassenmembern als Zuweisen von Werten in den Text des Konstruktors. Das folgende Beispiel zeigt eine Klasse `Box` mit drei überladene Konstruktoren. Verwenden Sie die letzten zwei Init Memberlisten:

```cpp
class Box {
public:
    // Default constructor
    Box() {}

    // Initialize a Box with equal dimensions (i.e. a cube)
    explicit Box(int i) : m_width(i), m_length(i), m_height(i) // member init list
    {}

    // Initialize a Box with custom dimensions
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}

    int Volume() { return m_width * m_length * m_height; }

private:
    // Will have value of 0 when default constructor is called.
    // If we didn't zero-init here, default constructor would
    // leave them uninitialized with garbage values.
    int m_width{ 0 };
    int m_length{ 0 };
    int m_height{ 0 };
};
```

Wenn Sie eine Instanz einer Klasse deklarieren, wählt der Compiler an, welcher Konstruktor aufrufen abhängig von den Regeln der überladungsauflösung:

```cpp
int main()
{
    Box b; // Calls Box()

    // Using uniform initialization (preferred):
    Box b2 {5}; // Calls Box(int)
    Box b3 {5, 8, 12}; // Calls Box(int, int, int)

    // Using function-style notation:
    Box b4(2, 4, 6); // Calls Box(int, int, int)
}
```

- Konstruktoren können deklariert werden, als **Inline**, [explizite](#explicit_constructors), **Friend** oder ["constexpr"](#constexpr_constructors).
- Ein Konstruktor kann ein Objekt, das als deklariert wurde initialisiert **const**, **flüchtige** oder **const Volatile**. Das Objekt nicht mehr **const** nach dem Abschluss des Konstruktors.
- Um einen Konstruktor in einer Implementierungsdatei zu definieren, geben sie einen vollqualifizierten Namen wie bei anderen Member-Funktion: `Box::Box(){...}`.

## <a name="member_init_list"></a> Memberlisten-Initialisierer

Ein Konstruktor kann optional eine Member-Initialisiererliste werden, die Klassenmember vor der Ausführung von den Text des Konstruktors initialisiert. (Beachten Sie, dass eine Memberinitialisiererliste nicht dasselbe wie ein *Initialisiererliste* des Typs [Std:: initializer_list\<T >](../standard-library/initializer-list-class.md).)

Verwendung einer Memberinitialisiererliste wird bevorzugt über Werte im Text des Konstruktors zugewiesen, da er direkt auf das Element initialisiert. Im folgenden Beispiel wird der Memberinitialisierer Liste enthält alle der **identifier(argument)** Ausdrücke nach dem Doppelpunkt:

```cpp
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}
```

Der Bezeichner muss auf einen Klassenmember beziehen. Es wird mit dem Wert des Arguments initialisiert. Das Argument kann eine der Parameter des Konstruktors, eines Funktionsaufrufs oder [Std:: initializer_list\<T >](../standard-library/initializer-list-class.md).

**const** Mitglieder sowie Mitglieder der Verweistyp müssen in der Member-Initialisiererliste initialisiert werden.

Parametrisierte Konstruktoren Aufrufe sollten in der Initialisiererliste vorgenommen werden, um sicherzustellen, dass die Basisklasse vor der Ausführung von den abgeleiteten Konstruktor vollständig initialisiert wurde.

## <a name="default_constructors"></a> Standardkonstruktoren

*Standardkonstruktoren* in der Regel keine Parameter, aber sie können Parameter mit Standardwerten.

```cpp
class Box {
public:
    Box() { /*perform any required default initialization steps*/}

    // All params have default values
    Box (int w = 1, int l = 1, int h = 1): m_width(w), m_height(h), m_length(l){}
...
}
```

Standardkonstruktoren zählen zu der die [spezielle Memberfunktionen](special-member-functions.md). Wenn keine Konstruktoren in einer Klasse deklariert sind, stellt der Compiler einen impliziten **Inline** Standardkonstruktor.

```cpp
#include <iostream>
using namespace std;

class Box {
public:
    int Volume() {return m_width * m_height * m_length;}
private:
    int m_width { 0 };
    int m_height { 0 };
    int m_length { 0 };
};

int main() {
    Box box1; // Invoke compiler-generated constructor
    cout << "box1.Volume: " << box1.Volume() << endl; // Outputs 0
}
```

Wenn Sie einen impliziten Standardkonstruktor verwenden, müssen Sie Elemente in der Klassendefinition initialisiert werden, wie im vorherigen Beispiel gezeigt. Ohne diese Initialisierer Elemente werden nicht initialisiert werden, und der Aufruf Volume() ergibt einen Wert für die Garbage. Im Allgemeinen ist es empfehlenswert, die zum Initialisieren von Membern, die auf diese Weise, auch wenn nicht auf einen impliziten Standardkonstruktor verlassen.

Sie können verhindern, dass den Compiler generiert einen impliziten Standardkonstruktor definieren ihn als [gelöscht](#explicitly_defaulted_and_deleted_constructors):

```cpp
    // Default constructor
    Box() = delete;
```

Ein vom Compiler generierten Standardkonstruktor wird als gelöscht, wenn alle Klassenmember nicht standardmäßig konstruierbar sind definiert. Beispielsweise müssen alle Member des Klassentyps und deren Member Klassentyp haben, einen Standardkonstruktor und -Destruktoren führen, die zugegriffen werden kann. Geben Sie alle Datenmember des Verweistyps, auch als **const** Member müssen ein standardmemberinitialisierer aufweisen.

Wenn Sie einen vom Compiler generierten Standardkonstruktor aufrufen und versuchen, mithilfe von Klammern, wird eine Warnung ausgegeben:

```cpp
class myclass{};
int main(){
myclass mc();     // warning C4930: prototyped function not called (was a variable definition intended?)
}
```

Dies ist ein Beispiel für das "Most Vexing Parse"-Problem. Da der Beispielsausdruck entweder als Deklaration einer Funktion oder als Aufruf eines Standardkonstruktors interpretiert werden kann, und da C++-Parser Deklarationen bevorzugen, wird der Ausdruck als Funktionsdeklaration behandelt. Weitere Informationen finden Sie unter [Most Vexing Parse](http://en.wikipedia.org/wiki/Most_vexing_parse).

Wenn nicht standardmäßige Konstruktoren deklariert werden, stellt der Compiler keinen Standardkonstruktor bereit:

```cpp
class Box {
public:
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height){}
private:
    int m_width;
    int m_length;
    int m_height;

};

int main(){

    Box box1(1, 2, 3);
    Box box2{ 2, 3, 4 };
    Box box3; // C2512: no appropriate default constructor available
}
```

Wenn eine Klasse keinen Standardkonstruktor hat, kann ein Array von Objekten dieser Klasse nicht allein mithilfe von Syntax in eckigen Klammern erstellt werden. Beispielsweise kann im vorherigen Codeblock ein Array von Feldern nicht folgendermaßen deklariert werden:

```cpp
Box boxes[3]; // C2512: no appropriate default constructor available
```

Allerdings können Sie einen Satz von Initialisiererlisten verwenden, um ein Array von Objekten von Feld zu initialisieren:

```cpp
Box boxes[3]{ { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };
```

Weitere Informationen finden Sie unter [Initialisierer](initializers.md).

## <a name="copy_and_move_constructors"></a> Kopierkonstruktoren

Ein *Kopierkonstruktor* Initialisiert ein Objekt durch die Werte aus einem Objekt des gleichen Typs kopieren. Wenn Ihre Klasse, Elemente alle einfache Typen wie Skalare Werte sind, der vom Compiler generierte Kopierkonstruktor ist ausreichend, und Sie müssen nicht definieren Ihre eigenen. Wenn Ihre Klasse komplexere Initialisierung erfordert, müssen Sie zum Implementieren eines benutzerdefinierten Kopierkonstruktors. Z. B. wenn ein Klassenmember ein Zeiger ist müssen Sie definieren einen Kopierkonstruktor zum neuen Speicher zuordnen, und kopieren Sie die Werte aus der anderen Person auf Objekt. Der vom Compiler generierte Kopierkonstruktor kopiert einfach den Zeiger, damit der neue Zeiger immer noch auf den anderen Speicherort verweist.

Ein Kopierkonstruktor möglicherweise eine der folgenden Signaturen:

```cpp
    Box(Box& other); // Avoid if possible--allows modification of other.
    Box(const Box& other);
    Box(volatile Box& other);
    Box(volatile const Box& other);

    // Additional parameters OK if they have default values
    Box(Box& other, int i = 42, string label = "Box");
```

Wenn Sie einen Kopierkonstruktor definieren, sollten Sie auch einen Kopie-Zuweisungsoperator (=) definieren. Weitere Informationen finden Sie unter [Zuweisung](assignment.md) und [Kopierkonstruktoren und Kopierzuweisungsoperatoren](copy-constructors-and-copy-assignment-operators-cpp.md).

Sie können verhindern, dass das Objekt kopiert wird, durch die Definition des Kopierkonstruktor gelöscht:

```cpp
    Box (const Box& other) = delete;
```

Versuch, das Objekt zu kopieren, wird Fehler *C2280: Es wird versucht, eine gelöschte Funktion zu verweisen*.

## <a name="move_constructors"></a> Move-Konstruktoren

Ein *bewegungskonstruktor* ist eine spezielle Memberfunktion, die Besitz der Daten in einem vorhandenen Objekt einer neuen Variable verschiebt, ohne die ursprünglichen Daten kopiert. Es akzeptiert einen Rvalue-Verweis als ersten Parameter, und alle zusätzlichen Parameter müssen Standardwerte. Move-Konstruktoren können erheblich Ihres Programms Effizienz erhöhen, wenn große Objekte übergeben. Verschieben-Konstruktor akzeptiert einen Rvalue-Verweis als ersten Parameter. Alle anderen Parameter müssen Standardwerte besitzen.

```cpp
Box(Box&& other);
```

Der Compiler wählt ein bewegungskonstruktor in bestimmten Situationen, in dem das Objekt von einem anderen Objekt desselben Typs initialisiert wird, die zerstört werden soll, und es nicht mehr benötigt, Ressourcen. Das folgende Beispiel zeigt einen Fall, wenn ein bewegungskonstruktor vom Auflösung von funktionsüberladungen ausgewählt wird. Die Variable *Feld* get_Box() zurückgegebenes wird einer *Xvalue* (ablaufenden Wert) der wird außerhalb des gültigen Bereichs. Um die Motivation für dieses Beispiel zu ermöglichen, geben wir Feld einen großen Vektor von Zeichenfolgen, die dessen Inhalt darstellen. Anstatt Kopieren der Vektor und die Zeichenfolgen stiehlt"der bewegungskonstruktor" es vom ablaufenden Wert "Box", damit der Vektor jetzt auf das neue Objekt gehört. Der Aufruf von `std::move` ist alles, was erforderlich ist, da beide `vector` und `string` Klassen implementieren ihre eigenen Move-Konstruktoren.

```cpp
#include <iostream>
#include <vector>
#include <string>
#include <algorithm>
using namespace std;

class Box {
public:
    Box() { std::cout << "default" << std::endl; }
    Box(int width, int height, int length)
       : m_width(width), m_height(height), m_length(length)
    {
        std::cout << "int,int,int" << std::endl;
    }
    Box(Box& other)
       : m_width(other.m_width), m_height(other.m_height), m_length(other.m_length)
    {
        std::cout << "copy" << std::endl;
    }
    Box(Box&& other) : m_width(other.m_width), m_height(other.m_height), m_length(other.m_length)
    {
        m_contents = std::move(other.m_contents);
        std::cout << "move" << std::endl;
    }
    int Volume() { return m_width * m_height * m_length; }
    void Add_Item(string item) { m_contents.push_back(item); }
    void Get_Contents()
    {
        for (const auto& item : m_contents)
        {
            cout << item << " ";
        }
    }
private:
    int m_width{ 0 };
    int m_height{ 0 };
    int m_length{ 0 };
    vector<string> m_contents;
};

Box get_Box()
{
    Box b(5, 10, 18); // "int,int,int"
    b.Add_Item("Toupee");
    b.Add_Item("Megaphone");
    b.Add_Item("Suit");

    return b;
}

int main()
{
    Box b; // "default"
    Box b1(b); // "copy"
    Box b2(get_Box()); // "move"
    cout << "b2 contents: ";
    b2.Get_Contents(); // Prove that we have all the values

    char ch;
    cin >> ch; // keep window open
    return 0;
}
```

Wenn eine Klasse, die nicht über einen bewegungskonstruktor definiert, generiert der Compiler eine implizite, liegt keine benutzerdeklarierten Kopierkonstruktor, Kopierzuweisungsoperator, bewegungszuweisungsoperator oder Destruktor. Wenn keine explizite oder implizite bewegungskonstruktor definiert ist, verwenden Sie stattdessen Vorgänge, die andernfalls einen bewegungskonstruktor verwenden würde den Copy-Konstruktor. Wenn ein bewegungskonstruktor oder bewegungszuweisungsoperator eine Klasse deklariert wird, wird der implizit deklarierten Kopierkonstruktor als gelöscht definiert.

Ein implizit deklarierte Verschiebungskonstruktor definiert ist, als gelöscht, wenn alle Elemente, die Klassentypen sind nicht über einen Destruktor oder der Compiler nicht, welcher Konstruktor feststellen kann, der für den Vorgang verwendet.

Weitere Informationen, wie Sie einen nicht trivialen bewegungskonstruktor schreiben können, finden Sie unter [Bewegungskonstruktoren und Bewegungszuweisungsoperatoren (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md).

## <a name="explicitly_defaulted_and_deleted_constructors"></a> Explizit vorgegebene und gelöschte Konstruktoren

Sie können explizit *Standard* Kopierkonstruktoren, Standardkonstruktoren, bewegungskonstruktoren, Kopierzuweisungsoperatoren, bewegungszuweisungsoperatoren und Destruktoren zu verschieben. Sie können explizit *löschen* alle speziellen Memberfunktionen.

```cpp
class Box
{
public:
    Box2() = delete;
    Box2(const Box2& other) = default;
    Box2& operator=(const Box2& other) = default;
    Box2(Box2&& other) = default;
    Box2& operator=(Box2&& other) = default;
    //...
};
```

Weitere Informationen finden Sie unter [explizit vorgegebene und gelöschte Funktionen](../cpp/explicitly-defaulted-and-deleted-functions.md).

## <a name="constexpr_constructors"></a> Constexpr-Konstruktoren

Ein Konstruktor kann deklariert werden, als ["constexpr"](constexpr-cpp.md) Wenn

- Es ist es für alle Bedingungen erfüllt, sonst entweder deklariert werden, wie auf den Standardwert festgelegte [Constexpr-Funktionen](constexpr-cpp.md#constexpr_functions) im Allgemeinen;
- die Klasse verfügt über keine virtuellen Basisklassen;
- Jeder Parameter ist ein [Literaltyp](trivial-standard-layout-and-pod-types.md#literal_types);
- der Text ist kein Try-Block einer Funktion;
- alle nicht statischen Datenmember und untergeordnete Objekte der Klasse initialisiert werden;
- Wenn die Klasse (a) einer Vereinigung mit variant Mitglieder oder (b) verfügt über anonyme Unions, wird nur einer der union-Member initialisiert;
- alle nicht statischen Datenmember des Klassentyps und alle untergeordneten Objekte von Basisklasse vorhanden Constexpr-Konstruktor.

## <a name="init_list_constructors"></a> Initialisierer Liste Konstruktoren

Wenn ein Konstruktor akzeptiert ein [Std:: initializer_list\<T\> ](../standard-library/initializer-list-class.md) als Parameter, und alle anderen Parameter Standardargumente haben, diesen Konstruktor ausgewählt werden, an der überladungsauflösung sobald die Klasse ist durch die direkte Initialisierung instanziiert. Sie können das initializer_list-Element verwenden, um jedes Element zu initialisieren, die sie akzeptieren kann. Nehmen wir beispielsweise an, die Box-Klasse, die (zuvor gezeigt) verfügt über eine `std::vector<string>` Member `m_contents`. Sie können einen Konstruktor wie folgt angeben:

```cpp
    Box(initializer_list<string> list, int w = 0, int h = 0, int l = 0)
        : m_contents(list), m_width(w), m_height(h), m_length(l)
{}
```

Und erstellen Sie im Feld-Objekte, wie diese:

```cpp
    Box b{ "apples", "oranges", "pears" }; // or ...
    Box b2(initializer_list<string> { "bread", "cheese", "wine" }, 2, 4, 6);
```

## <a name="explicit_constructors"></a> Explizite Konstruktoren

Wenn eine Klasse einen Konstruktor mit einem einzelnen Parameter aufweist oder wenn alle Parameter mit Ausnahmen von einem einen Standardwert besitzen, kann der Parametertyp impliziert zum Klassentyp konvertiert werden. Beispielsweise wenn die `Box`-Klasse über einen derartigen Konstruktor verfügt:

```cpp
Box(int size): m_width(size), m_length(size), m_height(size){}
```

Es ist möglich, ein Feld wie folgt zu initialisieren:

```cpp
Box b = 42;
```

Alternativ können Sie eine Ganzzahl an eine Funktion weiterleiten, die ein Feld verwendet:

```cpp
class ShippingOrder
{
public:
    ShippingOrder(Box b, double postage) : m_box(b), m_postage(postage){}

private:
    Box m_box;
    double m_postage;
}
//elsewhere...
    ShippingOrder so(42, 10.8);
```

Derartige Konvertierungen können in einigen Fällen hilfreich sein. Häufiger führen sie jedoch möglicherweise zu feinen, aber schwerwiegenden Fehlern in Ihrem Code. Als allgemeine Regel sollten Sie verwenden die **explizite** das Schlüsselwort für einen Konstruktor (und benutzerdefinierten Operatoren), um diese Art der impliziten typkonvertierung zu verhindern:

```cpp
explicit Box(int size): m_width(size), m_length(size), m_height(size){}
```

Wenn der Konstruktor explizit ist, verursacht diese Zeile einen Compilerfehler: `ShippingOrder so(42, 10.8);`.  Weitere Informationen finden Sie unter [User-Defined Type Conversions](../cpp/user-defined-type-conversions-cpp.md).

## <a name="order_of_construction"></a> Reihenfolge der Konstruktion

Ein Konstruktor führt die Arbeit in folgender Reihenfolge aus:

1. Er ruft Basisklassen- und Memberkonstruktoren in der Reihenfolge der Deklaration auf.

1. Wenn die Klasse von virtuellen Basisklassen abgeleitet wird, initialisiert er die virtuellen Basiszeiger des Objekts.

1. Wenn die Klasse virtuelle Funktionen hat oder erbt, initialisiert er die virtuellen Funktionszeiger des Objekts. Virtuelle Funktionszeiger zeigen auf die virtuelle Funktionstabelle der Klasse, um eine korrekte Bindung von virtuellen Funktionsaufrufen im Code zu ermöglichen.

1. Er führt den Code im Funktionsrumpf aus.

Das folgende Beispiel zeigt die Reihenfolge, in der Basisklassen- und Memberkonstruktoren im Konstruktor für eine abgeleitete Klasse aufgerufen werden. Zuerst wird der Basiskonstruktor aufgerufen. Anschließend werden die Basisklassenmember in der Reihenfolge initialisiert, in der sie in der Klassendeklaration stehen. Danach wird der abgeleitete Konstruktor aufgerufen.

```cpp
#include <iostream>

using namespace std;

class Contained1 {
public:
    Contained1() { cout << "Contained1 ctor\n"; }
};

class Contained2 {
public:
    Contained2() { cout << "Contained2 ctor\n"; }
};

class Contained3 {
public:
    Contained3() { cout << "Contained3 ctor\n"; }
};

class BaseContainer {
public:
    BaseContainer() { cout << "BaseContainer ctor\n"; }
private:
    Contained1 c1;
    Contained2 c2;
};

class DerivedContainer : public BaseContainer {
public:
    DerivedContainer() : BaseContainer() { cout << "DerivedContainer ctor\n"; }
private:
    Contained3 c3;
};

int main() {
    DerivedContainer dc;
}
```

Die Ausgabe ist wiefolgt:

```Output
Contained1 ctor
Contained2 ctor
BaseContainer ctor
Contained3 ctor
DerivedContainer ctor
```

Ein abgeleiteter Klassenkonstruktor ruft immer einen Basisklassenkonstruktor auf, damit er immer auf vollständig erstellte Basisklassen zurückgreifen kann, bevor zusätzliche Arbeit erforderlich ist. Die Basisklassenkonstruktoren werden in Reihenfolge der Ableitung aufgerufen – z. B. wenn `ClassA` ergibt sich aus `ClassB`, ergibt sich aus `ClassC`, wird die `ClassC` Konstruktor zuerst aufgerufen wird, und klicken Sie dann die `ClassB` Konstruktor die `ClassA` Konstruktor.

Wenn eine Basisklasse keinen Standardkonstruktor hat, müssen Sie die Parameter für den Basisklassenkonstruktor im abgeleiteten Klassenkonstruktor angeben:

```cpp
class Box {
public:
    Box(int width, int length, int height){
       m_width = width;
       m_length = length;
       m_height = height;
    }

private:
    int m_width;
    int m_length;
    int m_height;
};

class StorageBox : public Box {
public:
    StorageBox(int width, int length, int height, const string label&) : Box(width, length, height){
        m_label = label;
    }
private:
    string m_label;
};

int main(){

    const string aLabel = "aLabel";
    StorageBox sb(1, 2, 3, aLabel);
}
```

Wenn ein Konstruktor eine Ausnahme auslöst, ist die Reihenfolge der Zerstörung die umgekehrte Reihenfolge der Erstellung:

1. Der Code im Text der Konstruktorfunktion wird entladen.

1. Basisklassen- und Memberobjekte werden in der umgekehrten Reihenfolge der Deklaration zerstört.

1. Wenn der Konstruktor nicht delegierend ist, werden alle vollständig erstellten Basisklassenobjekte und Member zerstört. Da jedoch das Objekt selbst nicht vollständig erstellt wird, wird der Destruktor nicht ausgeführt.

### <a name="constructors-for-classes-that-have-multiple-inheritance"></a>Konstruktoren für Klassen mit mehrfachvererbung

Wenn eine Klasse von mehreren Basisklassen abgeleitet ist, werden die Basisklassenkonstruktoren in der Reihenfolge aufgerufen, in der sie in der Deklaration der abgeleiteten Klasse aufgelistet sind:

```cpp
#include <iostream>
using namespace std;

class BaseClass1 {
public:
    BaseClass1() { cout << "BaseClass1 ctor\n"; }
};
class BaseClass2 {
public:
    BaseClass2() { cout << "BaseClass2 ctor\n"; }
};
class BaseClass3 {
public:
    BaseClass3() { cout << "BaseClass3 ctor\n"; }
};
class DerivedClass : public BaseClass1,
                     public BaseClass2,
                     public BaseClass3
                     {
public:
    DerivedClass() { cout << "DerivedClass ctor\n"; }
};

int main() {
    DerivedClass dc;
}
```

Die folgende Ausgabe sollte angezeigt werden:

```Output
BaseClass1 ctor
BaseClass2 ctor
BaseClass3 ctor
DerivedClass ctor
```

## <a name="virtual_functions_in_constructors"></a> Virtuelle Funktionen in Konstruktoren

Beim Aufrufen von virtuellen Funktionen in Konstruktoren wird zur Vorsicht geraten. Da der Basisklassenkonstruktor immer vor dem abgeleiteten Klassenkonstruktor aufgerufen wird, ist die im Basiskonstruktor aufgerufene Funktion die Basisklassenversion und nicht die Version der abgeleiteten Klasse. Im folgenden Beispiel bewirkt die Erstellung von `DerivedClass`, dass die `BaseClass`-Implementierung von `print_it()` ausgeführt wird, bevor der `DerivedClass`-Konstruktor veranlasst, dass die `DerivedClass`-Implementierung von `print_it()` ausgeführt wird:

```cpp
#include <iostream>
using namespace std;

class BaseClass{
public:
    BaseClass(){
        print_it();
    }
    virtual void print_it() {
        cout << "BaseClass print_it" << endl;
    }
};

class DerivedClass : public BaseClass {
public:
    DerivedClass() {
        print_it();
    }
    virtual void print_it(){
        cout << "Derived Class print_it" << endl;
    }
};

int main() {

    DerivedClass dc;
}
```

Die Ausgabe ist wiefolgt:

```Output
BaseClass print_it
Derived Class print_it
```

## <a name="delegating_constructors"></a> Delegierende Konstruktoren

Ein *delegierender Konstruktor* ruft Sie einen anderen Konstruktor in derselben Klasse Teil der Arbeit der Initialisierung zu tun. Dies ist nützlich, wenn Sie über mehrere Konstruktoren verfügen, die alle ähnliche Aufgaben ausführen müssen. Sie können die Haupt-Logik in einem Konstruktor schreiben und ihn von anderen aufrufen. Die folgende einfache Beispiel delegiert Box(int) seiner Arbeit, die Box(int,int,int):

```cpp
class Box {
public:
    // Default constructor
    Box() {}

    // Initialize a Box with equal dimensions (i.e. a cube)
    Box(int i) :  Box(i, i, i);  // delegating constructor
    {}

    // Initialize a Box with custom dimensions
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}
    //... rest of class as before
};
```

Das von den Konstruktoren erstellte Objekt wird vollständig initialisiert, sobald jeder Konstruktor abgeschlossen ist. Weitere Informationen finden Sie unter [einheitliche Initialisierung und Delegierung von Konstruktoren](../cpp/uniform-initialization-and-delegating-constructors.md).

## <a name="inheriting_constructors"></a> Konstruktorvererbung (C ++ 11)

Eine abgeleitete Klasse kann die Konstruktoren von einer direkten Basisklasse erben, mithilfe einer **mit** Deklaration, wie im folgenden Beispiel gezeigt:

```cpp
#include <iostream>
using namespace std;

class Base
{
public:
    Base() { cout << "Base()" << endl; }
    Base(const Base& other) { cout << "Base(Base&)" << endl; }
    explicit Base(int i) : num(i) { cout << "Base(int)" << endl; }
    explicit Base(char c) : letter(c) { cout << "Base(char)" << endl; }

private:
    int num;
    char letter;
};

class Derived : Base
{
public:
    // Inherit all constructors from Base
    using Base::Base;

private:
    // Can't initialize newMember from Base constructors.
    int newMember{ 0 };
};

int main()
{
    cout << "Derived d1(5) calls: ";
    Derived d1(5);
    cout << "Derived d1('c') calls: ";
    Derived d2('c');
    cout << "Derived d3 = d2 calls: " ;
    Derived d3 = d2;
    cout << "Derived d4 calls: ";
    Derived d4;
}

/* Output:
Derived d1(5) calls: Base(int)
Derived d1('c') calls: Base(char)
Derived d3 = d2 calls: Base(Base&)
Derived d4 calls: Base()*/
```

**Visual Studio 2017 Version 15.7 und höher**: Die **mit** -Anweisung in **/Std: c ++ 17** Modus in den Bereich versetzt alle Konstruktoren aus der Basisklasse mit Ausnahme derjenigen, die eine identische Signatur wie Konstruktoren in der abgeleiteten Klasse aufweisen. Im Allgemeinen empfiehlt es sich, erbende Konstruktoren zu verwenden, wenn die abgeleitete Klasse keine neuen Datenmember oder Konstruktoren deklariert. Siehe auch [Verbesserungen in Visual Studio 2017 Version 15.7](../overview/cpp-conformance-improvements-2017.md#improvements_157).

Eine Klassenvorlage kann alle Konstruktoren aus einem Typargument erben, wenn dieser Typ eine Basisklasse angibt:

```cpp
template< typename T >
class Derived : T {
    using T::T;   // declare the constructors from T
    // ...
};
```

Eine erbende Klasse kann nicht aus mehreren Basisklassen erben, wenn diese Basisklassen über Konstruktoren mit einer identischen Signatur verfügen.

## <a name="constructors_in_composite_classes"></a> Konstruktoren und zusammengesetzte Klassen

Klassen, die klassentypmember enthalten, werden als bezeichnet *zusammengesetzte Klassen*. Wenn ein Klassentypmember einer zusammengesetzten Klasse erstellt wird, wird der Konstruktor vor dem Konstruktor der Klasse aufgerufen. Wenn einer enthaltenen Klasse ein Standardkonstruktor fehlt, müssen Sie eine Initialisierungsliste im Konstruktor der zusammengesetzten Klasse verwenden. Wenn Sie im `StorageBox`-Beispiel oben den Typ der `m_label`-Membervariable in eine neue `Label`-Klasse ändern, müssen Sie den Basisklassenkonstruktor aufrufen und die `m_label`-Variable im `StorageBox`-Konstruktor initialisieren:

```cpp
class Label {
public:
    Label(const string& name, const string& address) { m_name = name; m_address = address; }
    string m_name;
    string m_address;
};

class StorageBox : public Box {
public:
    StorageBox(int width, int length, int height, Label label)
        : Box(width, length, height), m_label(label){}
private:
    Label m_label;
};

int main(){
// passing a named Label
    Label label1{ "some_name", "some_address" };
    StorageBox sb1(1, 2, 3, label1);

    // passing a temporary label
    StorageBox sb2(3, 4, 5, Label{ "another name", "another address" });

    // passing a temporary label as an initializer list
    StorageBox sb3(1, 2, 3, {"myname", "myaddress"});
}
```
