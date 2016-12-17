---
title: "Werttypen (Modern C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: f63bb62c-60da-40d5-ac14-4366608fe260
caps.latest.revision: 15
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Werttypen (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+\-Klassen sind standardmäßig Werttypen.  Dieses Thema bietet eine Einführung Übersicht von Werttypen und Problemen in Bezug auf ihre Verwendung bereit.  
  
## Wert auf Verweistypen  
 Wie bereits erwähnt C\+\+\-Klassen sind standardmäßig Werttypen.  Sie können als Referenztypen angegeben werden, die Unterstützung Verhalten ermöglichen, objektorientierte Programmierung.  Werttypen werden manchmal aus Sicht des Arbeitsspeichers und eines Layoutsteuerelements angezeigt, während Referenztypen zu Basisklassen und virtuelle Funktionen zu den polymorphen Zwecke sind.  Standardmäßig sind Werttypen kopierbar, das bedeutet, dass es immer einen Kopierkonstruktor und ein Kopierzuweisungsoperator gibt.  Bei Verweistypen legen Sie die Klasse nicht\-\-copyable \(deaktivieren Sie den Kopierkonstruktor und den Kopierzuweisungsoperator\) und verwenden einen virtuellen Destruktor, wodurch ihre beabsichtigte Polymorphie unterstützt.  Werttypen können auch über den Inhalt, die, falls sie kopiert werden, haben Sie zwei unabhängige Werte immer geben, die separat bearbeitet werden können.  Referenztypen sind über Identität \- was ist Art von Objekt es?  Aus diesem Grund "" Verweistypen werden auch als "polymorphe Typen".  
  
 Wenn Sie einen Verweis ähnlichen Typ \(Basisklasse, virtuelle Funktionen\) möchten, müssen Sie das Kopieren, wie in der `MyRefType`\-Klasse im folgenden Code gezeigt explizit deaktivieren.  
  
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
  
 Das Kompilieren des obigen Code erzeugt den folgenden Fehler:  
  
  **test.cpp \(15\): Fehler C2248: "MyRefType::operator \=": kann das private Member zugreifen, die deklariert wird im MyRefType der Klasse"**  
 **meow.cpp \(5\): finden Deklaration von "MyRefType::operator \="**  
 **meow.cpp \(3\): finden Deklaration von "MyRefType"**   
## Werttypen und Verschiebungseffizienz  
 Kopienzuordnungsmehraufwand wird durch die neue Kopienoptimierungen vermieden.  Wenn Sie eine Zeichenfolge in der Mitte einem Vektor aus Zeichenfolgen einfügen, ist kein Kopienneuzuordnungsmehraufwand, nur eine Bewegung, selbst wenn ein Wachsung des Vektors selbst führt.  Dies gilt auch für andere Vorgänge auf und beispielsweise führt einen Hinzufügen auf zwei sehr großen Objekten aus.  Wie können Sie diese Wertvorgangsoptimierungen?  In einigen C\+\+\-Compilern aktiviert der Compiler dies für Sie implizit, ähnlich Kopierkonstruktoren kann der Compiler automatisch generiert werden.  In Visual C\+\+, muss die Klasse "abonnieren", um die Zuweisung als Konstruktoren zu verschieben, indem sie sie in der Klassendefinition deklariert.  Dies wird erreicht, indem die doppelten rvalu\-Verweis des kaufmännischen Und\-Zeichens \(&&\) in den entsprechenden Memberfunktionsdeklarationen verwendet und Verschiebungskonstruktor\- und Verschiebungszuweisungsmethoden definiert.  Sie müssen auch den korrekten Code einfügen "stehlen die Eingeweide" aus dem Quellobjekt heraus.  
  
 Wie entscheiden Sie, wenn die aktivierte Verschiebung müssen?  Wenn Sie bereits wissen, benötigen Sie die Kopienkonstruktion, die, wie Sie möchten aktiviert ist wahrscheinlich, die Verschiebung, die aktiviert wird, wenn sie als eine tiefe Kopie des s billiger sein kann.  Wenn Sie wissen, benötigen Sie Verschiebungsunterstützung, bedeutet dies nicht unbedingt, dass Sie die Kopie aktivierte soll.  Dieser letzte Fall würde einen "nur für Verschiebung Typ" aufgerufen.  Ein Beispiel bereits in der Standardbibliothek ist `unique_ptr`.  Als Randbemerkung wird das alte `auto_ptr` veraltet und wurde durch `unique_ptr` genau aufgrund der Sache Verschiebesemantikunterstützung in der Vorgängerversion von C\+\+ ersetzt.  
  
 Mithilfe Verschiebesemantik verwenden, können Sie EINGABETASTE\-durchWert oder EINFG\-in\-mittleres.  Verschiebung ist eine Optimierung der Kopie.  Es gibt für Anforderung Heapreservierung als Problemumgehung.  Betrachten Sie folgenden Pseudocode:  
  
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
  
### Aktivieren der Umsetzung für entsprechende Werttypen  
 Bei Wert eine ähnliche Klasse, in der Verschiebung als eine tiefe Kopie des s billiger sein kann, Verschiebungskonstruktion und Verschiebungszuweisung für Effizienz aktivieren.  Betrachten Sie folgenden Pseudocode:  
  
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
  
 Wenn Sie Kopienkonstruktion\/\-Zuweisung aktivieren, aktivieren Sie auch Verschiebungskonstruktion\/\-Zuweisung, wenn sie als eine tiefe Kopie des s billiger sein kann.  
  
 Eine *NichtWerttypen* sind, wie nur für Bewegung, wenn Sie eine Ressource nicht klonen können, nur übertragen.  Beispiel: `unique_ptr`  
  
## Abschnitt  
 Inhalt  
  
## Siehe auch  
 [C\+\+\-Typsystem](../cpp/cpp-type-system-modern-cpp.md)   
 [Willkommen zurück bei C\+\+](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C\+\+\-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [C\+\+\-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)