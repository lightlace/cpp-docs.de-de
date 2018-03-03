---
title: Konstruktoren (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- constructors [C++]
- objects [C++], creating
- instance constructors
ms.assetid: 3e9f7211-313a-4a92-9584-337452e061a9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 57854ec15d3104d80e8dbba68ebc33937222172f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="constructors-c"></a>Konstruktoren (C++)
Ein Konstruktor ist eine Art einer Memberfunktion, die eine Instanz ihrer Klasse initialisiert. Ein Konstruktor hat den gleichen Namen wie die Klasse und weist keinen Rückgabewert auf. Ein Konstruktor kann über eine beliebige Anzahl von Parametern verfügen, und eine Klasse weist möglicherweise eine beliebige Anzahl an überladenen Konstruktoren auf. Konstruktoren können jede Erreichbarkeit aufweisen: öffentlich, geschützt oder privat. Wenn Sie keine Konstruktoren definieren, generiert der Compiler einen Standardkonstruktor, der keine Parameter verwendet. Sie können dieses Verhalten überschreiben, indem Sie einen Standardkonstruktor als gelöscht deklarieren.  
  
## <a name="in-this-topic"></a>In diesem Thema  
  
-   [Reihenfolge der Erstellung](#order_of_construction)  
  
-   [Memberlisten](#member_lists)  
  
-   [Explizite Konstruktoren](#explicit_constructors)  
  
-   [Standardkonstruktoren](#default_constructors)  
  
-   [Kopier- und Bewegungskonstruktoren](#copy_and_move_constructors)  
  
-   [Explizit vorgegebene und gelöschte Konstruktoren](#explicitly_defaulted_and_deleted_constructors)  
  
-   [Konstruktoren in abgeleiteten Klassen](#constructors_in_derived_classes)  
  
-   [Virtuelle Funktionen in Konstruktoren](#virtual_functions_in_constructors)  
  
-   [Konstruktoren und zusammengesetzte Klassen](#constructors_in_composite_classes)  
  
-   [Delegierende Konstruktoren](#delegating_constructors)  
  
-   [Konstruktorvererbung (C ++ 11)](#inheriting_constructors)  
  
-   [Regeln zum Deklarieren von Konstruktoren](#rules_for_declaring_constructors)  
  
-   [Explizites Aufrufen von Konstruktoren](#explicitly_invoking_constructors)  
  
##  <a name="order_of_construction"></a>Reihenfolge der Erstellung  
 Ein Konstruktor führt die Arbeit in folgender Reihenfolge aus:  
  
1.  Er ruft Basisklassen- und Memberkonstruktoren in der Reihenfolge der Deklaration auf.  
  
2.  Wenn die Klasse von virtuellen Basisklassen abgeleitet wird, initialisiert er die virtuellen Basiszeiger des Objekts.  
  
3.  Wenn die Klasse virtuelle Funktionen hat oder erbt, initialisiert er die virtuellen Funktionszeiger des Objekts. Virtuelle Funktionszeiger zeigen auf die virtuelle Funktionstabelle der Klasse, um eine korrekte Bindung von virtuellen Funktionsaufrufen im Code zu ermöglichen.  
  
4.  Er führt den Code im Funktionsrumpf aus.  
  
 Das folgende Beispiel zeigt die Reihenfolge, in der Basisklassen- und Memberkonstruktoren im Konstruktor für eine abgeleitete Klasse aufgerufen werden. Zuerst wird der Basiskonstruktor aufgerufen. Anschließend werden die Basisklassenmember in der Reihenfolge initialisiert, in der sie in der Klassendeklaration stehen. Danach wird der abgeleitete Konstruktor aufgerufen.  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class Contained1 {  
public:  
    Contained1() {  
        cout << "Contained1 constructor." << endl;  
    }  
};  
  
class Contained2 {  
public:  
    Contained2() {  
        cout << "Contained2 constructor." << endl;  
    }  
};  
  
class Contained3 {  
public:  
    Contained3() {  
        cout << "Contained3 constructor." << endl;  
    }  
};  
  
class BaseContainer {  
public:  
    BaseContainer() {  
        cout << "BaseContainer constructor." << endl;  
    }  
private:  
    Contained1 c1;  
    Contained2 c2;  
};  
  
class DerivedContainer : public BaseContainer {  
public:  
    DerivedContainer() : BaseContainer() {  
        cout << "DerivedContainer constructor." << endl;  
    }  
private:  
    Contained3 c3;  
};  
  
int main() {  
    DerivedContainer dc;  
    int x = 3;  
}  
  
```  
  
 Die Ausgabe ist wiefolgt:  
  
```  
Contained1 constructor.  
Contained2 constructor.  
BaseContainer constructor.  
Contained3 constructor.  
DerivedContainer constructor.  
```  
  
 Wenn ein Konstruktor eine Ausnahme auslöst, ist die Reihenfolge der Zerstörung die umgekehrte Reihenfolge der Erstellung:  
  
1.  Der Code im Text der Konstruktorfunktion wird entladen.  
  
2.  Basisklassen- und Memberobjekte werden in der umgekehrten Reihenfolge der Deklaration zerstört.  
  
3.  Wenn der Konstruktor nicht delegierend ist, werden alle vollständig erstellten Basisklassenobjekte und Member zerstört. Da jedoch das Objekt selbst nicht vollständig erstellt wird, wird der Destruktor nicht ausgeführt.  
  
##  <a name="member_lists"></a>Memberlisten  
 Initialisieren Sie Klassenmember aus Konstruktorargumenten durch die Verwendung einer Memberinitialisiererliste. Diese Methode verwendet *direkte Initialisierung*, effizienter als die Verwendung von Zuweisungsoperatoren im konstruktortextteil ist.  
  
```cpp  
class Box {  
public:  
    Box(int width, int length, int height)   
        : m_width(width), m_length(length), m_height(height) // member init list  
    {}  
    int Volume() {return m_width * m_length * m_height; }  
private:  
    int m_width;  
    int m_length;  
    int m_height;  
  
};  
  
```  
  
 Erstellen Sie ein Box-Objekt:  
  
```  
Box b(42, 21, 12);  
cout << "The volume is " << b.Volume();  
```  
  
##  <a name="explicit_constructors"></a>Explizite Konstruktoren  
 Wenn eine Klasse einen Konstruktor mit einem einzelnen Parameter aufweist oder wenn alle Parameter mit Ausnahmen von einem einen Standardwert besitzen, kann der Parametertyp impliziert zum Klassentyp konvertiert werden. Beispielsweise wenn die `Box`-Klasse über einen derartigen Konstruktor verfügt:  
  
```  
Box(int size): m_width(size), m_length(size), m_height(size){}  
```  
  
 Es ist möglich, ein Feld wie folgt zu initialisieren:  
  
```  
Box b = 42;  
```  
  
 Alternativ können Sie eine Ganzzahl an eine Funktion weiterleiten, die ein Feld verwendet:  
  
```  
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
  
 Derartige Konvertierungen können in einigen Fällen hilfreich sein. Häufiger führen sie jedoch möglicherweise zu feinen, aber schwerwiegenden Fehlern in Ihrem Code. Sie sollten das `explicit`-Schlüsselwort im Allgemeinen für einen Konstruktor (und benutzerdefinierten Operatoren) verwenden, um diese Art der impliziten Typkonvertierung zu verhindern:  
  
```  
  
explicit Box(int size): m_width(size), m_length(size), m_height(size){}  
```  
  
 Wenn der Konstruktor explizit ist, verursacht diese Zeile einen Compilerfehler: `ShippingOrder so(42, 10.8);`.  Weitere Informationen finden Sie unter [benutzerdefinierte Typkonvertierungen](../cpp/user-defined-type-conversions-cpp.md).  
  
##  <a name="default_constructors"></a>Standardkonstruktoren  
 *Standardkonstruktoren* darf keine Parameter; sie etwas andere Regeln entsprechen:  
  
 Standardkonstruktoren zählen zu der die *spezielle Memberfunktionen*; Wenn keine Konstruktoren in einer Klasse deklariert werden der Compiler stellt einen Standardkonstruktor bereit:  
  
```cpp  
class Box {  
    Box(int width, int length, int height)   
        : m_width(width), m_length(length), m_height(height){}  
};  
  
int main(){  
  
    Box box1{}; // call compiler-generated default ctor  
    Box box2;   // call compiler-generated default ctor  
}  
```  
  
 Wenn Sie einen Standardkonstruktor aufrufen und versuchen, runde Klammern zu verwenden, wird eine Warnung ausgegeben:  
  
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
    Box box4;     // compiler error C2512: no appropriate default constructor available  
}  
  
```  
  
 Wenn eine Klasse keinen Standardkonstruktor hat, kann ein Array von Objekten dieser Klasse nicht allein mithilfe von Syntax in eckigen Klammern erstellt werden. Beispielsweise kann im vorherigen Codeblock ein Array von Feldern nicht folgendermaßen deklariert werden:  
  
```cpp  
Box boxes[3];    // compiler error C2512: no appropriate default constructor available  
  
```  
  
 Sie können jedoch einen Satz von Initialisiererlisten verwenden, um ein Array von Feldern zu initialisieren:  
  
```cpp  
Box boxes[3]{ { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };  
```  
  
##  <a name="copy_and_move_constructors"></a>Kopier- und Bewegungskonstruktoren  
 Ein *Kopierkonstruktor* ist eine spezielle Memberfunktion, die als Eingabe ein Verweis auf ein Objekt des gleichen geben, und erstellt eine Kopie des Zertifikats. Weitere Informationen finden Sie unter [Kopierkonstruktoren und Kopie Bewegungszuweisungsoperatoren (C++)](../cpp/copy-constructors-and-copy-assignment-operators-cpp.md). Ein *bewegungskonstruktor* ist auch eine spezielle Memberfunktion, die Daten für ein vorhandenes Objekt in eine neue Variable verschiebt, ohne den ursprünglichen Daten zu kopieren. Weitere Informationen finden Sie unter [Bewegungskonstruktoren und Bewegungszuweisungsoperatoren (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md).  
  
##  <a name="explicitly_defaulted_and_deleted_constructors"></a>Explizit vorgegebene und gelöschte Konstruktoren  
 Sie können explizit *Standard* Kopierkonstruktoren, Standardkonstruktoren, bewegungskonstruktoren, Kopierzuweisungsoperatoren, bewegungszuweisungsoperatoren und Destruktoren zu verschieben. Sie können explizit *löschen* alle speziellen Memberfunktionen. Weitere Informationen finden Sie unter [explizit vorgegebene und gelöschte Funktionen](../cpp/explicitly-defaulted-and-deleted-functions.md).  
  
##  <a name="constructors_in_derived_classes"></a>Konstruktoren in abgeleiteten Klassen  
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
  
### <a name="constructors-for-classes-that-have-multiple-inheritance"></a>Konstruktoren für Klassen mit Mehrfachvererbung  
 Wenn eine Klasse von mehreren Basisklassen abgeleitet ist, werden die Basisklassenkonstruktoren in der Reihenfolge aufgerufen, in der sie in der Deklaration der abgeleiteten Klasse aufgelistet sind:  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class BaseClass1 {  
public:  
    BaseClass1() {  
        cout << "BaseClass1 constructor." << endl;  
    }  
};  
class BaseClass2 {  
public:  
    BaseClass2() {  
        cout << "BaseClass2 constructor." << endl;  
    }  
};  
class BaseClass3{  
public:  
    BaseClass3() {  
        cout << "BaseClass3 constructor." << endl;  
    }  
};  
class DerivedClass : public BaseClass1, public BaseClass2, public BaseClass3  {  
public:  
    DerivedClass() {  
        cout << "DerivedClass constructor." << endl;  
    }  
};  
  
int main() {  
    DerivedClass dc;  
}  
  
```  
  
 Die folgende Ausgabe sollte angezeigt werden:  
  
```  
BaseClass1 constructor.  
BaseClass2 constructor.  
BaseClass3 constructor.  
DerivedClass constructor.  
```  
  
##  <a name="virtual_functions_in_constructors"></a>Virtuelle Funktionen in Konstruktoren  
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
  
```  
BaseClass print_it  
Derived Class print_it  
```  
  
##  <a name="constructors_in_composite_classes"></a>Konstruktoren und zusammengesetzte Klassen  
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
  
##  <a name="delegating_constructors"></a>Delegierende Konstruktoren  
 Ein *delegierender Konstruktor* einen anderen Konstruktor in der gleichen Klasse dazu Teil der Arbeit der Initialisierung aufgerufen. Im folgenden Beispiel hat die abgeleitete Klasse drei Konstruktoren. Der zweite Konstruktor delegiert an den ersten, und der dritte Konstruktor delegiert an den zweiten:  
  
```cpp  
#include <iostream>  
using namespace std;  
  
class ConstructorDestructor {  
public:  
    ConstructorDestructor() {  
        cout << "ConstructorDestructor default constructor." << endl;  
    }  
    ConstructorDestructor(int int1) {  
        cout << "ConstructorDestructor constructor with 1 int." << endl;  
    }  
    ConstructorDestructor(int int1, int int2) : ConstructorDestructor(int1) {  
        cout << "ConstructorDestructor constructor with 2 ints." << endl;  
  
        throw exception();  
    }  
    ConstructorDestructor(int int1, int int2, int int3) : ConstructorDestructor(int1, int2) {  
        cout << "ConstructorDestructor constructor with 3 ints." << endl;  
    }  
    ~ConstructorDestructor() {  
        cout << "ConstructorDestructor destructor." << endl;  
    }  
};  
  
int main() {  
    ConstructorDestructor dc(1, 2, 3);  
}  
  
```  
  
 Die Ausgabe ist wiefolgt:  
  
```  
ConstructorDestructor constructor with 1 int.  
ConstructorDestructor constructor with 2 ints.  
ConstructorDestructor constructor with 3 ints.  
```  
  
 Das von den Konstruktoren erstellte Objekt wird vollständig initialisiert, sobald jeder Konstruktor abgeschlossen ist. `DerivedContainer(int int1)` ist erfolgreich, aber `DerivedContainer(int int1, int int2)` schlägt fehl, und der Destruktor wird aufgerufen.  
  
```cpp  
class ConstructorDestructor {  
public:  
    ConstructorDestructor() {  
        cout << "ConstructorDestructor default constructor." << endl;  
    }  
    ConstructorDestructor(int int1) {  
        cout << "ConstructorDestructor constructor with 1 int." << endl;  
    }  
    ConstructorDestructor(int int1, int int2) : ConstructorDestructor(int1) {  
        cout << "ConstructorDestructor constructor with 2 ints." << endl;  
        throw exception();  
    }  
    ConstructorDestructor(int int1, int int2, int int3) : ConstructorDestructor(int1, int2) {  
        cout << "ConstructorDestructor constructor with 3 ints." << endl;  
    }  
  
    ~ConstructorDestructor() {  
        cout << "ConstructorDestructor destructor." << endl;  
    }  
};  
  
int main() {  
  
    try {  
        ConstructorDestructor cd{ 1, 2, 3 };  
    }  
    catch (const exception& ex){  
    }  
}  
  
```  
  
 Ausgabe:  
  
```  
ConstructorDestructor constructor with 1 int.  
ConstructorDestructor constructor with 2 ints.  
ConstructorDestructor destructor.  
```  
  
 Weitere Informationen finden Sie unter [einheitliche Initialisierung und Delegierung von Konstruktoren](../cpp/uniform-initialization-and-delegating-constructors.md).  
  
##  <a name="inheriting_constructors"></a>Konstruktorvererbung (C ++ 11)  
 Eine abgeleitete Klasse kann die Konstruktoren mithilfe einer „using“-Deklaration aus einer direkten Basisklasse erben, wie dies im folgenden Beispiel gezeigt wird:  
  
```  
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
  
int main(int argc, char argv[])  
{  
    cout << "Derived d1(5) calls: ";   
    Derived d1(5);  
    cout << "Derived d1('c') calls: ";  
    Derived d2('c');  
    cout << "Derived d3 = d2 calls: " ;  
    Derived d3 = d2;  
    cout << "Derived d4 calls: ";  
    Derived d4;   
  
    // Keep console open in debug mode:  
    cout << endl << "Press Enter to exit.";  
    char in[1];  
    cin.getline(in, 1);  
    return 0;  
}  
  
/* Output:  
Derived d1(5) calls: Base(int)  
Derived d1('c') calls: Base(char)  
Derived d3 = d2 calls: Base(Base&)  
Derived d4 calls: Base()  
  
Press Enter to exit.  
  
```  
  
 Mithilfe der „using“-Anweisung werden alle Konstruktoren aus dieser Basisklasse mit Ausnahme jener, die eine identische Signatur wie die Konstruktoren in der abgeleiteten Klasse aufweisen, in den Bereich versetzt. Im Allgemeinen empfiehlt es sich, erbende Konstruktoren zu verwenden, wenn die abgeleitete Klasse keine neuen Datenmember oder Konstruktoren deklariert.  
  
 Eine Klassenvorlage kann alle Konstruktoren aus einem Typargument erben, wenn dieser Typ eine Basisklasse angibt:  
  
```  
template< typename T >  
class Derived : T {  
    using T::T;   // declare the constructors from T  
    // ...  
};  
  
```  
  
 Eine erbende Klasse kann nicht aus mehreren Basisklassen erben, wenn diese Basisklassen über Konstruktoren mit einer identischen Signatur verfügen.  
  
##  <a name="rules_for_declaring_constructors"></a>Regeln zum Deklarieren von Konstruktoren  
 Ein Konstruktor hat den gleichen Namen wie seine Klasse. Eine beliebige Anzahl von Konstruktoren kann abhängig von den Regeln der überladenen Funktionen deklariert werden.  
  
 `argument-declaration-list` kann leer sein.  
  
 C++ definiert zwei spezielle Arten von Konstruktoren, Standard- und Kopierkonstruktoren, die in der folgenden Tabelle beschrieben werden.  
  
### <a name="default-and-copy-constructors"></a>Standard- und Kopierkonstruktoren  
  
|Art der Konstruktion|Argumente|Zweck|  
|--------------------------|---------------|-------------|  
|Standardkonstruktor|Kann ohne Argumente aufgerufen werden|Erstellen eines Standardobjekttyps des Klassentyps|  
|Kopierkonstruktor|Kann ein einzelnes Argument des Verweises auf den gleichen Klassentyp akzeptieren|Kopieren von Objekten des Klassentyps|  
  
 Standardkonstruktoren können ohne Argumente aufgerufen werden. Sie können jedoch einen Standardkonstruktor mit einer Argumentliste deklarieren, sofern alle Argumente über Standardwerte verfügen. Ebenso müssen Kopierkonstruktoren ein einzelnes Argument des Verweises auf denselben Klassentyp akzeptieren. Weitere Argumente können bereitgestellt werden, wenn alle nachfolgenden Argumente über Standardwerte verfügen.  
  
 Wenn Sie keine Konstruktoren angeben, versucht der Compiler, einen Standardkonstruktor zu generieren. Wenn Sie keinen Kopierkonstruktor angeben, versucht der Compiler, einen zu generieren. Diese vom Compiler generierten Konstruktoren gelten als öffentliche Memberfunktionen. Ein Fehler wird generiert, wenn Sie einen Kopierkonstruktor mit dem ersten Argument angeben, das ein Objekt und kein Verweis ist.  
  
 Ein vom Compiler generierter Standardkonstruktor initialisiert das Objekt (installiert vftables und vbtables, wie zuvor beschrieben), und ruft die Standardkonstruktoren für Basisklassen und Member auf, führt aber keine weiteren Aktionen aus. Basisklassen- und Memberkonstruktoren werden nur aufgerufen, wenn sie vorhanden sind, wenn auf sie zugegriffen werden kann und wenn sie eindeutig sind.  
  
 Ein vom Compiler generierter Kopierkonstruktor richtet ein neues Objekt ein und führt eine memberspezifische Kopie des Inhalts des zu kopierenden Objekts aus. Wenn Basisklassen- oder Memberkonstruktoren vorhanden sind, werden sie aufgerufen; andernfalls wird der bitweise Kopiervorgang ausgeführt.  
  
 Wenn alle Basis- und Memberklassen der Klasse `type` haben Kopierkonstruktoren, die akzeptieren ein **const** Argument, das vom Compiler generierte Kopierkonstruktor akzeptiert ein einzelnes Argument vom Typ **const** `type` **&**. Andernfalls akzeptiert der vom Compiler generierte Kopierkonstruktor ein einzelnes Argument vom Typ `type`  **&** .  
  
 Verwenden Sie einen Konstruktor zum Initialisieren einer **const** oder `volatile` -Objekt, aber der Konstruktor selbst kann nicht als deklariert werden **const** oder `volatile`. Ist der einzige zulässige Speicherklasse für einen Konstruktor **Inline**; verwenden, der eine beliebige andere Speicherklassenmodifizierer, einschließlich der `__declspec` -Schlüsselwort, klicken Sie mit einem Konstruktor, verursacht einen Compilerfehler.  
  
 Die "stdcall"-Aufrufkonvention wird für statische Memberfunktionen verwendet und globale Funktionen deklariert, mit der **__stdcall** -Schlüsselwort werden und keine Variablenargumentliste verwenden. Bei Verwendung der **__stdcall** -Schlüsselwort in einer nicht statischen Memberfunktion verwenden, z. B. einen Konstruktor, der Compiler die Thiscall-Aufrufkonvention verwendet. "  
  
 Konstruktoren von Basisklassen werden nicht von abgeleiteten Klassen geerbt. Wenn ein Objekt vom Typ einer abgeleiteten Klasse erstellt wird, werden für die Erstellung erst die Basisklassenkomponenten und dann die Komponenten der abgeleiteten Klasse verwendet. Wie das Teil des vollständigen Objekts initialisiert wird, verwendet der Compiler jedes Basisklassenkonstruktor (außer bei virtuellen ableitungen.  
  
##  <a name="explicitly_invoking_constructors"></a>Explizites Aufrufen von Konstruktoren  
 Konstruktoren können in einem Programm explizit aufgerufen werden, um Objekte eines bestimmten Typs zu erstellen. Um beispielsweise zwei `Point`-Objekte zu erstellen, die die Enden einer Zeile beschreiben, kann der folgende Code geschrieben werden:  
  
```  
DrawLine( Point( 13, 22 ), Point( 87, 91 ) );  
```  
  
 Zwei Objekte vom Typ `Point` werden erstellt, der Funktion `DrawLine` übergeben und am Ende des Ausdrucks (Funktionsaufruf) zerstört.  
  
 Ein anderer Kontext, in dem ein Konstruktor explizit aufgerufen wird, ist in einer Initialisierung:  
  
```  
Point pt = Point( 7, 11 );  
```  
  
 Ein Objekt vom Typ `Point` wird mithilfe des Konstruktors, der zwei Argumente des `int`-Typs akzeptiert, erstellt und initialisiert.  
  
 Objekte, die explizit von aufrufenden Konstruktoren erstellt werden, wie in den vorherigen beiden Beispielen, sind unbenannt und haben die Lebensdauer des Ausdrucks, in dem sie erstellt werden. Dies wird ausführlicher im [temporäre Objekte](../cpp/temporary-objects.md).  
  
 Es ist normalerweise sicher, alle Memberfunktionen aus einem Konstruktor aufzurufen, da das Objekt vor der Ausführung der ersten Zeile des Benutzercodes vollständig eingerichtet wurde (virtuelle Tabellen wurden initialisiert usw.). Allerdings ist es für eine Memberfunktion potenziell unsicher, während der Konstruktion oder der Zerstörung eine virtuelle Memberfunktion für eine abstrakte Basisklasse aufzurufen.  
  
 Konstruktoren können virtuelle Funktionen aufrufen. Beim Aufrufen von virtuellen Funktionen wird die für die eigene Klasse des Konstruktors definierte Funktion aufgerufen (oder von der Basisklasse vererbt). Das folgende Beispiel veranschaulicht, was geschieht, wenn eine virtuelle Funktion aus einem Konstruktor aufgerufen wird:  
  
```  
// specl_calling_virtual_functions.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class Base  
{  
public:  
    Base();             // Default constructor.  
    virtual void f();   // Virtual member function.  
};  
  
Base::Base()  
{  
    cout << "Constructing Base sub-object\n";  
    f();                // Call virtual member function  
}                       //  from inside constructor.  
  
void Base::f()  
{  
    cout << "Called Base::f()\n";  
}  
  
class Derived : public Base  
{  
public:  
    Derived();          // Default constructor.  
    void f();           // Implementation of virtual  
};                      //  function f for this class.  
  
Derived::Derived()  
{  
    cout << "Constructing Derived object\n";  
}  
  
void Derived::f()  
{  
    cout << "Called Derived::f()\n";  
}  
  
int main()  
{  
    Derived d;  
}  
```  
  
 Wenn das vorherige Programm ausgeführt wird, verursacht die `Derived d`-Deklaration die folgende Sequenz von Ereignissen:  
  
1.  Der Konstruktor für die `Derived`-Klasse (`Derived::Derived`) wird aufgerufen.  
  
2.  Vor dem Eingeben von Text des Konstruktors der `Derived`-Klasse wird der Konstruktor für die `Base`-Klasse (`Base::Base`) aufgerufen.  
  
 `Base::Base` ruft die `f`-Funktion auf, bei der es sich um eine virtuelle Funktion handelt. Normalerweise würde `Derived::f` aufgerufen, da das Objekt `d` vom Typ `Derived` ist. Da es sich bei der `Base::Base`-Funktion um einen Konstruktor handelt, ist das Objekt noch nicht vom Typ `Derived`, und `Base::f` wird aufgerufen.  
  
