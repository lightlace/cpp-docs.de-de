---
title: "deque-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.deque"
  - "deque"
  - "std::deque"
  - "deque/std::deque"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Deque-Klasse Informationen über die Deque-Klasse"
  - "deque-Klasse"
ms.assetid: 64842ee5-057a-4063-8c16-4267a0332584
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# deque-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ordnet Elemente eines angegebenen Typs in einer linearen Anordnung an, und aktiviert, wie ein Vektor, schnellen zufälligen Zugriff auf jedes Element sowie effizientes Einfügen und Löschen auf der Rückseite des Containers. Im Gegensatz zu einem Vektor, unterstützt die `deque`-Klasse allerdings auch das effiziente Einfügen und Löschen im Vordergrund des Containers.  
  
## <a name="syntax"></a>Syntax  
  
```unstlib  
template <class Type,   
    class Allocator =allocator<Type>>  
class deque  
```  
  
#### <a name="parameters"></a>Parameter  
 `Type`  
 Der in der Doppelschlange zu speichernde Elementdatentyp.  
  
 `Allocator`  
 Der Typ, der das gespeicherte Zuordnungsobjekt darstellt, das Details zum Belegen und Freigeben des Arbeitsspeichers der Doppelschlange kapselt. Dieses Argument ist optional, und der Standardwert ist **Allocator \< Typ>***.*  
  
## <a name="remarks"></a>Hinweise  
 Die Auswahl des Containertyps sollte im Allgemeinen auf Grundlage des für die Anwendung erforderlichen Suchen und Einfügetyps erfolgen. [Vektoren](vector%20Class.md) sollte der bevorzugte Container zum Verwalten einer Sequenz, wenn zufälliger Zugriff auf jedes Element ist und einfügen oder Löschen von Elementen nur werden am Ende einer Sequenz erforderlich. Die Leistung des Containers Liste überlegen, wenn das effiziente Einfügen und löschen (in konstanter Zeit) an einer beliebigen Position innerhalb der Sequenz ist. Solche Vorgänge in der Mitte der Sequenz benötigen Elementkopien und -Zuweisungen, die zur Anzahl von Elementen in der Sequenz proportional sind (lineare Zeit).  
  
 Die Neuzuordnung von Doppelschlangen tritt auf, wenn Elemente der Sequenz von einer Memberfunktion eingefügt oder gelöscht werden müssen:  
  
