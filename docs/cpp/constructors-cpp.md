---
title: Konstruktoren (C++) | Microsoft Docs
ms.custom: ''
ms.date: 04/06/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- constructors [C++]
- objects [C++], creating
- instance constructors
ms.assetid: 3e9f7211-313a-4a92-9584-337452e061a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d34dff9c04491c25b2babfd4e7f0574bf7c6c609
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="constructors-c"></a>Konstruktoren (C++)

Anpassen, wie Klasse, Elemente initialisiert werden, oder zum Aufrufen von Funktionen, wenn ein Objekt der Klasse erstellt wird, definieren eine *Konstruktor*. Ein Konstruktor hat den gleichen Namen wie die Klasse und weist keinen Rückgabewert auf. Sie können beliebig viele überladene Konstruktoren nach Bedarf, um die Initialisierung auf verschiedene Arten anpassen definieren. Konstruktoren in der Regel besitzen öffentliche zugreifbarkeit, damit Code außerhalb der Klassenhierarchie Definition oder Vererbung Objekte der Klasse erstellen kann. Sie können auch einen Konstruktor als deklariert jedoch **geschützt** oder **private**.

Optional können Mitglied Liste mit Init Konstruktoren. Dies ist eine effizientere Methode zum Initialisieren von Klassenmembern als Zuweisen von Werten im Konstruktortext. Das folgende Beispiel zeigt eine Klasse `Box` mit drei überladene Konstruktoren. Verwenden Sie die letzten beiden Init Memberlisten:

```cpp

class Box {
public:
    // Default constructor
    Box() {}

    // Initalize a Box with equal dimensions (i.e. a cube)
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

Wenn Sie eine Instanz einer Klasse deklarieren, wählt der Compiler an, welcher Konstruktor aufrufen auf den Regeln der Auflösung von funktionsüberladungen basieren:

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

- Konstruktoren können deklariert werden, als **Inline**, [explizite](#explicit_constructors), **"Friend"** oder [Constexpr](#constexpr_constructors).
- Ein Konstruktor kann ein Objekt, das als deklariert wurde initialisieren **const**, **volatile** oder **const Volatile**. Das Objekt nicht mehr **const** nach Abschluss der Konstruktor.
- Um einen Konstruktor in einer Implementierungsdatei definieren, geben Sie ihm einen qualifizierten Name wie bei jeder anderen Memberfunktion: `Box::Box(){...}`.

## <a name="member_init_list"></a> Memberlisten-Initialisierer

Ein Konstruktor kann optional eine Memberinitialisiererliste haben vor der Ausführung von Konstruktortext-Klasse, Elemente initialisiert. (Beachten Sie, dass eine Memberinitialisiererliste nicht dasselbe wie eine *Initialisiererliste* des Typs [Std:: initializer_list\<T >](../standard-library/initializer-list-class.md).)

Mithilfe einer Initialisiererliste Member wird über das Zuweisen von Werten in den Text des Konstruktors, da es direkt auf das Element initialisiert bevorzugt. Im folgenden Beispiel wird der Memberinitialisierer besteht aus der Liste aller der **identifier(argument)** hinter dem Doppelpunkt stehenden Ausdrücke:

```cpp
  
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height)
    {}
```

Der Bezeichner muss auf einen Klassenmember beziehen. Es wird mit dem Wert des Arguments initialisiert. Das Argument kann eine der Konstruktorparameter auftreten, ein Funktionsaufruf oder eine [Std:: initializer_list\<T >](../standard-library/initializer-list-class.md). 

**const** Member und Member der Verweistyp müssen in der Member-Initialisierungsliste initialisiert werden.

Aufrufe von parametrisierten Konstruktoren sollten in der Initialisiererliste vorgenommen werden, um sicherzustellen, dass die Basisklasse vollständig vor der Ausführung von der abgeleitete Konstruktor initialisiert wurde.

## <a name="default_constructors"></a> Standardkonstruktoren

 *Standardkonstruktoren* in der Regel keine Parameter besitzen, aber können Parameter mit Standardwerten.

```cpp
class Box {
public:
    Box() { /*perform any required default initialization steps*/}

