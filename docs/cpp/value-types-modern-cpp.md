---
title: Werttypen (Modern C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: f63bb62c-60da-40d5-ac14-4366608fe260
ms.openlocfilehash: 32cdb29ec1c59081ad7e0493888f290f21561d2b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390905"
---
# <a name="value-types-modern-c"></a>Werttypen (Modern C++)

C++-Klassen sind standardmäßig Werttypen. Dieses Thema enthält eine einführende Übersicht über Werttypen und Probleme im Zusammenhang mit ihrer Verwendung.

## <a name="value-vs-reference-types"></a>Wert im Vergleich zu Verweistypen

Wie bereits erwähnt, C++-Klassen standardmäßig Werttypen sind. Sie können als Verweistypen, angegeben werden, sodass objektorientierte Programmierung polymorphes Verhalten zu unterstützen. Werttypen werden manchmal auch aus der Perspektive des Speichers und das Layout-Steuerelement angezeigt, während Verweistypen um Basisklassen und virtuelle Funktionen, die für die polymorphe verwendet werden. Standardmäßig sind Werttypen kopiert, was bedeutet, dass stets einen Kopierkonstruktor und ein Kopierzuweisungsoperator vorhanden ist. Für Verweistypen; Sie legen Sie die Klasse nicht kopierbar (Deaktivieren der Kopierkonstruktor und Kopierzuweisungsoperator) und verwenden Sie einen virtuellen Destruktor, die ihre gewünschten Polymorphismus unterstützt. Werttypen sind auch über die Inhalte, die, wenn sie kopiert werden, immer zwei unabhängige Werte erhalten Sie, die getrennt geändert werden kann. Verweistypen sind über Identity – welche Art von Objekt es ist? Aus diesem Grund "Verweistypen" werden auch als "polymorphen Typen" bezeichnet.

Wenn Sie wirklich einen Referenz-ähnlicher-Typ (Basisklasse, virtuelle Funktionen) möchten, müssen Sie explizit zu deaktivieren, kopieren, siehe die `MyRefType` Klasse in den folgenden Code.

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

Kompilieren des obigen Codes führt zu folgendem Fehler:

```Output
test.cpp(15) : error C2248: 'MyRefType::operator =' : cannot access private member declared in class 'MyRefType'
        meow.cpp(5) : see declaration of 'MyRefType::operator ='
        meow.cpp(3) : see declaration of 'MyRefType'
```

## <a name="value-types-and-move-efficiency"></a>Werttypen Sie und verschieben Sie die Effizienz

Zuordnungsaufwand für die Kopie wird aufgrund von Optimierungen für neue vermieden. Z. B. beim Einfügen einer Zeichenfolge in der Mitte einen Vektor von Zeichenfolgen stehen keine Kopie Neubelegung Mehraufwand, nur eine Move - selbst wenn dies zu einer Vergrößerung des Vektors selbst führt. Dies gilt auch für andere Vorgänge, z. B. Ausführen eines Hinzufügevorgangs "auf zwei sehr große Objekte zu finden. Wie aktivieren Sie diesen Wert Vorgang Optimierungen? In einige C++-Compiler wird der Compiler dies für Sie implizit ermöglichen ähnlich wie Kopierkonstruktoren automatisch vom Compiler generiert werden können. Allerdings in Visual C++ müssen die Klasse "abonnierbare" um Zuweisung und Konstruktoren zu verschieben, indem Sie es in der Klasse deklarieren. Dies erfolgt mithilfe der doppelten kaufmännisches und-Zeichens (& &) Rvalue-Verweis in den entsprechenden Member Funktionsdeklarationen und definierenden bewegungskonstruktor und Methoden für die Zuweisung zu verschieben.  Sie müssen auch den korrekten Code, die Grundlagen aus dem Quellobjekt "stehlen" einfügen.

Wie entscheiden Sie, wenn Sie verschieben müssen, aktiviert? Wenn Sie bereits, dass Sie die Erstellung aktiviert kopieren müssen wissen, sollten Sie aktiviert zu verschieben, wenn es günstiger sein als eine tiefe Kopie sein kann. Wenn Sie, dass Sie die Unterstützung verschieben müssen wissen, bedeutet jedoch nicht sie unbedingt, dass die Kopie, die aktiviert werden sollen. Der letzte Fall würde eine "nur zur Verschiebung Type" aufgerufen werden. Ein Beispiel für bereits in der Standardbibliothek ist `unique_ptr`. Nebenbei bemerkt, die alte `auto_ptr` ist veraltet und wurde durch ersetzt `unique_ptr` genau aufgrund des Mangels an Move-Semantik-Unterstützung in der vorherigen Version von C++.

Mithilfe der Verschiebesemantik können Sie Return-Wert oder Insert-Middle. Verschieben ist eine Optimierung der Kopie. Es ist erforderlich, für die Heapzuordnung dieses Problem zu umgehen. Betrachten Sie den folgenden Pseudocode:

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

### <a name="enabling-move-for-appropriate-value-types"></a>Aktivieren Schritt für den entsprechenden Werttypen

Aktivieren Sie für eine Wert-ähnliche-Klasse, die in der Verschiebung günstiger als eine tiefe Kopie sein kann verschiebungskonstruktion aus, und verschieben Sie Zuweisung für Effizienz zu. Betrachten Sie den folgenden Pseudocode:

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

Wenn Sie eine Kopie nachrichtenerstellung/-Zuweisung aktivieren, können auch aktivieren Sie verschieben nachrichtenerstellung/-Zuweisung, wenn es günstiger sein als eine tiefe Kopie sein kann.

Einige *ohne Wert* Typen sind nur zur Verschiebung, z. B. Wenn Sie eine Ressource, die nur die Übertragung des Besitzes klonen können nicht. Beispiel: `unique_ptr`

## <a name="section"></a>Abschnitt

Content

## <a name="see-also"></a>Siehe auch

[C++- Typsystem (Modern C++)](../cpp/cpp-type-system-modern-cpp.md)<br/>
[Willkommen zurück bei C++ (Modern C++)](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)<br/>
[C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)