-   Wenn ein Element in einer leeren Sequenz eingefügt wird oder wenn ein Element zum Verlassen einer leeren Sequenz gelöscht wird, dann Iteratoren zuvor vom zurückgegeben [beginnen](#deque__begin) und [End](#deque__end) ungültig.  
  
-   Wenn ein Element an der ersten Position der Doppelschlange eingefügt wird, werden anschließend alle Iteratoren, allerdings keine Verweise, die vorhandene Elemente festlegen, ungültig.  
  
-   Wenn ein Element am Ende der doppelschlange, anschließend eingefügt wird [End](#deque__end) und alle Iteratoren, allerdings keine Verweise, die vorhandene Elemente ungültig.  
  
-   Wenn ein Element im Vordergrund der Doppelschlange gelöscht wird, werden nur dieser Iterator und die Verweise auf das gelöschte Element ungültig.  
  
-   Wenn das letzte Element am Ende der Doppelschlange gelöscht wird, werden nur dieser Iterator am letzen Element und die Verweise auf das gelöschte Element ungültig.  
  
 Andernfalls werden alle Iteratoren und Verweise durch das Einfügen und Löschen eines Elements und ungültig.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[deque](#deque__deque)|Erstellt eine `deque.` mehrere Konstruktoren werden bereitgestellt, um den Inhalt der neuen `deque` auf verschiedene Arten: leer, mit einer angegebenen Anzahl leerer Elemente geladen, Inhalte verschoben oder kopiert, von einem anderen `deque`; Inhalt kopiert oder mithilfe eines Iterators verschoben und ein Element kopiert, in der `deque`` count` Zeiten. Einige der Konstruktoren ermöglichen die Verwendung eines benutzerdefinierten `allocator` zum Erstellen von Elementen.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[allocator_type](#deque__allocator_type)|Ein Typ, der die `allocator`-Klassentyp für das `deque`-Objekt darstellt.|  
|[const_iterator](#deque__const_iterator)|Ein Typ, der einen Iterator mit zufälligem Zugriff bereitstellt, mit dem auf Elemente in der `deque` als `const` zugegriffen, und mit dem diese Elemente gelesen werden können.|  
|[const_pointer](#deque__const_pointer)|Ein Typ, der einen Zeiger auf ein Element in einer `deque`-als `const.` bereitstellt.|  
|[const_reference](#deque__const_reference)|Ein Typ, der einen Verweis auf ein Element in einer `deque` zum Lesen und für andere Vorgänge als `const.` bereitstellt|  
|[const_reverse_iterator](#deque__const_reverse_iterator)|Ein Typ, der einen Iterator mit zufälligem Zugriff bereitstellt, mit dem auf Elemente in der `deque` als `const` zugegriffen, und mit dem diese Elemente gelesen werden können. Die Doppelschlange wird umgekehrt angezeigt. Weitere Informationen finden Sie unter [Reverse_iterator-Klasse](../standard-library/reverse-iterator-class.md)|  
|[difference_type](#deque__difference_type)|Ein Typ, der den Unterschied zwischen zwei Iteratoren mit zufälligem Zugriff, die auf Elemente in derselben `deque` verweisen, bereitstellt.|  
|[Iterator](#deque__iterator)|Ein Typ, der einen Iterator mit zufälligem Zugriff bereitstellt, mit dem jedes Element in einer `deque` gelesen oder geändert werden kann.|  
|[Zeiger](#deque__pointer)|Ein Typ, der einen Zeiger auf ein Element in einer `deque` bereitstellt.|  
|[Referenz](#deque__reference)|Ein Typ, der einen Verweis auf ein in einer `deque` gespeichertes Element bereitstellt.|  
|[reverse_iterator](#deque__reverse_iterator)|Ein Typ, der einen Iterator mit zufälligem Zugriff bereitstellt, mit dem ein Element in einer `deque` gelesen oder geändert werden kann. Die Doppelschlange wird in umgekehrter Reihenfolge angezeigt.|  
|[size_type](#deque__size_type)|Ein Typ, der die Anzahl von Elementen in einer `deque` zählt.|  
|[Werttyp](#deque__value_type)|Ein Typ, der den in einer `deque` gespeicherten Datentyp darstellt.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[Zuweisen](#deque__assign)|Löscht Elemente aus einer `deque` und kopiert eine neue Sequenz von Elementen in die Ziel-`deque`.|  
|[am](#deque__at)|Gibt einen Verweis auf das Element an einer angegebenen Position in der `deque` zurück.|  
|[Zurück](#deque__back)|Gibt einen Verweis auf das letzte Element der `deque` zurück.|  
|[beginnen](#deque__begin)|Gibt ein Iterator mit zufälligem Zugriff zurück, der das erste Element in der `deque` adressiert.|  
|[deque:: cbegin](#deque__cbegin)|Gibt einen const-Iterator auf das erste Element im `deque`-Objekt zurück.|  
|[deque:: cend](#deque__cend)|Gibt einen `const`-Iterator mit zufälligem Zugriff zurück, der auf eine Position unmittelbar nach dem Ende der `deque` verweist.|  
|[Deaktivieren](#deque__clear)|Löscht alle Elemente einer `deque` auf.|  
|[deque:: crbegin](#deque__crbegin)|Gibt einen direkten const-Iterator mit zufälligem Zugriff zum ersten Element in der `deque` zurück, das in umgekehrter Reihenfolge angezeigt wird.|  
|[deque:: crend](#deque__crend)|Gibt einen direkten const-Iterator mit zufälligem Zugriff zum ersten Element in der `deque` zurück, das in umgekehrter Reihenfolge angezeigt wird.|  
|[deque:: emplace](#deque__emplace)|Fügt ein direkt konstruiertes Element an einer angegebenen Position in die `deque` ein.|  
|[deque:: emplace_back](#deque__emplace_back)|Fügt ein direkt konstruiertes Element am Ende der `deque` ein.|  
|[deque:: emplace_front](#deque__emplace_front)|Fügt ein direkt konstruiertes Element am Anfang der `deque` ein.|  
|[leere](#deque__empty)|Gibt `true` zurück, wenn `deque` keine Elemente enthält, und gibt `false` zurück, wenn mindestens ein Element enthält.|  
|[Ende](#deque__end)|Gibt einen Iterator mit zufälligem Zugriff zurück, der auf eine Position unmittelbar nach dem Ende der `deque` verweist.|  
|[zum Löschen des Bands](#deque__erase)|Entfernt ein Element oder eine Reihe von Elementen in einer `deque` aus angegebenen Speicherorten.|  
|[Vorderseite](#deque__front)|Gibt einen Verweis auf das erste Element in einer `deque` zurück.|  
|[get_allocator](#deque__get_allocator)|Gibt eine Kopie des zum Erstellen der `allocator` verwendeten `deque`-Objekts zurück.|  
|[Einfügen](#deque__insert)|Fügt ein Element, mehrere Elemente oder einen Reihe von Elementen an einer angegebenen Position in die `deque` ein.|  
|[max_size](#deque__max_size)|Gibt die mögliche Maximallänge der `deque` zurück.|  
|[pop_back](#deque__pop_back)|Löscht das Element am Ende der `deque`.|  
|[pop_front](#deque__pop_front)|Löscht das Element am Anfang der `deque`.|  
|[push_back](#deque__push_back)|Fügt am Ende der `deque` ein Element hinzu.|  
|[push_front](#deque__push_front)|Fügt am Anfang der `deque` ein Element hinzu.|  
|[rbegin](#deque__rbegin)|Gibt dem ersten Element einen Iterator mit zufälligem Zugriff in umgekehrter `deque` zurück.|  
|[REND](#deque__rend)|Gibt einen Iterator mit zufälligem Zugriff zurück, der grade über das letzte Element in einer umgekehrten `deque` zeigt.|  
|[Ändern der Größe](#deque__resize)|Gibt eine neue Größe für eine `deque` an.|  
|[deque:: shrink_to_fit](#deque__shrink_to_fit)|Verwirft Überkapazität.|  
|[Größe](#deque__size)|Gibt die Anzahl von Elementen in der `deque` zurück.|  
|[Swap](#deque__swap)|Tauscht die Elemente zweier `deque`n.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator &#91; &#93;](#deque__operator_at)|Gibt einen Verweis auf das `deque`-Element an einer angegebenen Position zurück.|  
|[deque:: Operator =](#deque__operator_eq)|Ersetzt die Elemente der `deque` mit einer Kopie einer anderen `deque`.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header**: \< doppelschlange>  
  
##  <a name="a-namedequeallocatortypea-dequeallocatortype"></a><a name="deque__allocator_type"></a>  deque:: allocator_type  
 Ein Typ, der die zuweisungsklasse für das Deque-Objekt darstellt.  
  
```  
typedef Allocator allocator_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 **Allocator_type** ist ein Synonym für den Vorlagenparameter **Zuweisung**.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Get_allocator](#deque__get_allocator).  
  
##  <a name="a-namedequeassigna-dequeassign"></a><a name="deque__assign"></a>  deque:: Assign  
 Löscht Elemente aus einer Doppelschlange und kopiert einen neuen Satz von Elementen in die Zieldoppelschlange.  
  
```  
template <class InputIterator>  
void assign(
    InputIterator First,  
    InputIterator Last);

void assign(
    size_type Count,  
    const Type& Val);

void assign(
    initializer_list<Type>  
IList);
```  
  
### <a name="parameters"></a>Parameter  
 `First`  
 Die Position des ersten Elements in dem aus der Argumentdoppelschlange zu kopierenden Elementbereich.  
  
 `Last`  
 Die Position des ersten Elements hinter dem aus der Argumentdoppelschlange zu kopierenden Elementbereich.  
  
 `Count`  
 Die Anzahl von Kopien eines Elements, das in die Doppelschlange eingefügt wird.  
  
 `Val`  
 Der Wert des Elements, das in die Doppelschlange eingefügt wird.  
  
 `IList`  
 Das initializer_list-Element, das in die Doppelschlange eingefügt wird.  
  
### <a name="remarks"></a>Hinweise  
 Nachdem alle vorhandenen Elemente in der Zieldoppelschlange gelöscht sind, wird von `assign` entweder ein angegebener Elementbereich aus der ursprünglichen oder einer anderen Doppelschlange in die Zieldoppelschlange eingefügt, oder es werden Kopien eines neuen Elements eines angegebenen Werts in die Zieldoppelschlange eingefügt.  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_assign.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
#include <initializer_list>  
  
int main()  
{  
    using namespace std;  
    deque <int> c1, c2;  
    deque <int>::const_iterator cIter;  
  
    c1.push_back(10);  
    c1.push_back(20);  
    c1.push_back(30);  
    c2.push_back(40);  
    c2.push_back(50);  
    c2.push_back(60);  
  
    deque<int> d1{ 1, 2, 3, 4 };  
    initializer_list<int> iList{ 5, 6, 7, 8 };  
    d1.assign(iList);  
  
    cout << "d1 = ";  
    for (int i : d1)  
        cout << i;  
    cout << endl;  
  
    cout << "c1 =";  
    for (int i : c1)  
        cout << i;  
    cout << endl;  
  
    c1.assign(++c2.begin(), c2.end());  
    cout << "c1 =";  
    for (int i : c1)  
        cout << i;  
    cout << endl;  
  
    c1.assign(7, 4);  
    cout << "c1 =";  
    for (int i : c1)  
        cout << i;  
    cout << endl;  
  
}  
  
```  
  
```Output  
d1 = 5678c1 =102030c1 =5060c1 =4444444  
```  
  
##  <a name="a-namedequeata-dequeat"></a><a name="deque__at"></a>  deque:: at  
 Gibt einen Verweis auf das Element an einer angegebenen Position in der doppelschlange zurück.  
  
```  
reference at(size_type _Pos);

const_reference at(size_type _Pos) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Pos`  
 Der Feldindex oder Positionsnummer des Elements auf in der doppelschlange zu verweisen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn `_Pos` ist größer als die Größe der doppelschlange **an** löst eine Ausnahme aus.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Rückgabewert der **am** zugewiesen ist eine `const_reference`, Deque-Objekt kann nicht geändert werden. Wenn der Rückgabewert der **am** zugewiesen ist eine **Verweis**, Deque-Objekt geändert werden kann.  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_at.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
  
   const int& i = c1.at( 0 );  
   int& j = c1.at( 1 );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namedequebacka-dequeback"></a><a name="deque__back"></a>  deque:: Back  
 Gibt einen Verweis auf das letzte Element der doppelschlange.  
  
```  
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das letzte Element der doppelschlange. Wenn die doppelschlange leer ist, ist der Rückgabewert nicht definiert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Rückgabewert von **wieder** zugewiesen ist eine `const_reference`, Deque-Objekt kann nicht geändert werden. Wenn der Rückgabewert von **wieder** zugewiesen ist eine **Verweis**, Deque-Objekt geändert werden kann.  
  
 Beim Kompilieren mit _SECURE_SCL 1 wird ein Laufzeitfehler auftreten, wenn Sie versuchen, ein Element in eine leere doppelschlange zuzugreifen.  Weitere Informationen finden Sie unter [Checked Iterators](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_back.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 11 );  
  
   int& i = c1.back( );  
   const int& ii = c1.front( );  
  
   cout << "The last integer of c1 is " << i << endl;  
   i--;  
   cout << "The next-to-last integer of c1 is " << ii << endl;  
}  
```  
  
```Output  
The last integer of c1 is 11  
The next-to-last integer of c1 is 10  
```  
  
##  <a name="a-namedequebegina-dequebegin"></a><a name="deque__begin"></a>  deque:: begin  
 Gibt einen Iterator, der das erste Element in der doppelschlange zurück.  
  
```  
const_iterator begin() const;

iterator begin();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator mit zufälligem Zugriff das erste Element in der doppelschlange oder den Speicherort adressiert, eine leere doppelschlange adressiert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Rückgabewert von **beginnen** zugewiesen ist eine `const_iterator`, Deque-Objekt kann nicht geändert werden. Wenn der Rückgabewert von **beginnen** zugewiesen ist ein **Iterator**, kann die Deque-Objekt geändert werden.  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_begin.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::iterator c1_Iter;  
   deque <int>::const_iterator c1_cIter;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
  
   c1_Iter = c1.begin( );  
   cout << "The first element of c1 is " << *c1_Iter << endl;  
  
 *c1_Iter = 20;  
   c1_Iter = c1.begin( );  
   cout << "The first element of c1 is now " << *c1_Iter << endl;  
  
   // The following line would be an error because iterator is const  
   // *c1_cIter = 200;  
}  
```  
  
```Output  
The first element of c1 is 1  
The first element of c1 is now 20  
```  
  
##  <a name="a-namedequecbegina-dequecbegin"></a><a name="deque__cbegin"></a>  deque:: cbegin  
 Gibt einen `const`-Iterator zurück, mit dem das erste Element im Bereich behandelt wird.  
  
```  
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `const`-Random-Access-Iterator, der auf das erste Element des Bereichs zeigt oder die Position direkt hinter dem Ende eines leeren Bereichs (für einen leeren Bereich gilt `cbegin() == cend()`).  
  
### <a name="remarks"></a>Hinweise  
 Bei dem Rückgabewert `cbegin` können die Elemente im Bereich nicht geändert werden.  
  
 Sie können diese Memberfunktion anstelle der `begin()`-Memberfunktion verwenden, um sicherzustellen, dass der Rückgabewert `const_iterator` ist. In der Regel in Verbindung mit verwendet die [Auto](../cpp/auto-cpp.md) typableitungsschlüsselwort, wie im folgenden Beispiel gezeigt. Im Beispiel sollten Sie `Container` Ein änderbarer (nicht `const`) Container jeder Art, die unterstützt `begin()` und `cbegin()`.  
  
```cpp  
 
auto i1 = Container.begin();
// i1 is Container<T>::iterator   
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator  
```  
  
##  <a name="a-namedequecenda-dequecend"></a><a name="deque__cend"></a>  deque:: cend  
 Gibt einen `const`-Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines Bereichs unmittelbar nachfolgt.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Random-Access-Iterator, der auf eine Position unmittelbar nach dem Ende des Bereichs verweist.  
  
### <a name="remarks"></a>Hinweise  
 `cend` wird verwendet, um zu testen, ob ein Iterator das Ende seines Bereichs übergeben hat.  
  
 Sie können diese Memberfunktion anstelle der `end()`-Memberfunktion verwenden, um sicherzustellen, dass der Rückgabewert `const_iterator` ist. In der Regel in Verbindung mit verwendet die [Auto](../cpp/auto-cpp.md) typableitungsschlüsselwort, wie im folgenden Beispiel gezeigt. Im Beispiel sollten Sie `Container` Ein änderbarer (nicht `const`) Container jeder Art, die unterstützt `end()` und `cend()`.  
  
```cpp  
 
auto i1 = Container.end();
// i1 is Container<T>::iterator   
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator  
```  
  
 Der von `cend` zurückgegebene Wert darf nicht dereferenziert werden.  
  
##  <a name="a-namedequecleara-dequeclear"></a><a name="deque__clear"></a>  deque:: Clear  
 Löscht alle Elemente einer doppelschlange.  
  
```  
void clear();
```  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_clear.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   cout << "The size of the deque is initially " << c1.size( ) << endl;  
   c1.clear( );  
   cout << "The size of the deque after clearing is " << c1.size( ) << endl;  
}  
```  
  
```Output  
The size of the deque is initially 3  
The size of the deque after clearing is 0  
```  
  
##  <a name="a-namedequeconstiteratora-dequeconstiterator"></a><a name="deque__const_iterator"></a>  deque:: const_iterator  
 Eine Typ, der einem Iterator mit zufälligem Zugriff bereitstellt, zugreifen kann, und Lesen einer **const** Element in der doppelschlange.  
  
```  
typedef implementation-defined const_iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Ein `const_iterator`-Typ kann nicht zum Ändern des Werts eines Elements verwendet werden.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [wieder](#deque__back).  
  
##  <a name="a-namedequeconstpointera-dequeconstpointer"></a><a name="deque__const_pointer"></a>  deque:: const_pointer  
 Stellt einen Zeiger auf ein `const`-Element in einer Doppelschlange bereit.  
  
```unstlib  
typedef typename Allocator::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>Hinweise  
 Ein `const_pointer`-Typ kann nicht zum Ändern des Werts eines Elements verwendet werden. Ein [Iterator](#deque__iterator) wird häufiger für den Zugriff auf ein doppelschlangenelement verwendet.  
  
##  <a name="a-namedequeconstreferencea-dequeconstreference"></a><a name="deque__const_reference"></a>  deque:: const_reference  
 Ein Typ, der einen Verweis auf eine **const** in einer doppelschlange zum Lesen und Ausführen von gespeicherten Elements **const** Vorgänge.  
  
```  
typedef typename Allocator::const_reference const_reference;  
```  
  
### <a name="remarks"></a>Hinweise  
 Ein `const_reference`-Typ kann nicht zum Ändern des Werts eines Elements verwendet werden.  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_const_ref.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
  
   const deque <int> c2 = c1;  
   const int &i = c2.front( );  
   const int &j = c2.back( );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
  
   // The following line would cause an error as c2 is const  
   // c2.push_back( 30 );  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namedequeconstreverseiteratora-dequeconstreverseiterator"></a><a name="deque__const_reverse_iterator"></a>  deque:: const_reverse_iterator  
 Eine Typ, der einem Iterator mit wahlfreiem Zugriff, können bietet gelesen **const** Element in der doppelschlange.  
  
```  
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Ein `const_reverse_iterator` kann nicht den Wert eines Elements ändern und wird verwendet, um die doppelschlange in umgekehrter Reihenfolge durchlaufen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Rbegin](#deque__rbegin) für ein Beispiel für das Deklarieren und verwenden einen Iterator.  
  
##  <a name="a-namedequecrbegina-dequecrbegin"></a><a name="deque__crbegin"></a>  deque:: crbegin  
 Gibt einen const-Iterator an das erste Element in einer umgekehrten Deque zurück.  
  
```  
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Const reverse-Iterator mit wahlfreiem Zugriff das erste Element in einer umgekehrten adressiert [Deque](../standard-library/deque-class.md) oder nach dem letzten Element in der nicht umgekehrten adressiert `deque`.  
  
### <a name="remarks"></a>Hinweise  
 Bei dem Rückgabewert von `crbegin` kann das `deque`-Objekt nicht geändert werden.  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_crbegin.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
   deque <int>::iterator v1_Iter;  
   deque <int>::const_reverse_iterator v1_rIter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   v1_Iter = v1.begin( );  
   cout << "The first element of deque is "  
        << *v1_Iter << "." << endl;  
  
   v1_rIter = v1.crbegin( );  
   cout << "The first element of the reversed deque is "  
        << *v1_rIter << "." << endl;  
}  
```  
  
```Output  
The first element of deque is 1.  
The first element of the reversed deque is 2.  
```  
  
##  <a name="a-namedequecrenda-dequecrend"></a><a name="deque__crend"></a>  deque:: crend  
 Gibt einen const-Iterator, der den Speicherort adressiert, das letzte Element in einer umgekehrten Deque adressiert.  
  
```  
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Const reverse-Iterator mit wahlfreiem Zugriff, der den Speicherort adressiert, das letzte Element in einer umgekehrten adressiert [Deque](../standard-library/deque-class.md) (der Speicherort, der das erste Element in der nicht umgekehrten Deque vorangegangen war).  
  
### <a name="remarks"></a>Hinweise  
 `crend` wird verwendet, mit einer umgekehrten `deque` wie [array::cend](../standard-library/array-class-stl.md#array__cend) wird verwendet, mit einer `deque`.  
  
 Mit dem Rückgabewert der `crend` (entsprechend dekrementiert), die `deque` -Objekt nicht geändert werden.  
  
 `crend` kann verwendet werden, um zu testen, ob ein reverse-Iterator am Ende der doppelschlange erreicht wurde.  
  
 Der von `crend` zurückgegebene Wert darf nicht dereferenziert werden.  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_crend.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
   deque <int>::const_reverse_iterator v1_rIter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   for ( v1_rIter = v1.rbegin( ) ; v1_rIter != v1.rend( ) ; v1_rIter++ )  
      cout << *v1_rIter << endl;  
}  
```  
  
```Output  
2  
1  
```  
  
##  <a name="a-namedequedequea-dequedeque"></a><a name="deque__deque"></a>  deque:: deque  
 Die Anzahl von Elementen in der erstellten Liste.  
  
```  
deque();

explicit deque(
    const Allocator& Al);

explicit deque(
    size_type Count);

deque(
    size_type Count,  
    const Type& Val);

deque(
    size_type Count,  
    const Type& Val,  
    const Allocator& Al);

deque(
    const deque& Right);

template <class InputIterator>  
deque(
 InputIterator First,  
    InputIterator Last);

template <class InputIterator>  
deque(
 InputIterator First,  
    InputIterator Last,  
    const Allocator& Al);

deque(
    initializer_list<value_type>  
IList,  
    const Allocator& Al);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|`Al`|Die mit diesem Objekt zu verwendende Zuweisungsklasse.|  
|`Count`|Die Anzahl von Elementen in der erstellten Doppelschlange.|  
|`Val`|Der Wert der Elemente in der erstellten Doppelschlange.|  
|`Right`|Die Doppelschlange, deren Kopie die erstellte Doppelschlange ist.|  
|`First`|Die Position des ersten Elements in dem zu kopierenden Elementbereich.|  
|`Last`|Die Position des ersten Elements nach dem zu kopierenden Elementbereich.|  
|`IList`|Das zu kopierende initializer_list-Element.|  
  
### <a name="remarks"></a>Hinweise  
 Alle Konstruktoren speichern ein Zuweisungsobjekt ( `Al`) und die doppelschlange initialisiert.  
  
 Die ersten beiden Konstruktoren geben eine leere ursprüngliche doppelschlange; der zweite gibt auch des Allocator-Typs ( `_Al`) verwendet werden.  
  
 Der dritte Konstruktor gibt eine Wiederholung einer angegebenen Anzahl ( ` count`) von Elementen des Standardwerts für die Klasse `Type`.  
  
 Die vierten und fünften Konstruktoren geben eine Wiederholung von ( `Count`) Elemente des Werts ` val`.  
  
 Der sechste Konstruktor gibt eine Kopie der Doppelschlange `Right` an.  
  
 Mit den siebten und achten Konstruktoren wird der Bereich `[First, Last)` einer Doppelschlange kopiert.  
  
 Der siebte Konstruktor verschiebt die Doppelschlange `Right`.  
  
 Der achte Konstruktor kopiert den Inhalt eines initializer_list-Elements.  
  
 Keine der Konstruktoren führen Zwischenneuzuordnungen aus.  
  
### <a name="example"></a>Beispiel  
  
```  
/ compile with: /EHsc  
#include <deque>  
#include <iostream>  
#include <forward_list>  
  
int main()  
{  
    using namespace std;  
  
    forward_list<int> f1{ 1, 2, 3, 4 };  
  
    f1.insert_after(f1.begin(), { 5, 6, 7, 8 });  
  
    deque <int>::iterator c1_Iter, c2_Iter, c3_Iter, c4_Iter, c5_Iter, c6_Iter;  
  
    // Create an empty deque c0  
    deque <int> c0;  
  
    // Create a deque c1 with 3 elements of default value 0  
    deque <int> c1(3);  
  
    // Create a deque c2 with 5 elements of value 2  
    deque <int> c2(5, 2);  
  
    // Create a deque c3 with 3 elements of value 1 and with the   
    // allocator of deque c2  
    deque <int> c3(3, 1, c2.get_allocator());  
  
    // Create a copy, deque c4, of deque c2  
    deque <int> c4(c2);  
  
    // Create a deque c5 by copying the range c4[ first,  last)  
    c4_Iter = c4.begin();  
    c4_Iter++;  
    c4_Iter++;  
    deque <int> c5(c4.begin(), c4_Iter);  
  
    // Create a deque c6 by copying the range c4[ first,  last) and   
    // c2 with the allocator of deque  
    c4_Iter = c4.begin();  
    c4_Iter++;  
    c4_Iter++;  
    c4_Iter++;  
    deque <int> c6(c4.begin(), c4_Iter, c2.get_allocator());  
  
    // Create a deque c8 by copying the contents of an initializer_list  
    // using brace initialization  
    deque<int> c8({ 1, 2, 3, 4 });  
  
    initializer_list<int> iList{ 5, 6, 7, 8 };  
    deque<int> c9( iList);  
  
    cout << "c1 = ";  
    for (int i : c1)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c2 = ";  
    for (int i : c2)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c3 = ";  
    for (int i : c3)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c4 = ";  
    for (int i : c4)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c5 = ";  
    for (int i : c5)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c6 = ";  
    for (int i : c6)  
        cout << i << " ";  
    cout << endl;  
  
    // Move deque c6 to deque c7  
    deque <int> c7(move(c6));  
    deque <int>::iterator c7_Iter;  
  
    cout << "c7 =";  
    for (int i : c7)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c8 = ";  
    for (int i : c8)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c9 = ";  
    for (int i : c9)  
        cout << i << " ";  
    cout << endl;  
  
    int x = 3;  
}  
// deque_deque.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
    using namespace std;  
   deque <int>::iterator c1_Iter, c2_Iter, c3_Iter, c4_Iter, c5_Iter, c6_Iter;  
  
    // Create an empty deque c0  
    deque <int> c0;  
  
    // Create a deque c1 with 3 elements of default value 0  
    deque <int> c1( 3 );  
  
    // Create a deque c2 with 5 elements of value 2  
    deque <int> c2( 5, 2 );  
  
    // Create a deque c3 with 3 elements of value 1 and with the   
    // allocator of deque c2  
    deque <int> c3( 3, 1, c2.get_allocator( ) );  
  
    // Create a copy, deque c4, of deque c2  
    deque <int> c4( c2 );  
  
    // Create a deque c5 by copying the range c4[ first,  last)  
    c4_Iter = c4.begin( );  
    c4_Iter++;  
    c4_Iter++;  
    deque <int> c5( c4.begin( ), c4_Iter );  
  
    // Create a deque c6 by copying the range c4[ first,  last) and   
    // c2 with the allocator of deque  
    c4_Iter = c4.begin( );  
   c4_Iter++;  
   c4_Iter++;  
   c4_Iter++;  
   deque <int> c6( c4.begin( ), c4_Iter, c2.get_allocator( ) );  
  
    // Create a deque c8 by copying the contents of an initializer_list  
    // using brace initialization  
    deque<int> c8({ 1, 2, 3, 4 });  
  
        initializer_list<int> iList{ 5, 6, 7, 8 };  
    deque<int> c9( iList);  
  
    cout << "c1 = ";  
    for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
        cout << *c1_Iter << " ";  
    cout << endl;  
  
    cout << "c2 = ";  
    for ( c2_Iter = c2.begin( ); c2_Iter != c2.end( ); c2_Iter++ )  
        cout << *c2_Iter << " ";  
    cout << endl;  
  
    cout << "c3 = ";  
    for ( c3_Iter = c3.begin( ); c3_Iter != c3.end( ); c3_Iter++ )  
        cout << *c3_Iter << " ";  
    cout << endl;  
  
    cout << "c4 = ";  
    for ( c4_Iter = c4.begin( ); c4_Iter != c4.end( ); c4_Iter++ )  
        cout << *c4_Iter << " ";  
    cout << endl;  
  
    cout << "c5 = ";  
    for ( c5_Iter = c5.begin( ); c5_Iter != c5.end( ); c5_Iter++ )  
        cout << *c5_Iter << " ";  
    cout << endl;  
  
    cout << "c6 = ";  
    for ( c6_Iter = c6.begin( ); c6_Iter != c6.end( ); c6_Iter++ )  
        cout << *c6_Iter << " ";  
    cout << endl;  
  
    // Move deque c6 to deque c7  
    deque <int> c7( move(c6) );  
    deque <int>::iterator c7_Iter;  
  
    cout << "c7 =" ;  
    for ( c7_Iter = c7.begin( ) ; c7_Iter != c7.end( ) ; c7_Iter++ )  
        cout << " " << *c7_Iter;  
    cout << endl;  
  
    cout << "c8 = ";  
    for (int i : c8)  
        cout << i << " ";  
    cout << endl;  
  
    cout << "c9 = ";  
    or (int i : c9)  
        cout << i << " ";  
    cout << endl;  
}  
```  
  
##  <a name="a-namedequedifferencetypea-dequedifferencetype"></a><a name="deque__difference_type"></a>  deque:: difference_type  
 Ein Typ, die die Differenz zwischen zwei Iteratoren, auf Elemente innerhalb der gleichen Deque verweisen, bereitstellt.  
  
```  
typedef typename Allocator::difference_type difference_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Ein `difference_type` kann auch als die Anzahl der Elemente zwischen zwei Zeigern beschrieben werden.  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_diff_type.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <deque>  
#include <algorithm>  
  
int main( )   
{  
   using namespace std;  
  
   deque <int> c1;  
   deque <int>::iterator c1_Iter, c2_Iter;  
  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1.push_back( 10 );  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
  
   c1_Iter = c1.begin( );  
   c2_Iter = c1.end( );  
  
   deque <int>::difference_type df_typ1, df_typ2, df_typ3;  
  
   df_typ1 = count( c1_Iter, c2_Iter, 10 );  
   df_typ2 = count( c1_Iter, c2_Iter, 20 );  
   df_typ3 = count( c1_Iter, c2_Iter, 30 );  
   cout << "The number '10' is in c1 collection " << df_typ1 << " times.\n";  
   cout << "The number '20' is in c1 collection " << df_typ2 << " times.\n";  
   cout << "The number '30' is in c1 collection " << df_typ3 << " times.\n";  
}  
```  
  
```Output  
The number '10' is in c1 collection 1 times.  
The number '20' is in c1 collection 2 times.  
The number '30' is in c1 collection 3 times.  
```  
  
##  <a name="a-namedequeemplacea-dequeemplace"></a><a name="deque__emplace"></a>  deque:: emplace  
 Fügt ein Element vor Ort in die doppelschlange an einer angegebenen Position erstellt.  
  
```  
iterator emplace(
    const_iterator _Where,  
    Type&& val);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|`_Where`|Die Position in der [Deque](../standard-library/deque-class.md) in dem das erste Element eingefügt wird.|  
|` val`|Der Wert des Elements, das in den `deque` eingefügt wird.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die Funktion gibt einen Iterator, der auf die Position zeigt, in dem das neue Element in die doppelschlange eingefügt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Jeder Einfügevorgang kann teuer sein, finden Sie unter `deque` eine Erläuterung der `deque` Leistung.  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_emplace.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
   deque <int>::iterator Iter;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
   v1.push_back( 30 );  
  
   cout << "v1 =" ;  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
// initialize a deque of deques by moving v1  
   deque < deque <int> > vv1;  
  
   vv1.emplace( vv1.begin(), move( v1 ) );  
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )  
      {  
      cout << "vv1[0] =";  
      for (Iter = vv1[0].begin( ); Iter != vv1[0].end( ); Iter++ )  
         cout << " " << *Iter;  
      cout << endl;  
      }  
}  
```  
  
```Output  
v1 = 10 20 30  
vv1[0] = 10 20 30  
```  
  
##  <a name="a-namedequeemplacebacka-dequeemplaceback"></a><a name="deque__emplace_back"></a>  deque:: emplace_back  
 Fügt ein Element am Ende der doppelschlange konstruiertes.  
  
```  
void emplace_back(Type&& val);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|` val`|Das Element hinzugefügt, die an das Ende der [Deque](../standard-library/deque-class.md).|  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_emplace_back.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
  
   v1.push_back( 1 );  
   if ( v1.size( ) != 0 )  
      cout << "Last element: " << v1.back( ) << endl;  
  
   v1.push_back( 2 );  
   if ( v1.size( ) != 0 )  
      cout << "New last element: " << v1.back( ) << endl;  
  
// initialize a deque of deques by moving v1  
   deque < deque <int> > vv1;  
  
   vv1.emplace_back( move( v1 ) );  
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )  
      cout << "Moved last element: " << vv1[0].back( ) << endl;  
}  
```  
  
```Output  
Last element: 1  
New last element: 2  
Moved last element: 2  
```  
  
##  <a name="a-namedequeemplacefronta-dequeemplacefront"></a><a name="deque__emplace_front"></a>  deque:: emplace_front  
 Fügt ein Element am Ende der doppelschlange konstruiertes.  
  
```  
void emplace_front(Type&& val);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|` val`|Das Element hinzugefügt wird, am Anfang der [Deque](../standard-library/deque-class.md).|  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_emplace_front.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
  
   v1.push_back( 1 );  
   if ( v1.size( ) != 0 )  
      cout << "Last element: " << v1.back( ) << endl;  
  
   v1.push_back( 2 );  
   if ( v1.size( ) != 0 )  
      cout << "New last element: " << v1.back( ) << endl;  
  
// initialize a deque of deques by moving v1  
   deque < deque <int> > vv1;  
  
   vv1.emplace_front( move( v1 ) );  
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )  
      cout << "Moved last element: " << vv1[0].back( ) << endl;  
}  
```  
  
```Output  
Last element: 1  
New last element: 2  
Moved last element: 2  
```  
  
##  <a name="a-namedequeemptya-dequeempty"></a><a name="deque__empty"></a>  deque:: Empty  
 Testet, ob eine Deque leer ist.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 **true** ist die doppelschlange leer ist; **false** Wenn doppelschlange nicht leer ist.  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_empty.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   if ( c1.empty( ) )  
      cout << "The deque is empty." << endl;  
   else  
      cout << "The deque is not empty." << endl;  
}  
```  
  
```Output  
The deque is not empty.  
```  
  
##  <a name="a-namedequeenda-dequeend"></a><a name="deque__end"></a>  deque:: End  
 Gibt einen Iterator, der den Speicherort adressiert, das letzte Element in einer doppelschlange zurück.  
  
```  
const_iterator end() const;

iterator end();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator mit zufälligem Zugriff, der den Speicherort adressiert, das letzte Element in einer doppelschlange adressiert. Die doppelschlange ist leer, und klicken Sie dann auf deque:: End == deque.  
  
### <a name="remarks"></a>Hinweise  
 **End** wird verwendet, um zu testen, ob ein Iterator das Ende der doppelschlange erreicht hat.  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_end.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::iterator c1_Iter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_Iter = c1.end( );  
   c1_Iter--;  
   cout << "The last integer of c1 is " << *c1_Iter << endl;  
  
   c1_Iter--;  
 *c1_Iter = 400;  
   cout << "The new next-to-last integer of c1 is " << *c1_Iter << endl;  
  
   // If a const iterator had been declared instead with the line:  
   // deque <int>::const_iterator c1_Iter;  
   // an error would have resulted when inserting the 400  
  
   cout << "The deque is now:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
}  
```  
  
```Output  
The last integer of c1 is 30  
The new next-to-last integer of c1 is 400  
The deque is now: 10 400 30  
```  
  
##  <a name="a-namedequeerasea-dequeerase"></a><a name="deque__erase"></a>  deque:: Erase  
 Entfernt ein Element oder einen Bereich von Elementen in einer doppelschlange von angegebenen Speicherorten.  
  
```  
iterator erase(iterator _Where);

iterator erase(iterator first, iterator last);
```  
  
### <a name="parameters"></a>Parameter  
 `_Where`  
 Die Position des Elements aus der entfernt werden soll.  
  
 ` first`  
 Position des ersten Elements aus der entfernt werden soll.  
  
 ` last`  
 Die Position direkt hinter das letzte Element aus der entfernt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator mit wahlfreiem Zugriff, der das erste Element verbleibt, nachdem alle Elemente entfernt wurden, oder ein Zeiger auf das Ende der doppelschlange, wenn kein solches Element vorhanden ist.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu **Löschen**, finden Sie unter [deque:: Erase und deque:: Clear](../misc/deque-erase-and-deque-clear.md).  
  
 **Löschen Sie** nie eine Ausnahme auslöst.  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_erase.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::iterator Iter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1.push_back( 40 );  
   c1.push_back( 50 );  
   cout << "The initial deque is: ";  
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << *Iter << " ";  
   cout << endl;  
   c1.erase( c1.begin( ) );  
   cout << "After erasing the first element, the deque becomes:  ";  
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << *Iter << " ";  
   cout << endl;  
   Iter = c1.begin( );  
   Iter++;  
   c1.erase( Iter, c1.end( ) );  
   cout << "After erasing all elements but the first, deque becomes: ";  
   for ( Iter = c1.begin( ); Iter != c1.end( ); Iter++ )  
      cout << *Iter << " ";  
   cout << endl;  
}  
```  
  
```Output  
The initial deque is: 10 20 30 40 50   
After erasing the first element, the deque becomes:  20 30 40 50   
After erasing all elements but the first, deque becomes: 20   
```  
  
##  <a name="a-namedequefronta-dequefront"></a><a name="deque__front"></a>  deque:: Front  
 Gibt einen Verweis auf das erste Element in einer doppelschlange zurück.  
  
```  
reference front();

const_reference front() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die doppelschlange leer ist, ist die Rückgabe nicht definiert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Rückgabewert der `front` zugewiesen ist eine `const_reference`, Deque-Objekt kann nicht geändert werden. Wenn der Rückgabewert der `front` zugewiesen ist eine **Verweis**, kann die Deque-Objekt geändert werden.  
  
 Beim Kompilieren mit _SECURE_SCL 1 wird ein Laufzeitfehler auftreten, wenn Sie versuchen, ein Element in eine leere doppelschlange zuzugreifen.  Weitere Informationen finden Sie unter [Checked Iterators](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_front.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 11 );  
  
   int& i = c1.front( );  
   const int& ii = c1.front( );  
  
   cout << "The first integer of c1 is " << i << endl;  
   i++;  
   cout << "The second integer of c1 is " << ii << endl;  
}  
```  
  
```Output  
The first integer of c1 is 10  
The second integer of c1 is 11  
```  
  
##  <a name="a-namedequegetallocatora-dequegetallocator"></a><a name="deque__get_allocator"></a>  deque:: get_allocator  
 Gibt eine Kopie des zuweisungsobjekts verwendet, um die doppelschlange zu erstellen.  
  
```  
Allocator get_allocator() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Zuweisung von doppelschlange verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Zuweisungen für die Deque-Klasse geben an, wie die Klasse Speicher verwaltet. Für die meisten Programmieranforderungen reichen die Standard-Zuweisungen mit STL-Container-Klassen aus. Schreiben und Verwenden Ihrer eigener Zuweisungsklasse ist ein C++ -Thema für Fortgeschrittene.  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_get_allocator.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   // The following lines declare objects that use the default allocator.  
   deque <int> c1;  
   deque <int, allocator<int> > c2 = deque <int, allocator<int> >( allocator<int>( ) );  
  
   // c3 will use the same allocator class as c1  
   deque <int> c3( c1.get_allocator( ) );  
  
   deque <int>::allocator_type xlst = c1.get_allocator( );  
   // You can now call functions on the allocator class used by c1  
}  
```  
  
##  <a name="a-namedequeinserta-dequeinsert"></a><a name="deque__insert"></a>  deque:: Insert  
 Fügt ein Element oder mehrere Elemente oder ein Reihe von Elementen an einer bestimmten Position in die Doppelschlange ein.  
  
```  
iterator insert(
    const_iterator Where,  
    const Type& Val);

iterator insert(
    const_iterator Where,  
    Type&& Val);

void insert(
    iterator Where,  
    size_type Count,  
    const Type& Val);

template <class InputIterator>  
void insert(
    iterator Where,  
    InputIterator First,  
    InputIterator Last);

iterator insert(
    iterator Where,initializer_list<Type>  
IList);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|`Where`|Die Position in der Zieldoppelschlange, an der das erste Element eingefügt wird.|  
|`Val`|Der Wert des Elements, das in die Doppelschlange eingefügt wird.|  
|`Count`|Die Anzahl von Elementen, die in die Doppelschlange eingefügt werden.|  
|`First`|Die Position des ersten Elements in dem Elementbereich in der Argumentdoppelschlange, die kopiert werden soll.|  
|`Last`|Die Position des ersten Elements hinter dem Elementbereich in der Argumentdoppelschlange, die kopiert werden soll.|  
|`IList`|Das initializer_list-Element der einzufügenden Elemente.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die ersten zwei Einfügefunktionen geben ein Iterator zurück, der auf den Speicherort zeigt, an dem das neue Element in die Doppelschlange eingefügt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Jeder Einfügevorgang kann ressourcenintensiv sein.  
  
##  <a name="a-namedequeiteratora-dequeiterator"></a><a name="deque__iterator"></a>  deque:: Iterator  
 Eine Typ, die einem Iterator mit zufälligem Zugriff bereitstellt, kann lesen oder ändern ein Element in einer doppelschlange.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Ein Typ **Iterator** kann zum Ändern des Werts eines Elements verwendet werden.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [beginnen](#deque__begin).  
  
##  <a name="a-namedequemaxsizea-dequemaxsize"></a><a name="deque__max_size"></a>  deque:: max_size  
 Gibt die maximale Länge der doppelschlange zurück.  
  
```  
size_type max_size() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximal mögliche Länge der doppelschlange.  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_max_size.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::size_type i;  
  
   i = c1.max_size( );  
   cout << "The maximum possible length of the deque is " << i << "." << endl;  
}  
```  
  
##  <a name="a-namedequeoperatorata-dequeoperator"></a><a name="deque__operator_at"></a>  deque:: Operator]  
 Gibt einen Verweis auf das Deque-Element an der angegebenen Position zurück.  
  
```  
reference operator[](size_type _Pos);

const_reference operator[](size_type _Pos) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Pos`  
 Die Position des Elements Deque verwiesen werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das Element, dessen Position im Argument angegeben wird. Wenn die angegebene Position größer als die Größe der doppelschlange ist, ist das Ergebnis nicht definiert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Rückgabewert der `operator[]` zugewiesen ist eine `const_reference`, Deque-Objekt kann nicht geändert werden. Wenn der Rückgabewert der `operator[]` zugewiesen ist eine **Verweis**, kann die Deque-Objekt geändert werden.  
  
 Beim Kompilieren mit _SECURE_SCL 1 wird ein Laufzeitfehler auftreten, wenn Sie versuchen, ein Element außerhalb der Grenzen der doppelschlange zuzugreifen.  Weitere Informationen finden Sie unter [Checked Iterators](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_op_ref.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   cout << "The first integer of c1 is " << c1[0] << endl;  
   int& i = c1[1];  
   cout << "The second integer of c1 is " << i << endl;  
  
}  
```  
  
```Output  
The first integer of c1 is 10  
The second integer of c1 is 20  
```  
  
##  <a name="a-namedequeoperatoreqa-dequeoperator"></a><a name="deque__operator_eq"></a>  deque:: Operator =  
 Ersetzt die Elemente dieser mit den Elementen aus einer anderen doppelschlange.  
  
```  
deque& operator=(const deque& right);

deque& operator=(deque&& right);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|` right`|Die doppelschlange, die den neuen Inhalt bereitstellt.|  
  
### <a name="remarks"></a>Hinweise  
 Die erste Außerkraftsetzung kopiert die Elemente in dieser Deque aus ` right`, die Quelle der Zuordnung. Die zweite Außerkraftsetzung verschiebt die Elemente in dieser Deque aus ` right`.  
  
 Elemente, die in diesem Deque enthalten sind, bevor der Operator ausgeführt wird, werden entfernt.  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_operator_as.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
using namespace std;  
  
typedef deque<int> MyDeque;  
  
template<typename MyDeque> struct S;  
  
template<typename MyDeque> struct S<MyDeque&> {  
  static void show( MyDeque& d ) {  
    MyDeque::const_iterator iter;  
    for (iter = d.cbegin(); iter != d.cend(); iter++)  
       cout << *iter << " ";  
    cout << endl;  
  }  
};  
  
template<typename MyDeque> struct S<MyDeque&&> {  
  static void show( MyDeque&& d ) {  
    MyDeque::const_iterator iter;  
    for (iter = d.cbegin(); iter != d.cend(); iter++)  
       cout << *iter << " ";  
cout << " via unnamed rvalue reference " << endl;  
  }  
};  
  
int main( )  
{  
   MyDeque d1, d2;  
  
   d1.push_back(10);  
   d1.push_back(20);  
   d1.push_back(30);  
   d1.push_back(40);  
   d1.push_back(50);  
  
   cout << "d1 = " ;  
   S<MyDeque&>::show( d1 );  
  
   d2 = d1;  
   cout << "d2 = ";  
   S<MyDeque&>::show( d2 );  
  
   cout << "     ";  
   S<MyDeque&&>::show ( move< MyDeque& > (d1) );  
 }  
```  
  
##  <a name="a-namedequepointera-dequepointer"></a><a name="deque__pointer"></a>  deque:: Pointer  
 Gibt einen Zeiger auf ein Element in einem [Deque](../standard-library/deque-class.md).  
  
```unstlib  
typedef typename Allocator::pointer pointer;  
```  
  
### <a name="remarks"></a>Hinweise  
 Ein Typ **Zeiger** kann zum Ändern des Werts eines Elements verwendet werden. Ein [Iterator](#deque__iterator) wird häufiger für den Zugriff auf ein doppelschlangenelement verwendet.  
  
##  <a name="a-namedequepopbacka-dequepopback"></a><a name="deque__pop_back"></a>  deque:: pop_back  
 Löscht das Element am Ende der doppelschlange.  
  
```  
void pop_back();
```  
  
### <a name="remarks"></a>Hinweise  
 Das letzte Element darf nicht leer sein. `pop_back` löst nie eine Ausnahme aus.  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_pop_back.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   cout << "The first element is: " << c1.front( ) << endl;  
   cout << "The last element is: " << c1.back( ) << endl;  
  
   c1.pop_back( );  
   cout << "After deleting the element at the end of the deque, the "  
      "last element is: " << c1.back( ) << endl;  
}  
```  
  
```Output  
The first element is: 1  
The last element is: 2  
After deleting the element at the end of the deque, the last element is: 1  
```  
  
##  <a name="a-namedequepopfronta-dequepopfront"></a><a name="deque__pop_front"></a>  deque:: pop_front  
 Löscht das Element am Anfang der doppelschlange.  
  
```  
void pop_front();
```  
  
### <a name="remarks"></a>Hinweise  
 Das erste Element darf nicht leer sein. `pop_front` löst nie eine Ausnahme aus.  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_pop_front.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   cout << "The first element is: " << c1.front( ) << endl;  
   cout << "The second element is: " << c1.back( ) << endl;  
  
   c1.pop_front( );  
   cout << "After deleting the element at the beginning of the "  
      "deque, the first element is: " << c1.front( ) << endl;  
}  
```  
  
```Output  
The first element is: 1  
The second element is: 2  
After deleting the element at the beginning of the deque, the first element is: 2  
```  
  
##  <a name="a-namedequepushbacka-dequepushback"></a><a name="deque__push_back"></a>  deque:: push_back  
 Fügt ein Element am Ende der doppelschlange.  
  
```  
void push_back(const Type& val);

void push_back(Type&& val);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|` val`|Das Element am Ende der doppelschlange hinzugefügt.|  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Ausnahme ausgelöst wird, bleibt die Deque unverändert, und die Ausnahme erneut ausgelöst wird.  
  
##  <a name="a-namedequepushfronta-dequepushfront"></a><a name="deque__push_front"></a>  deque:: push_front  
 Fügt ein Element am Anfang der doppelschlange.  
  
```  
    void push_front(const Type& val);

void push_front(Type&& val);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|` val`|Das Element am Anfang der doppelschlange eingefügt wird.|  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Ausnahme ausgelöst wird, bleibt die Deque unverändert, und die Ausnahme erneut ausgelöst wird.  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_push_front.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
#include <string>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_front( 1 );  
   if ( c1.size( ) != 0 )  
      cout << "First element: " << c1.front( ) << endl;  
  
   c1.push_front( 2 );  
   if ( c1.size( ) != 0 )  
      cout << "New first element: " << c1.front( ) << endl;  
  
// move initialize a deque of strings  
   deque <string> c2;  
   string str("a");  
  
   c2.push_front( move( str ) );  
   cout << "Moved first element: " << c2.front( ) << endl;  
}  
```  
  
```Output  
First element: 1  
New first element: 2  
Moved first element: a  
```  
  
##  <a name="a-namedequerbegina-dequerbegin"></a><a name="deque__rbegin"></a>  deque:: rbegin  
 Gibt einen Iterator an das erste Element in einer umgekehrten Deque zurück.  
  
```  
const_reverse_iterator rbegin() const;

reverse_iterator rbegin();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein umgekehrter Iterator mit wahlfreiem Zugriff das erste Element in einer umgekehrten Deque adressiert oder nach dem letzten Element in der nicht umgekehrten Deque adressiert.  
  
### <a name="remarks"></a>Hinweise  
 `rbegin` wird mit einem umgekehrten Deque verwendet, ebenso wie [beginnen](#deque__begin) mit einer doppelschlange verwendet wird.  
  
 Wenn der Rückgabewert der `rbegin` zugewiesen ist eine `const_reverse_iterator`, Deque-Objekt kann nicht geändert werden. Wenn der Rückgabewert der `rbegin` zugewiesen ist eine `reverse_iterator`, kann die Deque-Objekt geändert werden.  
  
 `rbegin` kann verwendet werden, um eine Deque rückwärts durchlaufen.  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_rbegin.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::iterator c1_Iter;  
   deque <int>::reverse_iterator c1_rIter;  
  
   // If the following line had replaced the line above, an error   
   // would have resulted in the line modifying an element   
   // (commented below) because the iterator would have been const  
   // deque <int>::const_reverse_iterator c1_rIter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_rIter = c1.rbegin( );  
   cout << "Last element in the deque is " << *c1_rIter << "." << endl;  
  
   cout << "The deque contains the elements: ";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << *c1_Iter << " ";  
   cout << "in that order.";  
   cout << endl;  
  
   // rbegin can be used to iterate through a deque in reverse order  
   cout << "The reversed deque is: ";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << *c1_rIter << " ";  
   cout << endl;  
  
   c1_rIter = c1.rbegin( );  
 *c1_rIter = 40;  // This would have caused an error if a   
                    // const_reverse iterator had been declared as   
                    // noted above  
   cout << "Last element in deque is now " << *c1_rIter << "." << endl;  
}  
```  
  
```Output  
Last element in the deque is 30.  
The deque contains the elements: 10 20 30 in that order.  
The reversed deque is: 30 20 10   
Last element in deque is now 40.  
```  
  
##  <a name="a-namedequereferencea-dequereference"></a><a name="deque__reference"></a>  deque:: Reference  
 Ein Typ, der einen Verweis auf ein Element in einer doppelschlange bereitstellt.  
  
```  
typedef typename Allocator::reference reference;  
```  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_reference.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
  
   const int &i = c1.front( );  
   int &j = c1.back( );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namedequerenda-dequerend"></a><a name="deque__rend"></a>  deque:: rend  
 Gibt einen Iterator, der den Speicherort adressiert, das letzte Element in einer umgekehrten Deque zurück.  
  
```  
const_reverse_iterator rend() const;

reverse_iterator rend();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein umgekehrter Iterator mit zufälligem Zugriff, der nachfolgt das letzte Element in einer umgekehrten Deque (der Speicherort, der das erste Element in der nicht umgekehrten Deque vorangegangen war).  
  
### <a name="remarks"></a>Hinweise  
 `rend` wird mit einem umgekehrten Deque verwendet, ebenso wie [End](#deque__end) mit einer doppelschlange verwendet wird.  
  
 Wenn der Rückgabewert der `rend` zugewiesen ist eine `const_reverse_iterator`, Deque-Objekt kann nicht geändert werden. Wenn der Rückgabewert der `rend` zugewiesen ist eine `reverse_iterator`, kann die Deque-Objekt geändert werden.  
  
 `rend` kann verwendet werden, zu überprüfen, ob es sich bei ein umgekehrter Iterator das Ende der doppelschlange erreicht hat.  
  
 Der von `rend` zurückgegebene Wert darf nicht dereferenziert werden.  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_rend.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
  
   deque <int> c1;  
   deque <int>::iterator c1_Iter;  
   deque <int>::reverse_iterator c1_rIter;  
   // If the following line had replaced the line above, an error  
   // would have resulted in the line modifying an element  
   // (commented below) because the iterator would have been const  
   // deque <int>::const_reverse_iterator c1_rIter;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1_rIter = c1.rend( );  
   c1_rIter --; // Decrementing a reverse iterator moves it forward   
                // in the deque (to point to the first element here)  
   cout << "The first element in the deque is: " << *c1_rIter << endl;  
  
   cout << "The deque is: ";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << *c1_Iter << " ";  
   cout << endl;  
  
   // rend can be used to test if an iteration is through all of   
   // the elements of a reversed deque  
   cout << "The reversed deque is: ";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << *c1_rIter << " ";  
   cout << endl;  
  
   c1_rIter = c1.rend( );  
   c1_rIter--; // Decrementing the reverse iterator moves it backward   
               // in the reversed deque (to the last element here)  
 *c1_rIter = 40; // This modification of the last element would   
                   // have caused an error if a const_reverse   
                   // iterator had been declared (as noted above)  
   cout << "The modified reversed deque is: ";  
   for ( c1_rIter = c1.rbegin( ); c1_rIter != c1.rend( ); c1_rIter++ )  
      cout << *c1_rIter << " ";  
   cout << endl;  
}  
```  
  
```Output  
The first element in the deque is: 10  
The deque is: 10 20 30   
The reversed deque is: 30 20 10   
The modified reversed deque is: 30 20 40   
```  
  
##  <a name="a-namedequeresizea-dequeresize"></a><a name="deque__resize"></a>  deque:: Resize  
 Gibt eine neue Größe für die Anzahl an.  
  
```  
void resize(size_type _Newsize);

void resize(size_type _Newsize, Type val);
```  
  
### <a name="parameters"></a>Parameter  
 `_Newsize`  
 Die neue Größe der doppelschlange.  
  
 ` val`  
 Der Wert der doppelschlange hinzugefügt werden, wenn die neue Größe größer ist als neue Elemente, die der ursprünglichen Größe. Wenn der Wert ausgelassen wird, werden dem Standardwert die neuen Elemente für die Klasse zugewiesen.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die doppelschlange Größe kleiner als die angeforderte Größe ist `_Newsize`, werden Elemente hinzugefügt, die doppelschlange, bis er die angeforderte Größe erreicht.  
  
 Der doppelschlange größer als die angeforderte Größe ist, werden die Elemente am Ende der doppelschlange gelöscht, bis die doppelschlange die Größe erreicht `_Newsize`.  
  
 Wenn die tatsächliche Größe der doppelschlange der angeforderten Größe entspricht, ist keine Aktion ausgeführt.  
  
 [Größe](#deque__size) entspricht der aktuellen Größe der doppelschlange.  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_resize.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{   
   using namespace std;  
   deque <int> c1;  
  
   c1.push_back( 10 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
  
   c1.resize( 4,40 );  
   cout << "The size of c1 is: " << c1.size( ) << endl;  
   cout << "The value of the last element is " << c1.back( ) << endl;  
  
   c1.resize( 5 );  
   cout << "The size of c1 is now: " << c1.size( ) << endl;  
   cout << "The value of the last element is now " << c1.back( ) << endl;  
  
   c1.resize( 2 );  
   cout << "The reduced size of c1 is: " << c1.size( ) << endl;  
   cout << "The value of the last element is now " << c1.back( ) << endl;  
}  
```  
  
```Output  
The size of c1 is: 4  
The value of the last element is 40  
The size of c1 is now: 5  
The value of the last element is now 0  
The reduced size of c1 is: 2  
The value of the last element is now 20  
```  
  
##  <a name="a-namedequereverseiteratora-dequereverseiterator"></a><a name="deque__reverse_iterator"></a>  deque:: reverse_iterator  
 Eine Typ, die einem Iterator mit zufälligem Zugriff bereitstellt, kann lesen oder ändern ein Elements in einer umgekehrten Deque.  
  
```  
typedef std::reverse_iterator<iterator> reverse_iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Ein `reverse_iterator` wird verwendet, um die doppelschlange durchlaufen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für Rbegin.  
  
##  <a name="a-namedequeshrinktofita-dequeshrinktofit"></a><a name="deque__shrink_to_fit"></a>  deque:: shrink_to_fit  
 Verwirft Überkapazität.  
  
```  
void shrink_to_fit();
```  
  
### <a name="remarks"></a>Hinweise  
 Es gibt keine portable Möglichkeit zum bestimmen, ob `shrink_to_fit` von genutzte Speicher verringert eine [Deque](../standard-library/deque-class.md).  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_shrink_to_fit.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   deque <int> v1;  
   //deque <int>::iterator Iter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
   cout << "Current size of v1 = "   
      << v1.size( ) << endl;  
   v1.shrink_to_fit();  
   cout << "Current size of v1 = "   
      << v1.size( ) << endl;  
}  
```  
  
```Output  
Current size of v1 = 1  
Current size of v1 = 1  
```  
  
##  <a name="a-namedequesizea-dequesize"></a><a name="deque__size"></a>  deque:: Size  
 Gibt die Anzahl der Elemente in der doppelschlange zurück.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Länge der doppelschlange.  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_size.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1;  
   deque <int>::size_type i;  
  
   c1.push_back( 1 );  
   i = c1.size( );  
   cout << "The deque length is " << i << "." << endl;  
  
   c1.push_back( 2 );  
   i = c1.size( );  
   cout << "The deque length is now " << i << "." << endl;  
}  
```  
  
```Output  
The deque length is 1.  
The deque length is now 2.  
```  
  
##  <a name="a-namedequesizetypea-dequesizetype"></a><a name="deque__size_type"></a>  deque:: size_type  
 Ein Typ, der die Anzahl der Elemente in einer doppelschlange ermittelt.  
  
```  
typedef typename Allocator::size_type size_type;  
```  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Größe](#deque__size).  
  
##  <a name="a-namedequeswapa-dequeswap"></a><a name="deque__swap"></a>  deque:: Swap  
 Tauscht die Elemente von zwei deque-Objekten aus.  
  
```  
void swap(deque<Type, Allocator>& right);

friend void swap(deque<Type, Allocator>& left, deque<Type, Allocator>& right) template <class Type, class Allocator>  
void swap(deque<Type, Allocator>& left, deque<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` right`  
 Die doppelschlange, die die auszutauschenden Elemente werden oder die doppelschlange, deren Elemente sind mit denen der doppelschlange ausgetauscht werden ` left`.  
  
 ` left`  
 Anzahl, dessen Elemente sind mit denen der doppelschlange ausgetauscht werden ` right`.  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_swap.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   deque <int> c1, c2, c3;  
   deque <int>::iterator c1_Iter;  
  
   c1.push_back( 1 );  
   c1.push_back( 2 );  
   c1.push_back( 3 );  
   c2.push_back( 10 );  
   c2.push_back( 20 );  
   c3.push_back( 100 );  
  
   cout << "The original deque c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   c1.swap( c2 );  
  
   cout << "After swapping with c2, deque c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   swap( c1,c3 );  
  
   cout << "After swapping with c3, deque c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
  
   swap<>(c1, c2);  
   cout << "After swapping with c2, deque c1 is:";  
   for ( c1_Iter = c1.begin( ); c1_Iter != c1.end( ); c1_Iter++ )  
      cout << " " << *c1_Iter;  
   cout << endl;  
}  
```  
  
```Output  
The original deque c1 is: 1 2 3  
After swapping with c2, deque c1 is: 10 20  
After swapping with c3, deque c1 is: 100  
After swapping with c2, deque c1 is: 1 2 3  
```  
  
##  <a name="a-namedequevaluetypea-dequevaluetype"></a><a name="deque__value_type"></a>  deque:: value_type  
 Ein Typ, der in einer doppelschlange gespeicherten Datentyp darstellt.  
  
```  
typedef typename Allocator::value_type value_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 `value_type` ist ein Synonym für den Vorlagenparameter **Typ**.  
  
### <a name="example"></a>Beispiel  
  
```  
// deque_value_type.cpp  
// compile with: /EHsc  
#include <deque>  
#include <iostream>  
int main( )   
{  
   using namespace std;  
   deque<int>::value_type AnInt;  
   AnInt = 44;  
   cout << AnInt << endl;  
}  
```  
  
```Output  
44  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)

