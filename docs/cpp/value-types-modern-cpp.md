---
title: C++-Klassen als Werttypen
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: f63bb62c-60da-40d5-ac14-4366608fe260
ms.openlocfilehash: 1aabcad46e848e1a499a142adaba5002a829bbf5
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246022"
---
# <a name="c-classes-as-value-types"></a>C++-Klassen als Werttypen

C++Klassen sind Standard Werttypen. Sie können als Verweis Typen angegeben werden, die das polymorphe Verhalten zur Unterstützung der objektorientierten Programmierung ermöglichen. Werttypen werden manchmal aus der Perspektive der Arbeitsspeicher-und Layoutsteuerung angezeigt, während Verweis Typen auf Basisklassen und virtuelle Funktionen für polymorphe Zwecke basieren. Standardmäßig sind Werttypen copyable, was bedeutet, dass immer ein Kopierkonstruktor und ein Kopier Zuweisungs Operator vorhanden sind. Für Verweis Typen machen Sie die Klasse als nicht Kopier fähig (deaktivieren Sie den Kopierkonstruktor und den Kopier Zuweisungs Operator) und verwenden einen virtuellen Dekonstruktor, der die gewünschte Polymorphie unterstützt. Bei Werttypen geht es auch um die Inhalte, die beim Kopieren immer zwei unabhängige Werte erhalten, die separat geändert werden können. Referenztypen sind Informationen über die Identität: welche Art von Objekt ist Sie? Aus diesem Grund werden "Verweis Typen" auch als "polymorphe Typen" bezeichnet.

Wenn Sie einen Verweis ähnlichen Typ (Basisklasse, virtuelle Funktionen) wirklich wünschen, müssen Sie das Kopieren explizit deaktivieren, wie in der `MyRefType`-Klasse im folgenden Code gezeigt.

```cpp
// cl /EHsc /nologo /W4

class MyRefType {
private:
    MyRefType & operator=(const MyRefType &);
    MyRefType(const MyRefType &);
public:
    MyRefType () {}
};

int main()
{
    MyRefType Data1, Data2;
    // ...
    Data1 = Data2;
}
```

Das Kompilieren des obigen Codes führt zu folgendem Fehler:

```Output
test.cpp(15) : error C2248: 'MyRefType::operator =' : cannot access private member declared in class 'MyRefType'
        meow.cpp(5) : see declaration of 'MyRefType::operator ='
        meow.cpp(3) : see declaration of 'MyRefType'
```

## <a name="value-types-and-move-efficiency"></a>Werttypen und Verschiebungs Effizienz

Der Aufwand für die Kopier Zuweisung wird aufgrund neuer Kopier Optimierungen vermieden. Wenn Sie z. b. eine Zeichenfolge in der Mitte eines Vektor von Zeichen folgen einfügen, gibt es keinen mehr Aufwand für die erneute Zuordnung von Kopier Vorgängen, sondern nur für eine Verschiebung, auch wenn der Vektor selbst vergrößert wird. Dies gilt auch für andere Vorgänge, z.b. für das Ausführen eines Add-Vorgangs für zwei sehr große Objekte. Wie können Sie diese Wert Vorgangs Optimierungen aktivieren? Bei einigen C++ Compilern aktiviert der Compiler dies implizit, ähnlich wie Kopierkonstruktoren können vom Compiler automatisch generiert werden. In C++muss Ihre Klasse jedoch "abonnieren", um Zuweisungen und Konstruktoren zu verschieben, indem Sie Sie in der Klassendefinition deklarieren. Dies wird erreicht, indem der rvalue-Verweis "Double-and (& &)" in den entsprechenden Deklarationen der Element Funktion und das Definieren von bewegungskonstruktoren und Verschiebungs Zuweisungs Methoden verwendet werden.  Außerdem müssen Sie den richtigen Code einfügen, um den Grund für das Quell Objekt zu "stehlen".

Wie entscheiden Sie, ob die Verschiebung aktiviert werden muss? Wenn Sie bereits wissen, dass die Kopier Erstellung aktiviert sein muss, ist es wahrscheinlich, dass das verschieben aktiviert ist, wenn es günstiger als eine tiefe Kopie sein kann. Wenn Sie jedoch wissen, dass Sie Unterstützung benötigen, bedeutet dies nicht unbedingt, dass das Kopieren aktiviert werden soll. Der letztere Fall würde als "Move-only Type" bezeichnet werden. Ein Beispiel, das bereits in der Standardbibliothek vorhanden ist, ist `unique_ptr`. Als neben Hinweis ist die alte `auto_ptr` veraltet und wurde durch `unique_ptr` genau aufgrund der fehlenden Unterstützung der Verschiebungs Semantik in der vorherigen Version von C++ersetzt.

Mithilfe von Verschiebungs Semantik können Sie eine Rückgabe nach Wert oder INSERT-in-Middle durchführen. Move ist eine Optimierung der Kopie. Es ist eine Heap Zuordnung erforderlich, um eine Problem Umgehung zu umgehen. Betrachten Sie den folgenden Pseudocode:

```cpp
#include <set>
#include <vector>
#include <string>
using namespace std;

//...
set<widget> LoadHugeData() {
    set<widget> ret;
    // ... load data from disk and populate ret
    return ret;
}
//...
widgets = LoadHugeData();   // efficient, no deep copy

vector<string> v = IfIHadAMillionStrings();
v.insert( begin(v)+v.size()/2, "scott" );   // efficient, no deep copy-shuffle
v.insert( begin(v)+v.size()/2, "Andrei" );  // (just 1M ptr/len assignments)
//...
HugeMatrix operator+(const HugeMatrix& , const HugeMatrix& );
HugeMatrix operator+(const HugeMatrix& ,       HugeMatrix&&);
HugeMatrix operator+(      HugeMatrix&&, const HugeMatrix& );
HugeMatrix operator+(      HugeMatrix&&,       HugeMatrix&&);
//...
hm5 = hm1+hm2+hm3+hm4+hm5;   // efficient, no extra copies
```

### <a name="enabling-move-for-appropriate-value-types"></a>Aktivieren von Move für geeignete Werttypen

Für eine Wert ähnliche Klasse, bei der die Verschiebung günstiger als eine tiefe Kopie sein kann, aktivieren Sie die Verschiebungs Konstruktion und die Verschiebungs Zuweisung. Betrachten Sie den folgenden Pseudocode:

```cpp
#include <memory>
#include <stdexcept>
using namespace std;
// ...
class my_class {
    unique_ptr<BigHugeData> data;
public:
    my_class( my_class&& other )   // move construction
        : data( move( other.data ) ) { }
    my_class& operator=( my_class&& other )   // move assignment
    { data = move( other.data ); return *this; }
    // ...
    void method() {   // check (if appropriate)
        if( !data )
            throw std::runtime_error("RUNTIME ERROR: Insufficient resources!");
    }
};
```

Wenn Sie die Kopier Konstruktion/-Zuweisung aktivieren, aktivieren Sie auch die Option zum Verschieben von Konstruktion/Zuweisung, wenn diese günstiger als eine tiefe Kopie sein kann.

Einige *nicht-Werttypen* sind nur Verschiebe Vorgang, z. b. Wenn Sie keine Ressource Klonen können, sondern nur den Besitz übertragen. Beispiel: `unique_ptr`

## <a name="see-also"></a>Siehe auch

[C++Typsystem](../cpp/cpp-type-system-modern-cpp.md)<br/>
[Willkommen zurück beiC++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)
