---
title: Werttypen (Modern C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f63bb62c-60da-40d5-ac14-4366608fe260
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e7e49c97bca86b8d2debde2f5b132f7dde16998e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="value-types-modern-c"></a>Werttypen (Modern C++)
C++-Klassen sind standardmäßig Werttypen. Dieses Thema enthält einführenden Überblick Werttypen und Probleme im Zusammenhang mit Verwendungsbeispielen.  
  
## <a name="value-vs-reference-types"></a>Wert im Vergleich zu Verweistypen  
 Wie bereits erwähnt, C++-Klassen standardmäßig Werttypen sind. Sie können als Verweistypen, angegeben werden, sodass objektorientierte Programmierung polymorphes Verhalten zu unterstützen. Werttypen werden manchmal aus der Perspektive des Speichers und das Layout-Steuerelement angezeigt, wohingegen Verweistypen zu Basisklassen und virtuelle Funktionen für die polymorphe verwendet werden. Standardmäßig sind Werttypen kopiert, was bedeutet, dass stets einen Kopierkonstruktor und ein Kopierzuweisungsoperator vorhanden ist. Für Verweistypen, Sie machen die Klasse nicht kopierbare (deaktivieren Sie den Kopierkonstruktor und der Kopierzuweisungsoperator), und verwenden Sie einen virtuellen Destruktor, der ihren beabsichtigten Polymorphie unterstützt. Werttypen sind auch über die Inhalte, die, wenn sie kopiert werden, immer Sie zwei unabhängige Werte zugewiesen werden, die getrennt geändert werden können. Verweistypen sind im Begriff Identity – welche Art von Objekt es ist? Aus diesem Grund "Referenztypen" werden auch als "polymorphen Typen" bezeichnet.  
  
 Wenn Sie wirklich ein Referenz-ähnliche (Basisklasse, virtuelle Funktionen) möchten, müssen Sie explizit zu deaktivieren, kopieren, entsprechend der `MyRefType` Klasse im folgenden Code.  
  
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
  
## <a name="value-types-and-move-efficiency"></a>Werttypen und Effizienz verschieben  
 Kopie Zuordnungsaufwand ist aufgrund von Optimierungen für neue vermieden. Z. B. Wenn Sie eine Zeichenfolge in der Mitte einen Vektor von Zeichenfolgen einfügen, wird keine Kopie erneute Zuordnung Mehraufwand, nur eine Move - selbst wenn dies zu einem Grow des Vektors selbst führt. Dies gilt auch für andere Vorgänge, z. B. Ausführen eines Hinzufügevorgangs "auf zwei sehr große Objekte. Wie wird aktiviert dieser Wert Vorgang Optimierungen? In einigen C++-Compiler wird der Compiler dies für Sie implizit aktiviert ähnlich wie Kopierkonstruktoren automatisch vom Compiler generiert werden können. Allerdings in Visual C++ müssen Ihre Klasse "abonnierbare" um Zuweisung und Konstruktoren zu verschieben, indem Sie es in der Klasse deklarieren. Dies erfolgt mithilfe der doppelten kaufmännisches und-Zeichens (& &) Rvalue-Verweis in das entsprechende Element Funktion Deklarationen und definierenden bewegungskonstruktor und Zuweisung Methoden zu verschieben.  Sie müssen auch den richtigen Code aus dem Quellobjekt zu "das wesentliche stehlen" einfügen.  
  
 Wie entscheiden Sie, wenn Sie verschieben müssen aktiviert? Wenn Sie bereits, dass Sie zur Erstellung aktiviert kopieren müssen wissen, möchten Sie möglicherweise aktiviert verschieben, wenn es billiger als eine tiefe Kopie sein kann. Jedoch, wenn Sie, dass Sie Support verschieben müssen wissen, es unbedingt bedeutet nicht, dass kopieren, die aktiviert werden soll. Diese letzteren Fall würde eine "reine verschieben Type" aufgerufen werden. Ein Beispiel für bereits in der Standardbibliothek ist `unique_ptr`. Nebenbei bemerkt, die alte `auto_ptr` ist veraltet und wurde ersetzt durch `unique_ptr` genau aufgrund eines fehlenden Move-Semantik-Unterstützung in der vorherigen Version von C++.  
  
 Durch Verwendung der Verschiebesemantik können Sie vom Rückgabewert oder Insert in Middle. Verschieben ist eine Optimierung der Kopie. Ist erforderlich für Heapzuordnung dieses Problem zu umgehen. Betrachten Sie den folgenden Pseudocode:  
  
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
  
### <a name="enabling-move-for-appropriate-value-types"></a>Aktivieren für den entsprechenden Werttypen verschieben  
 Für eine Wert-ähnliche-Klasse, wobei verschieben günstiger als eine tiefe Kopie sein kann, verschiebungskonstruktion aktivieren und Effizienzgründen verschiebezuweisung verarbeitet. Betrachten Sie den folgenden Pseudocode:  
  
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
  
 Wenn Sie die Kopie nachrichtenerstellung/-Zuweisung aktivieren, können auch aktivieren Sie verschieben nachrichtenerstellung/-Zuweisung, wenn es billiger als eine tiefe Kopie sein kann.  
  
 Einige *kein Werttyp* Typen sind nur verschoben, z. B. Wenn Sie eine Ressource, die nur den Besitz übertragen klonen können nicht. Beispiel: `unique_ptr`  
  
## <a name="section"></a>Bereich  
 Inhalt  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Typsystem](../cpp/cpp-type-system-modern-cpp.md)   
 [Willkommen zurück bei C++](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)