    // All params have default values
    Box (int w = 1, int l = 1, int h = 1): m_width(w), m_height(h), m_length(l){}
...
}
```

Standardkonstruktoren zählen zu der die [spezielle Memberfunktionen](special-member-functions.md). Wenn keine Konstruktoren in einer Klasse deklariert werden, stellt der Compiler einen impliziten **Inline** Standardkonstruktor.

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

Wenn Sie einen impliziten Standardkonstruktor benötigen, müssen Sie Initialisieren von Membern in der Klassendefinition, wie im vorherigen Beispiel gezeigt. Ohne diese Initialisierer wäre der Member nicht initialisiert und Volume() Aufruf wäre einen Garbage-Wert. Im Allgemeinen ist es empfiehlt sich zum Initialisieren von Membern auf diese Weise auch, wenn nicht auf einen impliziten Standardkonstruktor verlassen.

Sie können verhindern, dass den Compiler generiert einen impliziten Standardkonstruktor definieren ihn als [gelöscht](#explicitly_defaulted_and_deleted_constructors):

```cpp

    // Default constructor
    Box() = delete;

```

Ein vom Compiler generierter Standardkonstruktor wird definiert als gelöscht, wenn keine Klassenmember standardmäßig erstellt werden. Beispielsweise müssen alle Member des Klassentyps und ihre klassentypmember haben, einen Standardkonstruktor und Destruktoren die zugegriffen werden kann. Geben Sie alle Datenmember des Verweistyps, auch als **const** Member müssen eine Standard-Memberinitialisierer aufweisen.

Wenn Sie einen Compiler generierter Standardkonstruktor aufrufen und versuchen Sie Klammern verwenden, wird eine Warnung ausgegeben:

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
    Box(int width, int length, int height)
        : m_width(width), m_length(length), m_height(height){}
};
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

Sie können jedoch einen Satz von Initialisiererlisten verwenden, zum Initialisieren eines Arrays von Objekten im Feld:

```cpp
Box boxes[3]{ { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };
```

Weitere Informationen finden Sie unter [Initialisierer](initializers.md).

## <a name="copy_and_move_constructors"></a> Kopierkonstruktoren

Ein *Kopierkonstruktor* Initialisiert ein Objekt durch Kopieren der Werte der Elemente aus einem Objekt des gleichen Typs. Wenn die Klassenmember alle einfachen Typen z. B. Skalare Werte sind, vom Compiler generierte Kopierkonstruktor ist ausreichend, und Sie müssen nicht Definieren eigener. Wenn Ihre Klasse komplexere Initialisierung erforderlich ist, müssen Sie einen benutzerdefinierten Kopierkonstruktor zu implementieren. Z. B. wenn ein Klassenmember ein Zeiger ist müssen Sie einen Kopierkonstruktor, um neue Arbeitsspeicher belegen, und kopieren Sie die Werte aus der anderen auf Objekt definieren. Vom Compiler generierte Kopierkonstruktor kopiert einfach den Zeiger, damit der neue Zeiger weiterhin auf die andere Speicheradresse verweist.

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

Sie können verhindern, dass das Objekt kopiert werden, indem der Kopierkonstruktor als gelöscht definiert:

```cpp
    Box (const Box& other) = delete;
```

Fehler beim Kopieren der des Objekts erzeugt *C2280: Versuch, auf eine gelöschte Funktion verweisen*.

## <a name="move_constructors"></a> Bewegungskonstruktoren
Ein *bewegungskonstruktor* ist eine spezielle Memberfunktion, die Daten für ein vorhandenes Objekt in eine neue Variable verschiebt, ohne den ursprünglichen Daten zu kopieren. Er akzeptiert einen Rvalue-Verweis als ersten Parameter, und alle weiteren Parameter müssen Standardwerte haben. Bewegungskonstruktoren können die Effizienz des Programms erheblich steigern, bei der Übergabe großer Objekte. Ein Move-Konstruktor akzeptiert einen Rvalue-Verweis als erster Parameter an. Alle anderen Parameter müssen Standardwerte haben.

```cpp
Box(Box&& other);
```

Der Compiler entscheidet Ressourcen ein bewegungskonstruktor in bestimmten Situationen, in dem das Objekt von einem anderen Objekt desselben Typs initialisiert wird, die zerstört werden soll und nicht mehr benötigt wird. Das folgende Beispiel zeigt einen Fall, wenn ein bewegungskonstruktor von überladungsauflösung ausgewählt ist. Die Variable *Feld* get_Box() zurückgegebenes ist ein *Xvalue* (ablaufenden Wert) also außerhalb des Gültigkeitsbereichs liegen. Zum Bereitstellen von Motivation für dieses Beispiel geben wir Feld einen großen Vektor von Zeichenfolgen, die den Inhalt darstellen. Anstatt das Kopieren des Vektors und Zeichenfolgen, stiehlt"der Verschiebungskonstruktor" es aus dem ablaufenden Wert "Box", damit der Vektor jetzt mit dem neuen Objekt gehört. Der Aufruf von `std::move` ist die einzige erforderliche da beide `vector` und `string` Klassen implementieren ihre eigenen bewegungskonstruktoren.

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

Wenn eine Klasse, die nicht über einen bewegungskonstruktor definiert, generiert der Compiler eine implizite aus, wenn es keine benutzerdeklarierten Kopierkonstruktor, Kopierzuweisungsoperator, bewegungszuweisungsoperator oder Destruktor ist. Wenn keine explizite oder implizite bewegungskonstruktor definiert ist, verwenden Sie stattdessen auszuführen, die andernfalls einen bewegungskonstruktor verwendet, würde, den Kopierkonstruktor. Wenn ein bewegungskonstruktor oder bewegungszuweisungsoperator eine Klasse deklariert wird, wird der implizit deklarierten Kopierkonstruktor definiert, als gelöscht.

Eine implizit deklarierte bewegungskonstruktor wird als gelöscht definiert, wenn alle Elemente, die Klassentypen sind einen Destruktor fehlender oder der Compiler kann nicht feststellen, welcher Konstruktor für den Verschiebevorgang verwendet.

Weitere Informationen dazu, wie Sie einen nicht trivialen bewegungskonstruktor schreiben, finden Sie unter [Bewegungskonstruktoren und Bewegungszuweisungsoperatoren (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md).

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

Ein Konstruktor kann deklariert werden, als [Constexpr](constexpr-cpp.md) Wenn

- Es ist entweder deklariert werden, da übernommen, da sonst es erfüllt die Bedingungen für [Constexpr-Funktionen](constexpr-cpp.md#constexpr_functions) im Allgemeinen;
- die Klasse verfügt über keine virtuellen Basisklassen;
- jede der Parameter ist ein [Literaltyp](trivial-standard-layout-and-pod-types.md#literal_types);
- der Text ist keine Funktion Try-Block.
- alle nicht statischen Datenmember und untergeordnete Basisklassenobjekte initialisiert;
- Wenn die Klasse ist "(a) eine Union mit variant-Member" oder (b) verfügt über anonyme Unions, ist nur eine union-Member initialisiert.
- alle nicht statischen Datenmember des Klassentyps und alle untergeordneten Objekte von Basisklasse haben einen Constexpr-Konstruktor


## <a name="init_list_constructors"></a> Initialisierer Liste Konstruktoren

Wenn ein Konstruktor akzeptiert ein [Std:: initializer_list\<T\> ](../standard-library/initializer-list-class.md) wie Parameter und alle anderen Parameter Standardargumente haben, diesen Konstruktor ausgewählt werden an der überladungsauflösung, wenn die Klasse ist durch direkte Initialisierung instanziiert. Das initializer_list-Element können Sie um einen beliebigen Member zu initialisieren, der sie akzeptieren können. Nehmen wir beispielsweise an die Box-Klasse, die (zuvor gezeigt) verfügt über eine `std::vector<string>` Member **M_contents**. Sie können einen Konstruktor wie folgt angeben:

```cpp
    Box(initializer_list<string> list, int w = 0, int h = 0, int l = 0)
        : m_contents(list), m_width(w), m_height(h), m_length(l)
{}
```

Und erstellen Sie im Feld Objekte wie folgt:

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

Derartige Konvertierungen können in einigen Fällen hilfreich sein. Häufiger führen sie jedoch möglicherweise zu feinen, aber schwerwiegenden Fehlern in Ihrem Code. Als allgemeine Regel, sollten Sie verwenden die **explizite** Schlüsselwort auf einen Konstruktor (und benutzerdefinierten Operatoren), um diese Art der impliziten typkonvertierung zu verhindern:

```cpp

explicit Box(int size): m_width(size), m_length(size), m_height(size){}
```

Wenn der Konstruktor explizit ist, verursacht diese Zeile einen Compilerfehler: `ShippingOrder so(42, 10.8);`.  Weitere Informationen finden Sie unter [benutzerdefinierte Typkonvertierungen](../cpp/user-defined-type-conversions-cpp.md).

## <a name="order_of_construction"></a> Reihenfolge der Erstellung

Ein Konstruktor führt die Arbeit in folgender Reihenfolge aus:

1. Er ruft Basisklassen- und Memberkonstruktoren in der Reihenfolge der Deklaration auf.

2. Wenn die Klasse von virtuellen Basisklassen abgeleitet wird, initialisiert er die virtuellen Basiszeiger des Objekts.

3. Wenn die Klasse virtuelle Funktionen hat oder erbt, initialisiert er die virtuellen Funktionszeiger des Objekts. Virtuelle Funktionszeiger zeigen auf die virtuelle Funktionstabelle der Klasse, um eine korrekte Bindung von virtuellen Funktionsaufrufen im Code zu ermöglichen.

4. Er führt den Code im Funktionsrumpf aus.

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

```output
Contained1 ctor
Contained2 ctor
BaseContainer ctor
Contained3 ctor
DerivedContainer ctor
```

Ein abgeleiteter Klassenkonstruktor ruft immer einen Basisklassenkonstruktor auf, damit er immer auf vollständig erstellte Basisklassen zurückgreifen kann, bevor zusätzliche Arbeit erforderlich ist. Die Basisklassenkonstruktoren werden in der Reihenfolge der Ableitung aufgerufen. Beispiel: Wenn ClassA von ClassB abgeleitet ist, die von ClassC abgeleitet ist, wird zuerst der ClassC-Konstruktor, dann der ClassB-Konstruktor und anschließend der ClassA-Konstruktor aufgerufen.

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

```output

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

```output
BaseClass print_it
Derived Class print_it
```

## <a name="delegating_constructors"></a> Delegierende Konstruktoren

Ein *delegierender Konstruktor* einen anderen Konstruktor in der gleichen Klasse dazu Teil der Arbeit der Initialisierung aufgerufen. Dies ist hilfreich, wenn Sie mehrere Konstruktoren haben, dass alle ähnliche Aufgaben ausführen müssen. Sie können die Hauptlogik in einen Konstruktor schreiben und rufen Sie sie von anderen. Im folgenden Beispiel triviale delegiert Box(int) ihre Arbeit Box(int,int,int):

```cpp
class Box {
public:
    // Default constructor
    Box() {}

    // Initalize a Box with equal dimensions (i.e. a cube)
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

Eine abgeleitete Klasse kann die Konstruktoren mithilfe einer „using“-Deklaration aus einer direkten Basisklasse erben, wie dies im folgenden Beispiel gezeigt wird:

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

Mithilfe der „using“-Anweisung werden alle Konstruktoren aus dieser Basisklasse mit Ausnahme jener, die eine identische Signatur wie die Konstruktoren in der abgeleiteten Klasse aufweisen, in den Bereich versetzt. Im Allgemeinen empfiehlt es sich, erbende Konstruktoren zu verwenden, wenn die abgeleitete Klasse keine neuen Datenmember oder Konstruktoren deklariert.

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