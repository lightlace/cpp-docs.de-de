---
title: "Vector-Klasse 1"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "std::vector"
  - "vector"
  - "std.vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vector-Klasse"
ms.assetid: a3e0a8f8-7565-4fe0-93e4-e4d74ae1b70d
caps.latest.revision: 24
caps.handback.revision: "24"
ms.author: "corob"
manager: "ghogen"
---
# Vector-Klasse 1
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die STL-Vektorklasse ist eine Vorlagenklasse von Sequenzcontainern, die Elemente eines bestimmten Typs in einer linearen Anordnung organisieren und schnellen, wahlfreien Zugriff auf jedes Element ermöglichen. Sie sollten der jeweils bevorzugte Container für eine Sequenz sein, wenn die Leistung mit wahlfreiem Zugriff ein wichtiger Faktor ist.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Type, class Allocator = allocator<Type>>  
class vector  
```  
  
#### <a name="parameters"></a>Parameter  
 *Typ*  
 Der im Vektor zu speichernde Elementdatentyp.  
  
 `Allocator`  
 Der Typ, der das gespeicherte allocator-Objekt darstellt, das Details zum Belegen und Freigeben von Arbeitsspeicher für den Vektor kapselt. Dieses Argument ist optional und der Standardwert ist **Zuweisung***\< Typ>.*  
  
## <a name="remarks"></a>Hinweise  
 Vektoren ermöglichen konstante Zeiteinfügungen und -löschungen am Ende der Sequenz. Für das Einfügen oder Löschen von Elementen in der Mitte eines Vektors ist lineare Zeit erforderlich. Die Leistung der [Deque-Klasse](../standard-library/deque-class.md) Container ist in Bezug auf die Einfüge- und Löschvorgänge am Anfang und Ende einer Sequenz leistungsfähiger. Die [list-Klasse](../standard-library/list-class.md) Container ist in Bezug auf die Einfüge- und Löschvorgänge an einer beliebigen Position innerhalb der Sequenz leistungsfähiger.  
  
 Eine Speicherneubelegung für einen Vektor findet statt, wenn eine Memberfunktion die Sequenz, die in dem vector-Objekt enthalten ist, über dessen aktuelle Speicherkapazität hinaus vergrößern muss. Andere Einfügungen und Löschungen können verschiedene Speicheradressen innerhalb der Sequenz ändern. In allen diesen Fällen werden Iteratoren oder Verweise auf geänderte Teile der Sequenz ungültig. Wenn keine Neuzuordnung stattfindet, bleiben nur Iteratoren und Verweise vor dem Einfüge-/Löschpunkt gültig.  
  
 Die [Vector \< Bool> Klasse](../standard-library/vector-bool-class.md) eine vollständige Spezialisierung des vorlagenklassenvektors für Elemente vom Typ Bool mit einer Zuweisung für den zugrunde liegenden Typ, der von der Spezialisierung verwendet wird.  
  
 Die [Vector \< Bool> reference-Klasse](../standard-library/vector-bool-class.md#vector_lt_bool_gt___reference_class) ist eine geschachtelte Klasse, deren Objekte Verweise auf Elemente (einzelne Bits) innerhalb eines Vektors bereitstellen \< Bool> Objekt.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[Vektor](#vector__vector)|Erstellt einen Vektor einer bestimmten Größe bzw. mit Elementen eines bestimmten Werts oder mit einem bestimmten `allocator`-Element oder als vollständige bzw. teilweise Kopie eines anderen Vektors.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[allocator_type](#vector__allocator_type)|Ein Typ, der die `allocator`-Klasse für das Vektorobjekt darstellt.|  
|[const_iterator](#vector__const_iterator)|Ein Typ, der einen Iterator mit wahlfreiem Zugriff bereitstellt, mit dem ein `const`-Element in einem Vektor gelesen werden kann.|  
|[const_pointer](#vector__const_pointer)|Ein Typ, der einen Zeiger auf ein `const`-Element in einem Vektor bereitstellt.|  
|[const_reference](#vector__const_reference)|Ein Typ, der einen Verweis auf ein `const`-Element bereitstellt, das in einem Vektor zum Lesen und Ausführen von `const`-Vorgängen gespeichert ist.|  
|[const_reverse_iterator](#vector__const_reverse_iterator)|Ein Typ, der einen Iterator mit zufälligem Zugriff bereitstellt, mit dem jedes `const`-Element im Vektor gelesen werden kann.|  
|[difference_type](#vector__difference_type)|Ein Typ, der die Differenz zwischen den Adressen von zwei Elementen in einem Vektor bereitstellt.|  
|[Iterator](#vector__iterator)|Ein Typ, der einen Iterator mit wahlfreiem Zugriff bereitstellt, mit dem jedes Element in einem Vektor gelesen oder geändert werden kann.|  
|[Zeiger](#vector__pointer)|Ein Typ, der einen Zeiger auf ein Element in einem Vektor bereitstellt.|  
|[Referenz](#vector__reference)|Ein Typ, der einen Verweis auf ein in einem Vektor gespeichertes Element bereitstellt.|  
|[reverse_iterator](#vector__reverse_iterator)|Ein Typ, der einen Iterator mit zufälligem Zugriff bereitstellt, mit dem jedes Element in einem umgekehrten Vektor gelesen oder geändert werden kann.|  
|[size_type](#vector__size_type)|Ein Typ, der die Anzahl von Elementen in einem Vektor zählt.|  
|[Werttyp](#vector__value_type)|Ein Typ, der den in einem Vektor gespeicherten Datentyp darstellt.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[Zuweisen](#vector__assign)|Löscht einen Vektor und kopiert die angegebenen Elemente in den leeren Vektor.|  
|[am](#vector__at)|Gibt einen Verweis auf das Element an einer angegebenen Position in dem Vektor zurück.|  
|[Zurück](#vector__back)|Gibt einen Verweis auf das letzte Element des Vektors zurück.|  
|[beginnen](#vector__begin)|Gibt einen Iterator mit wahlfreiem Zugriff für das erste Element im Vektor zurück.|  
|[Kapazität](#vector__capacity)|Gibt die Anzahl von Elementen zurück, die der Vektor enthalten kann, ohne zusätzlichen Speicher zuzuweisen.|  
|[cbegin](#vector__cbegin)|Gibt einen const-Iterator mit wahlfreiem Zugriff für das erste Element im Vektor zurück.|  
|[cend](#vector__cend)|Gibt einen für wahlfreien Zugriff eingerichteten konstanten Iterator zurück, der unmittelbar hinter das Ende des Vektors zeigt.|  
|[crbegin](#vector__crbegin)|Gibt einen const-Iterator zum ersten Element in einem umgekehrten Vektor zurück.|  
|[crend](#vector__crend)|Gibt einen const-Iterator zum Ende eines umgekehrten Vektors zurück.|  
|[Deaktivieren](#vector__clear)|Löscht die Elemente des Vektors.|  
|[Daten](#vector__data)|Gibt einen Zeiger auf das erste Element im Vektor zurück.|  
|[emplace](#vector__emplace)|Fügt ein direkt konstruiertes Element an einer angegebenen Position in den Vektor ein.|  
|[emplace_back](#vector__emplace_back)|Fügt ein direkt konstruiertes Element am Ende des Vektors ein.|  
|[leere](#vector__empty)|Testet, ob der Vektorcontainer leer ist.|  
|[Ende](#vector__end)|Gibt einen Iterator mit wahlfreiem Zugriff zurück, der auf das Ende des Vektors zeigt.|  
|[zum Löschen des Bands](#vector__erase)|Entfernt ein Element oder eine Reihe von Elementen aus angegebenen Positionen in einem Vektor.|  
|[Vorderseite](#vector__front)|Gibt einen Verweis auf das erste Element in einem Vektor zurück.|  
|[get_allocator](#vector__get_allocator)|Gibt ein Objekt an die `allocator`-Klasse zurück, das von einem Vektor verwendet wird.|  
|[Einfügen](#vector__insert)|Fügt ein Element oder eine Reihe von Elementen an einer angegebenen Position in den Vektor ein.|  
|[max_size](#vector__max_size)|Gibt die Maximallänge des Vektors zurück.|  
|[pop_back](#vector__pop_back)|Löscht das Element am Ende des Vektors.|  
|[push_back](#vector__push_back)|Fügt ein Element am Ende des Vektors hinzu.|  
|[rbegin](#vector__rbegin)|Gibt einen Iterator an das erste Element in einem umgekeherten Vektor zurück.|  
|[REND](#vector__rend)|Gibt einen Iterator zum Ende eines umgekehrten Vektors zurück.|  
|[Reservieren](#vector__reserve)|Reserviert eine Mindestspeicherlänge für ein Vektorobjekt.|  
|[Ändern der Größe](#vector__resize)|Gibt eine neue Größe für einen Vektor an.|  
|[shrink_to_fit](#vector__shrink_to_fit)|Verwirft Überkapazität.|  
|[Größe](#vector__size)|Gibt die Anzahl von Elementen in dem Vektor zurück.|  
|[Swap](#vector__swap)|Tauscht die Elemente zweier Vektoren aus.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator &#91; &#93;](#vector__operator_at)|Gibt einen Verweis auf das Vektorelement an einer angegebenen Position zurück.|  
|[Operator =](#vector__operator_eq)|Ersetzt die Elemente des Vektors durch eine Kopie eines anderen Vektors.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \< Vektor>  
  
 **Namespace:** std  
  
##  <a name="a-namevectorallocatortypea-vectorallocatortype"></a><a name="vector__allocator_type"></a>  Vector:: allocator_type  
 Ein Typ, der die Zuweisungsklasse für das Vektorobjekt darstellt.  
  
```  
typedef Allocator allocator_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 `allocator_type` ist ein Synonym für den Vorlagenparameter **Zuweisung.**  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Get_allocator](#vector__get_allocator) ein Beispiel für die `allocator_type`.  
  
##  <a name="a-namevectorassigna-vectorassign"></a><a name="vector__assign"></a>  Vector:: Assign  
 Löscht einen Vektor und kopiert die angegebenen Elemente in den leeren Vektor.  
  
```  
void assign(
    size_type Count,  
    const Type& Val);

void assign(
    initializer_list<Type> IList);

template <class InputIterator>  
void assign(
    InputIterator First,  
    InputIterator Last);
```  
  
### <a name="parameters"></a>Parameter  
 `First`  
 Die Position des ersten Elements in dem zu kopierenden Elementbereich.  
  
 `Last`  
 Die Position des ersten Elements nach dem zu kopierenden Elementbereich.  
  
 `Count`  
 Die Anzahl von Kopien eines Elements, das in den Vektor eingefügt wird.  
  
 `Val`  
 Der Wert des Elements, das in den Vektor eingefügt wird.  
  
 `IList`  
 Das initializer_list-Element, in den die zu kopierenden Elemente eingefügt werden.  
  
### <a name="remarks"></a>Hinweise  
 Nachdem ein vorhandenes Elemente in einem Vektor gelöscht wurde, wird entweder "Einfügen eines angegebenen Elementbereichs aus dem ursprünglichen Vektor in einen Vektor" oder "Einfügen von Kopien eines neuen Elements eines angegebenen Werts in einen Vektor" zugewiesen.  
  
### <a name="example"></a>Beispiel  
  
```  
/ vector_assign.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    vector<int> v1, v2, v3;  
  
    v1.push_back(10);  
    v1.push_back(20);  
    v1.push_back(30);  
    v1.push_back(40);  
    v1.push_back(50);  
  
    cout << "v1 = ";  
    for (auto& v : v1){  
        cout << v << " ";  
    }  
    cout << endl;  
  
    v2.assign(v1.begin(), v1.end());  
    cout << "v2 = ";  
    for (auto& v : v2){  
        cout << v << " ";  
    }  
    cout << endl;  
  
    v3.assign(7, 4);  
    cout << "v3 = ";  
    for (auto& v : v3){  
        cout << v << " ";  
    }  
    cout << endl;  
  
    v3.assign({ 5, 6, 7 });  
    for (auto& v : v3){  
        cout << v << " ";  
    }  
    cout << endl;  
}  
  
```  
  
##  <a name="a-namevectorata-vectorat"></a><a name="vector__at"></a>  Vector:: at  
 Gibt einen Verweis auf das Element an einer angegebenen Position in dem Vektor zurück.  
  
```  
reference at(size_type _Pos);

const_reference at(size_type _Pos) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Pos`  
 Dier Feldindex oder Positionsnummer des Elements, das auf den Vektor verweisen soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das Element, das im Argument indiziert ist. Wenn `_Off` ist größer als die Größe des Vektors, **am** löst eine Ausnahme aus.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Rückgabewert der **am** zugewiesen ist eine `const_reference`, Vector-Objekt kann nicht geändert werden. Wenn der Rückgabewert der **am** zugewiesen ist eine **Verweis**, kann das Vektorobjekt geändert werden.  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_at.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
  
   const int &i = v1.at( 0 );  
   int &j = v1.at( 1 );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namevectorbacka-vectorback"></a><a name="vector__back"></a>  Vector:: Back  
 Gibt einen Verweis auf das letzte Element des Vektors zurück.  
  
```  
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das letzte Element des Vektors. Wenn der Vektor leer ist, ist der Rückgabewert nicht definiert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Rückgabewert von **wieder** zugewiesen ist ein `const_reference`, das Vektorobjekt nicht geändert werden. Wenn der Rückgabewert von **wieder** zugewiesen ist eine **Verweis**, kann das Vektorobjekt geändert werden.  
  
 Beim Kompilieren mit _SECURE_SCL 1 tritt ein Laufzeitfehler auf, wenn Sie versuchen, auf ein Element in einem leeren Vektor zuzugreifen.  Weitere Informationen finden Sie unter [Checked Iterators](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_back.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main() {  
   using namespace std;     
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 11 );  
  
   int& i = v1.back( );  
   const int& ii = v1.front( );  
  
   cout << "The last integer of v1 is " << i << endl;  
   i--;  
   cout << "The next-to-last integer of v1 is "<< ii << endl;  
}  
```  
  
##  <a name="a-namevectorbegina-vectorbegin"></a><a name="vector__begin"></a>  Vector:: begin  
 Gibt einen Iterator mit wahlfreiem Zugriff für das erste Element im Vektor zurück.  
  
```  
const_iterator begin() const;

 
iterator begin();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator mit zufälligem Zugriff, das erste Element in der `vector` oder auf den Speicherort adressiert, der eine leere `vector`. Sie sollten stets den Rückgabewert mit vergleichen [Vector:: End](#vector__end) um sicherzustellen, dass er gültig ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Rückgabewert der `begin` zugewiesen ist eine [Vector:: const_iterator](#vector__const_iterator), die `vector` -Objekt nicht geändert werden. Wenn der Rückgabewert der `begin` zugewiesen ist ein [Vector:: Iterator](#vector__iterator), die `vector` -Objekt bearbeitet werden können.  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_begin.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    vector<int> c1;  
    vector<int>::iterator c1_Iter;  
    vector<int>::const_iterator c1_cIter;  
  
    c1.push_back(1);  
    c1.push_back(2);  
  
    cout << "The vector c1 contains elements:";  
    c1_Iter = c1.begin();  
    for (; c1_Iter != c1.end(); c1_Iter++)  
    {  
        cout << " " << *c1_Iter;  
    }  
    cout << endl;  
  
    cout << "The vector c1 now contains elements:";  
    c1_Iter = c1.begin();  
 *c1_Iter = 20;  
    for (; c1_Iter != c1.end(); c1_Iter++)  
    {  
        cout << " " << *c1_Iter;  
    }  
    cout << endl;  
  
    // The following line would be an error because iterator is const  
    // *c1_cIter = 200;  
}  
```  
  
```Output  
The vector c1 contains elements: 1 2  
The vector c1 now contains elements: 20 2  
```  
  
##  <a name="a-namevectorcapacitya-vectorcapacity"></a><a name="vector__capacity"></a>  Vector:: Capacity  
 Gibt die Anzahl von Elementen zurück, die der Vektor enthalten kann, ohne zusätzlichen Speicher zuzuweisen.  
  
```  
size_type capacity() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Speicherlänge, die für den Vektor zugewiesen wurde.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion [Größe](#vector__resize) effizienter, wenn ausreichend Arbeitsspeicher zugeordnet wird, angepasst werden. Verwenden Sie die Memberfunktion [reservieren](#vector__reserve) die Größe des Arbeitsspeichers angeben.  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_capacity.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector <int> v1;  
  
   v1.push_back( 1 );  
   cout << "The length of storage allocated is "  
        << v1.capacity( ) << "." << endl;  
  
   v1.push_back( 2 );  
   cout << "The length of storage allocated is now "  
        << v1.capacity( ) << "." << endl;  
}  
```  
  
```Output  
The length of storage allocated is 1.  
The length of storage allocated is now 2.  
```  
  
##  <a name="a-namevectorcbegina-vectorcbegin"></a><a name="vector__cbegin"></a>  Vector:: cbegin  
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
  
##  <a name="a-namevectorcenda-vectorcend"></a><a name="vector__cend"></a>  Vector:: cend  
 Gibt einen `const`-Iterator zurück, der den Speicherort adressiert, der dem letzten Element eines Bereichs unmittelbar nachfolgt.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen `const`-Random-Access-Iterator zurück, der auf eine Position unmittelbar hinter dem Ende des Bereichs verweist.  
  
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
  
##  <a name="a-namevectorcleara-vectorclear"></a><a name="vector__clear"></a>  Vector:: Clear  
 Löscht die Elemente des Vektors.  
  
```  
void clear();
```  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_clear.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
   v1.push_back( 30 );  
  
   cout << "The size of v1 is " << v1.size( ) << endl;  
   v1.clear( );  
   cout << "The size of v1 after clearing is " << v1.size( ) << endl;  
}  
```  
  
```Output  
The size of v1 is 3  
The size of v1 after clearing is 0  
```  
  
##  <a name="a-namevectorconstiteratora-vectorconstiterator"></a><a name="vector__const_iterator"></a>  Vector:: const_iterator  
 Ein Typ, der einem Iterator mit wahlfreiem Zugriff, können bietet Lesen einer **const** Element in einem Vektor.  
  
```  
typedef implementation-defined const_iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Ein `const_iterator`-Typ kann nicht zum Ändern des Werts eines Elements verwendet werden.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [wieder](#vector__back) ein Beispiel für die `const_iterator`.  
  
##  <a name="a-namevectorconstpointera-vectorconstpointer"></a><a name="vector__const_pointer"></a>  Vector:: const_pointer  
 Ein Typ, der ein Zeiger auf eine **const** Element in einem Vektor.  
  
```  
typedef typename Allocator::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>Hinweise  
 Ein `const_pointer`-Typ kann nicht zum Ändern des Werts eines Elements verwendet werden.  
  
 Ein [Iterator](#vector__iterator) wird häufiger für den Zugriff auf ein Vektorelement verwendet.  
  
##  <a name="a-namevectorconstreferencea-vectorconstreference"></a><a name="vector__const_reference"></a>  Vector:: const_reference  
 Ein Typ, der einen Verweis auf eine **const** Element in einem Vektor zum Lesen und Ausführen von gespeicherten **const** Vorgänge.  
  
```  
typedef typename Allocator::const_reference const_reference;  
```  
  
### <a name="remarks"></a>Hinweise  
 Ein `const_reference`-Typ kann nicht zum Ändern des Werts eines Elements verwendet werden.  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_const_ref.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
  
   const vector <int> v2 = v1;  
   const int &i = v2.front( );  
   const int &j = v2.back( );  
   cout << "The first element is " << i << endl;  
   cout << "The second element is " << j << endl;  
  
   // The following line would cause an error as v2 is const  
   // v2.push_back( 30 );  
}  
```  
  
```Output  
The first element is 10  
The second element is 20  
```  
  
##  <a name="a-namevectorconstreverseiteratora-vectorconstreverseiterator"></a><a name="vector__const_reverse_iterator"></a>  Vector:: const_reverse_iterator  
 Eine Typ, der einem Iterator mit wahlfreiem Zugriff, können bietet gelesen **const** Element im Vektor.  
  
```  
typedef std::reverse_iterator<const_iterator> const_reverse_iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Ein `const_reverse_iterator` kann nicht den Wert eines Elements ändern und wird verwendet, um den Vektor in umgekehrter Reihenfolge durchlaufen.  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter [Rbegin](#vector__rbegin) für ein Beispiel für das Deklarieren und verwenden einen Iterator.  
  
##  <a name="a-namevectorcrbegina-vectorcrbegin"></a><a name="vector__crbegin"></a>  Vector:: crbegin  
 Gibt einen const-Iterator zum ersten Element in einem umgekehrten Vektor zurück.  
  
```  
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Const reverse-Iterator mit wahlfreiem Zugriff das erste Element in einer umgekehrten adressiert [Vektor](vector%20Class.md) oder nach dem letzten Element in der nicht umgekehrten adressiert `vector`.  
  
### <a name="remarks"></a>Hinweise  
 Bei dem Rückgabewert von `crbegin` kann das `vector`-Objekt nicht geändert werden.  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_crbegin.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::iterator v1_Iter;  
   vector <int>::const_reverse_iterator v1_rIter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   v1_Iter = v1.begin( );  
   cout << "The first element of vector is "  
        << *v1_Iter << "." << endl;  
  
   v1_rIter = v1.crbegin( );  
   cout << "The first element of the reversed vector is "  
        << *v1_rIter << "." << endl;  
}  
```  
  
```Output  
The first element of vector is 1.  
The first element of the reversed vector is 2.  
```  
  
##  <a name="a-namevectorcrenda-vectorcrend"></a><a name="vector__crend"></a>  Vector:: crend  
 Gibt einen Konstanten Iterator, der den Speicherort adressiert, das letzte Element in einem umgekehrten Vektor zurück.  
  
```  
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Const reverse-Iterator mit wahlfreiem Zugriff, der den Speicherort adressiert, das letzte Element in einer umgekehrten adressiert [Vektor](vector%20Class.md) (der Speicherort, der das erste Element in der nicht umgekehrten vorangegangen war `vector`).  
  
### <a name="remarks"></a>Hinweise  
 `crend` wird verwendet, mit einer umgekehrten `vector` wie [Vector:: cend](#vector__cend) wird verwendet, mit einer `vector`.  
  
 Mit dem Rückgabewert der `crend` (entsprechend dekrementiert), die `vector` -Objekt nicht geändert werden.  
  
 `crend` kann verwendet werden, um zu testen, ob das Ende der `vector` von einem umgekehrten Iterator erreicht wurde.  
  
 Der von `crend` zurückgegebene Wert darf nicht dereferenziert werden.  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_crend.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::const_reverse_iterator v1_rIter;  
  
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
  
##  <a name="a-namevectordataa-vectordata"></a><a name="vector__data"></a>  Vector Data  
 Gibt einen Zeiger auf das erste Element im Vektor zurück.  
  
```  
const_pointer data() const;

 
pointer data();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das erste Element in der [Vektor](vector%20Class.md) oder auf den Speicherort adressiert, der eine leere `vector`.  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_data.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    vector<int> c1;  
    vector<int>::pointer c1 ptr;  
    vector<int>::const_pointer c1_cPtr;  
  
    c1.push_back(1);  
    c1.push_back(2);  
  
    cout << "The vector c1 contains elements:";  
    c1_cPtr = c1.data();  
    for (size_t n = c1.size(); 0 < n; --n, c1_cPtr++)  
    {  
        cout << " " << *c1_cPtr;  
    }  
    cout << endl;  
  
    cout << "The vector c1 now contains elements:";  
    c1 ptr = c1.data();  
 *c1 ptr = 20;  
    for (size_t n = c1.size(); 0 < n; --n, c1 ptr++)  
    {  
        cout << " " << *c1 ptr;  
    }  
    cout << endl;  
}  
```  
  
```Output  
The vector c1 contains elements: 1 2  
The vector c1 now contains elements: 20 2  
```  
  
##  <a name="a-namevectordifferencetypea-vectordifferencetype"></a><a name="vector__difference_type"></a>  Vector:: difference_type  
 Ein Typ, der den Unterschied zwischen zwei Iteratoren, die auf Elemente innerhalb desselben Vektors verweisen, bereitstellt.  
  
```  
typedef typename Allocator::difference_type difference_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Ein `difference_type` kann auch als die Anzahl der Elemente zwischen zwei Zeigern beschrieben werden, da ein Zeiger auf ein Element, dessen Adresse enthält.  
  
 Ein [Iterator](#vector__iterator) wird häufiger für den Zugriff auf ein Vektorelement verwendet.  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_diff_type.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <vector>  
#include <algorithm>  
  
int main( )  
{  
   using namespace std;  
  
   vector <int> c1;  
   vector <int>::iterator c1_Iter, c2_Iter;  
  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
   c1.push_back( 30 );  
   c1.push_back( 10 );  
   c1.push_back( 30 );  
   c1.push_back( 20 );  
  
   c1_Iter = c1.begin( );  
   c2_Iter = c1.end( );  
  
   vector <int>::difference_type   df_typ1, df_typ2, df_typ3;  
  
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
  
##  <a name="a-namevectoremplacea-vectoremplace"></a><a name="vector__emplace"></a>  Vector emplace  
 Fügt ein direkt konstruiertes Element an einer angegebenen Position in den Vektor ein.  
  
```  
iterator emplace(
    const_iterator _Where,  
    Type&& val);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|`_Where`|Die Position in der [Vektor](vector%20Class.md) in dem das erste Element eingefügt wird.|  
|` val`|Der Wert des Elements, das in den `vector` eingefügt wird.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die Funktion gibt einen Iterator zurück, der auf den Speicherort zeigt, an dem das neue Element in den `vector` eingefügt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Jeder Einfügevorgang kann teuer sein, siehe [vector-Klasse](vector%20Class.md) eine Erläuterung der `vector` Leistung.  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_emplace.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::iterator Iter;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
   v1.push_back( 30 );  
  
   cout << "v1 =" ;  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
// initialize a vector of vectors by moving v1  
   vector < vector <int> > vv1;  
  
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
  
##  <a name="a-namevectoremplacebacka-vectoremplaceback"></a><a name="vector__emplace_back"></a>  Vector emplace_back  
 Fügt ein direkt konstruiertes Element am Ende des Vektors ein.  
  
```  
template <class... Types>  
void emplace_back(Types&&... _Args);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`_Args`|Konstruktorargumente Die Funktion leitet auf Grundlage der bereitgestellten Argumente die erforderliche die Konstruktorüberladung ab.|  
  
### <a name="example"></a>Beispiel  
  
```cpp  
  
#include <vector>  
struct obj  
{  
   obj(int, double) {}  
};  
  
int main()  
{  
   std::vector<obj> v;  
   v.emplace_back(1, 3.14); // obj in created in place in the vector  
}  
  
```  
  
##  <a name="a-namevectoremptya-vectorempty"></a><a name="vector__empty"></a>  Vector:: Empty  
 Testet, ob der Vektor leer ist.  
  
```  
bool empty() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 **true** Wenn der Vektor leer, andernfalls ist **false** Wenn der Vektor nicht leer ist.  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_empty.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
  
   v1.push_back( 10 );  
  
   if ( v1.empty( ) )  
      cout << "The vector is empty." << endl;  
   else  
      cout << "The vector is not empty." << endl;  
}  
```  
  
```Output  
The vector is not empty.  
```  
  
##  <a name="a-namevectorenda-vectorend"></a><a name="vector__end"></a>  Vector:: End  
 Gibt den "past-the-end"-Iterator zurück.  
  
```  
iterator end();

const_iterator end() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der "past-the-end"-Iterator für den Vektor. Wenn der Vektor leer ist, dann gilt `vector::end() == vector::begin()`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Rückgabewert von **End** wird eine Variable vom Typ zugewiesen `const_iterator`, Vector-Objekt kann nicht geändert werden. Wenn der Rückgabewert von **End** wird eine Variable vom Typ zugewiesen **Iterator**, kann das Vektorobjekt geändert werden.  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_end.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
int main( )  
{  
   using namespace std;  
   vector <int> v1;  
   vector <int>::iterator v1_Iter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   for ( v1_Iter = v1.begin( ) ; v1_Iter != v1.end( ) ; v1_Iter++ )  
      cout << *v1_Iter << endl;  
}  
```  
  
```Output  
1  
2  
```  
  
##  <a name="a-namevectorerasea-vectorerase"></a><a name="vector__erase"></a>  Vector:: Erase  
 Entfernt ein Element oder eine Reihe von Elementen aus angegebenen Positionen in einem Vektor.  
  
```  
iterator erase(
    const_iterator _Where);

iterator erase(
    const_iterator first,  
    const_iterator last);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|`_Where`|Die Position des von dem Vektor zu entfernenden Elements.|  
|` first`|Die Position des ersten Elements, das von dem Vektor entfernt werden soll.|  
|` last`|Die Position direkt hinter dem letzten von dem Vektor entfernten Element.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator, der das erste über die entfernten Elemente hinaus verbliebene Element festlegt, oder ein Zeiger, der das Ende des Vektors darstellt, wenn kein solches Element vorhanden ist.  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_erase.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::iterator Iter;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
   v1.push_back( 30 );  
   v1.push_back( 40 );  
   v1.push_back( 50 );  
  
   cout << "v1 =" ;  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
   v1.erase( v1.begin( ) );  
   cout << "v1 =";  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
   v1.erase( v1.begin( ) + 1, v1.begin( ) + 3 );  
   cout << "v1 =";  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
}  
```  
  
```Output  
v1 = 10 20 30 40 50  
v1 = 20 30 40 50  
v1 = 20 50  
```  
  
##  <a name="a-namevectorfronta-vectorfront"></a><a name="vector__front"></a>  Vector:: Front  
 Gibt einen Verweis auf das erste Element in einem Vektor zurück.  
  
```  
reference front();

const_reference front() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das erste Element im Vektorobjekt. Wenn der Vektor leer ist, ist die Rückgabe nicht definiert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `front` dem Rückgabewert von `const_reference` zugewiesen wird, kann das Vektorobjekt nicht geändert werden. Wenn der Rückgabewert der `front` zugewiesen ist eine **Verweis**, kann das Vektorobjekt geändert werden.  
  
 Beim Kompilieren mit _SECURE_SCL 1 tritt ein Laufzeitfehler auf, wenn Sie versuchen, auf ein Element in einem leeren Vektor zuzugreifen.  Weitere Informationen finden Sie unter [Checked Iterators](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_front.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 11 );  
  
   int& i = v1.front( );  
   const int& ii = v1.front( );  
  
   cout << "The first integer of v1 is "<< i << endl;  
   // by incrementing i, we move the the front reference to the second element  
   i++;  
   cout << "Now, the first integer of v1 is "<< i << endl;  
}  
```  
  
##  <a name="a-namevectorgetallocatora-vectorgetallocator"></a><a name="vector__get_allocator"></a>  Vector:: get_allocator  
 Gibt eine Kopie des zuweisungsobjekts verwendet, um den Vektor zu erstellen.  
  
```  
Allocator get_allocator() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die von dem Vektor verwendete Zuweisung.  
  
### <a name="remarks"></a>Hinweise  
 Zuweisungen für die Vector-Klasse geben an, wie die Klasse Speicher verwaltet. Für die meisten Programmieranforderungen reichen die Standard-Zuweisungen mit STL-Container-Klassen aus. Schreiben und Verwenden Ihrer eigener Zuweisungsklasse ist ein C++ -Thema für Fortgeschrittene.  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_get_allocator.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   // The following lines declare objects that use the default allocator.  
   vector<int> v1;  
   vector<int, allocator<int> > v2 = vector<int, allocator<int> >(allocator<int>( )) ;  
  
   // v3 will use the same allocator class as v1  
   vector <int> v3( v1.get_allocator( ) );  
  
   vector<int>::allocator_type xvec = v3.get_allocator( );  
   // You can now call functions on the allocator class used by vec  
}  
```  
  
##  <a name="a-namevectorinserta-vectorinsert"></a><a name="vector__insert"></a>  Vector:: Insert  
 Fügt ein Element oder mehrere Elemente oder ein Reihe von Elementen an einer bestimmten Position in den Vektor ein.  
  
```  
iterator insert(
    const_iterator _Where,  
    const Type& val);

iterator insert(
    const_iterator _Where,  
    Type&& val);

void insert(
    const_iterator _Where,  
    size_type count,  
    const Type& val);

template <class InputIterator>  
void insert(
    const_iterator _Where,  
    InputIterator first,  
    InputIterator last);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|`_Where`|Die Position in dem Vektor, an der das erste Element eingefügt wird.|  
|` val`|Der Wert des Elements, das in den Vektor eingefügt wird.|  
|` count`|Die Anzahl von Elementen, die in den Vektor eingefügt werden.|  
|` first`|Die Position des ersten Elements in dem zu kopierenden Elementbereich.|  
|` last`|Die Position des ersten Elements nach dem zu kopierenden Elementbereich.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die ersten zwei `insert`-Funktionen geben einen Iterator zurück, der auf den Speicherort zeigt, an dem das neue Element in den Vektor eingefügt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Jeder Einfügevorgang kann teuer sein, siehe [vector-Klasse](vector%20Class.md) eine Erläuterung der `vector` Leistung.  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_insert.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::iterator Iter;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
   v1.push_back( 30 );  
  
   cout << "v1 =" ;  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
   v1.insert( v1.begin( ) + 1, 40 );  
   cout << "v1 =";  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
   v1.insert( v1.begin( ) + 2, 4, 50 );  
  
   cout << "v1 =";  
   for ( Iter = v1.begin( ) ; Iter != v1.end( ) ; Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
   v1.insert( v1.begin( )+1, v1.begin( )+2, v1.begin( )+4 );  
   cout << "v1 =";  
   for (Iter = v1.begin( ); Iter != v1.end( ); Iter++ )  
      cout << " " << *Iter;  
   cout << endl;  
  
// initialize a vector of vectors by moving v1  
   vector < vector <int> > vv1;  
  
   vv1.insert( vv1.begin(), move( v1 ) );  
   if ( vv1.size( ) != 0 && vv1[0].size( ) != 0 )  
      {  
      vector < vector <int> >::iterator Iter;  
      cout << "vv1[0] =";  
      for (Iter = vv1[0].begin( ); Iter != vv1[0].end( ); Iter++ )  
         cout << " " << *Iter;  
      cout << endl;  
      }  
}  
```  
  
```Output  
v1 = 10 20 30  
v1 = 10 40 20 30  
v1 = 10 40 50 50 50 50 20 30  
v1 = 10 50 50 40 50 50 50 50 20 30  
vv1[0] = 10 50 50 40 50 50 50 50 20 30  
```  
  
##  <a name="a-namevectoriteratora-vectoriterator"></a><a name="vector__iterator"></a>  Vector:: Iterator  
 Ein Typ, der einen Iterator mit wahlfreiem Zugriff bereitstellt, mit dem jedes Element in einem Vektor gelesen oder geändert werden kann.  
  
```  
typedef implementation-defined iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Ein Typ **Iterator** kann zum Ändern des Werts eines Elements verwendet werden.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [beginnen](#vector__begin).  
  
##  <a name="a-namevectormaxsizea-vectormaxsize"></a><a name="vector__max_size"></a>  Vector:: max_size  
 Gibt die Maximallänge des Vektors zurück.  
  
```  
size_type max_size() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die mögliche Maximallänge des Vektors.  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_max_size.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::size_type i;  
  
   i = v1.max_size( );     
   cout << "The maximum possible length of the vector is " << i << "." << endl;  
}  
```  
  
##  <a name="a-namevectoroperatorata-vectoroperator"></a><a name="vector__operator_at"></a>  Vector:: Operator]  
 Gibt einen Verweis auf das Vektorelement an einer angegebenen Position zurück.  
  
```  
reference operator[](size_type Pos);

const_reference operator[](size_type Pos) const;
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|`Pos`|Die Position des angegebenen Vektorelements.|  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die angegebene Position größer oder gleich der Größe des Containers ist, ist das Ergebnis nicht definiert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `operator[]` dem Rückgabewert von `const_reference` zugewiesen wird, kann das Vektorobjekt nicht geändert werden. Wenn der Rückgabewert von `operator[]` einem Verweis zugewiesen wird, kann das Vektorobjekt geändert werden.  
  
 Beim Kompilieren mit _SECURE_SCL 1 (gesteuert, die mit [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)), tritt ein Laufzeitfehler auf, wenn Sie versuchen, ein Element außerhalb der Grenzen des Vektors zuzugreifen.  Weitere Informationen finden Sie unter [Checked Iterators](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// vector_op_ref.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
  
   v1.push_back( 10 );  
   v1.push_back( 20 );  
  
   int& i = v1[1];  
   cout << "The second integer of v1 is " << i << endl;  
}  
```  
  
##  <a name="a-namevectoroperatoreqa-vectoroperator"></a><a name="vector__operator_eq"></a>  Vector:: Operator =  
 Ersetzt die Elemente des Vektors durch eine Kopie eines anderen Vektors.  
  
```  
vector& operator=(const vector& right);

vector& operator=(vector&& right);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|` right`|Der [Vektor](vector%20Class.md) kopiert werden, in der `vector`.|  
  
### <a name="remarks"></a>Hinweise  
 Nachdem ein vorhandenes Element in einem `vector` gelöscht wurde, kopiert oder verschiebt `operator=` den Inhalt von ` right` in den `vector`.  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_operator_as.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector<int> v1, v2, v3;  
   vector<int>::iterator iter;  
  
   v1.push_back(10);  
   v1.push_back(20);  
   v1.push_back(30);  
   v1.push_back(40);  
   v1.push_back(50);  
  
   cout << "v1 = " ;  
   for (iter = v1.begin(); iter != v1.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
  
   v2 = v1;  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
  
// move v1 into v2  
   v2.clear();  
   v2 = move(v1);  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << *iter << " ";  
   cout << endl;  
}  
```  
  
##  <a name="a-namevectorpointera-vectorpointer"></a><a name="vector__pointer"></a>  Vector:: Pointer  
 Ein Typ, der einen Zeiger auf ein Element in einem Vektor bereitstellt.  
  
```  
typedef typename Allocator::pointer pointer;  
```  
  
### <a name="remarks"></a>Hinweise  
 Ein Typ **Zeiger** kann zum Ändern des Werts eines Elements verwendet werden.  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_pointer.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector<int> v;  
   v.push_back( 11 );  
   v.push_back( 22 );  
  
   vector<int>::pointer ptr = &v[0];  
   cout << *ptr << endl;  
   ptr++;  
   cout << *ptr << endl;  
 *ptr = 44;  
   cout << *ptr << endl;  
}  
```  
  
```Output  
11  
22  
44  
```  
  
##  <a name="a-namevectorpopbacka-vectorpopback"></a><a name="vector__pop_back"></a>  Vector:: pop_back  
 Löscht das Element am Ende des Vektors.  
  
```  
void pop_back();
```  
  
### <a name="remarks"></a>Hinweise  
 Ein Codebeispiel finden Sie unter [Vector::push_back()](#vector__push_back).  
  
##  <a name="a-namevectorpushbacka-vectorpushback"></a><a name="vector__push_back"></a>  Vector:: push_back  
 Fügt ein Element am Ende des Vektors hinzu.  
  
```  
void push_back(const T& Val);

 
void push_back(T&& Val);
```  
  
### <a name="parameters"></a>Parameter  
 `Val`  
 Der Wert, der dem am Ende des Vektors hinzugefügten Element zugewiesen werden soll.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// compile with: /EHsc /W4  
#include <vector>  
#include <iostream>  
  
using namespace std;  
  
template <typename T> void print_elem(const T& t) {  
    cout << "(" << t << ") ";  
}  
  
template <typename T> void print_collection(const T& t) {  
    cout << "  " << t.size() << " elements: ";  
  
    for (const auto& p : t) {  
        print_elem(p);  
    }  
    cout << endl;  
}  
  
int main()  
{  
    vector<int> v;  
    for (int i = 0; i < 10; ++i) {  
        v.push_back(10 + i);  
    }  
  
    cout << "vector data: " << endl;  
    print_collection(v);  
  
    // pop_back() until it's empty, printing the last element as we go  
    while (v.begin() != v.end()) {   
        cout << "v.back(): "; print_elem(v.back()); cout << endl;  
        v.pop_back();  
    }  
}  
```  
  
##  <a name="a-namevectorrbegina-vectorrbegin"></a><a name="vector__rbegin"></a>  Vector:: rbegin  
 Gibt einen Iterator an das erste Element in einem umgekeherten Vektor zurück.  
  
```  
reverse_iterator rbegin();

const_reverse_iterator rbegin() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein umgekehrter Iterator mit wahlfreiem Zugriff, der das erste Element in einem umgekehrten Vektor oder nach dem letzten Element in der nicht umgekehrten Vektor adressiert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `rbegin` dem Rückgabewert von `const_reverse_iterator` zugewiesen wird, kann das Vektorobjekt nicht geändert werden. Wenn der Rückgabewert der `rbegin` zugewiesen ist eine `reverse_iterator`, kann das Vektorobjekt geändert werden.  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_rbegin.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::iterator v1_Iter;  
   vector <int>::reverse_iterator v1_rIter;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
  
   v1_Iter = v1.begin( );  
   cout << "The first element of vector is "  
        << *v1_Iter << "." << endl;  
  
   v1_rIter = v1.rbegin( );  
   cout << "The first element of the reversed vector is "  
        << *v1_rIter << "." << endl;  
}  
```  
  
```Output  
The first element of vector is 1.  
The first element of the reversed vector is 2.  
```  
  
##  <a name="a-namevectorreferencea-vectorreference"></a><a name="vector__reference"></a>  Vector:: Reference  
 Ein Typ, der einen Verweis auf ein in einem Vektor gespeichertes Element bereitstellt.  
  
```  
typedef typename Allocator::reference reference;  
```  
  
### <a name="example"></a>Beispiel  
  Finden Sie unter [auf](#vector__at) ein Beispiel zum Verwenden von **Verweis** im Vector-Klasse.  
  
##  <a name="a-namevectorrenda-vectorrend"></a><a name="vector__rend"></a>  Vector:: rend  
 Gibt einen Iterator, der den Speicherort adressiert, das letzte Element in einem umgekehrten Vektor zurück.  
  
```  
const_reverse_iterator rend() const;

reverse_iterator rend();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein umgekehrter Iterator mit zufälligem Zugriff, der nachfolgt das letzte Element in einem umgekehrten Vektor (der Speicherort, der das erste Element in der nicht umgekehrten Vektor vorangegangen war).  
  
### <a name="remarks"></a>Hinweise  
 `rend` Bei einer umgekehrten Vektor verwendet wird wie [End](#vector__end) bei einer Vektor verwendet wird.  
  
 Wenn der Rückgabewert der `rend` zugewiesen ist eine `const_reverse_iterator`, und klicken Sie dann das Vektorobjekt geändert werden kann. Wenn der Rückgabewert der `rend` zugewiesen ist eine `reverse_iterator`, und klicken Sie dann das Vektorobjekt geändert werden kann.  
  
 `rend` kann verwendet werden, um zu testen, ob ein reverse-Iterator das Ende seiner Vektor erreicht wurde.  
  
 Der von `rend` zurückgegebene Wert darf nicht dereferenziert werden.  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_rend.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::reverse_iterator v1_rIter;  
  
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
  
##  <a name="a-namevectorreservea-vectorreserve"></a><a name="vector__reserve"></a>  Vector:: Reserve  
 Reserviert eine Mindestlänge von Speicher für ein Vektorobjekt und weist Speicherplatz zu, falls erforderlich.  
  
```  
void reserve(size_type count);
```  
  
### <a name="parameters"></a>Parameter  
 ` count`  
 Die minimale Speicherlänge, die für für den Vektor zugeordnet werden soll.  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_reserve.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   //vector <int>::iterator Iter;  
  
   v1.push_back( 1 );  
   cout << "Current capacity of v1 = "   
      << v1.capacity( ) << endl;  
   v1.reserve( 20 );  
   cout << "Current capacity of v1 = "   
      << v1.capacity( ) << endl;  
}  
```  
  
```Output  
Current capacity of v1 = 1  
Current capacity of v1 = 20  
```  
  
##  <a name="a-namevectorresizea-vectorresize"></a><a name="vector__resize"></a>  Vector:: Resize  
 Gibt eine neue Größe für einen Vektor an.  
  
```  
void resize(size_type Newsize);

void resize(size_type Newsize, Type Val);
```  
  
### <a name="parameters"></a>Parameter  
 `Newsize`  
 Die neue Größe des Vektors.  
  
 `Val`  
 Der Initialisierungswert für neue Elemente, der zum Vektor hinzugefügt wird, wenn die neue Größe die Originalgröße übersteigt. Wenn der Wert ausgelassen wird, verwenden die neuen Objekte ihren Standardkonstruktor.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Größe der Liste unter der angeforderte Größe liegt, werden dem Vektor `Newsize`-Elemente hinzugefügt, bis er die angeforderte Größe erreicht. Wenn die Größe des Containers die angeforderte Größe übersteigt, werden die Elemente, die dem Ende des Containers am nächsten sind, gelöscht, bis der Container die Größe `Newsize` erreicht. Wenn die tatsächliche Größe des Containers der angeforderten Größe entspricht, wird keine Aktion durchgeführt.  
  
 [Größe](#vector__size) Gibt die aktuelle Größe des Vektors wider.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// vectorsizing.cpp  
// compile with: /EHsc /W4  
// Illustrates vector::reserve, vector::max_size,  
// vector::resize, vector::resize, and vector::capacity.  
//  
// Functions:  
//  
//    vector::max_size - Returns maximum number of elements vector could  
//                       hold.  
//  
//    vector::capacity - Returns number of elements for which memory has  
//                       been allocated.  
//  
//    vector::size - Returns number of elements in the vector.  
//  
//    vector::resize - Reallocates memory for vector, preserves its  
//                     contents if new size is larger than existing size.  
//  
//    vector::reserve - Allocates elements for vector to ensure a minimum  
//                      size, preserving its contents if the new size is  
//                      larger than existing size.  
//  
//    vector::push_back - Appends (inserts) an element to the end of a  
//                        vector, allocating memory for it if necessary.  
//  
//////////////////////////////////////////////////////////////////////  
  
// The debugger cannot handle symbols more than 255 characters long.  
// STL often creates symbols longer than that.  
// The warning can be disabled:  
//#pragma warning(disable:4786)  
  
#include <iostream>  
#include <vector>  
#include <string>  
  
using namespace std;  
  
template <typename C> void print(const string& s, const C& c) {  
    cout << s;  
  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
    cout << endl;  
}  
  
void printvstats(const vector<int>& v) {  
    cout << "   the vector's size is: " << v.size() << endl;  
    cout << "   the vector's capacity is: " << v.capacity() << endl;  
    cout << "   the vector's maximum size is: " << v.max_size() << endl;  
}  
  
int main()  
{  
    // declare a vector that begins with 0 elements.  
    vector<int> v;  
  
    // Show statistics about vector.  
    cout << endl << "After declaring an empty vector:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    // Add one element to the end of the vector.  
    v.push_back(-1);  
    cout << endl << "After adding an element:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    for (int i = 1; i < 10; ++i) {  
        v.push_back(i);  
    }  
    cout << endl << "After adding 10 elements:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    v.resize(6);  
    cout << endl << "After resizing to 6 elements without an initialization value:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    v.resize(9, 999);  
    cout << endl << "After resizing to 9 elements with an initialization value of 999:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    v.resize(12);  
    cout << endl << "After resizing to 12 elements without an initialization value:" << endl;  
    printvstats(v);  
    print("   the vector's contents: ", v);  
  
    // Ensure there's room for at least 1000 elements.  
    v.reserve(1000);  
    cout << endl << "After vector::reserve(1000):" << endl;  
    printvstats(v);  
  
    // Ensure there's room for at least 2000 elements.  
    v.resize(2000);  
    cout << endl << "After vector::resize(2000):" << endl;  
    printvstats(v);  
}  
```  
  
##  <a name="a-namevectorreverseiteratora-vectorreverseiterator"></a><a name="vector__reverse_iterator"></a>  Vector:: reverse_iterator  
 Ein Typ, der einen Iterator mit zufälligem Zugriff bereitstellt, mit dem jedes Element in einem umgekehrten Vektor gelesen oder geändert werden kann.  
  
```  
typedef std::reverse_iterator<iterator> reverse_iterator;  
```  
  
### <a name="remarks"></a>Hinweise  
 Ein `reverse_iterator`-Typ wird verwendet, um den Vektor in umgekehrter Reihenfolge zu durchlaufen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Rbegin](#vector__rbegin).  
  
##  <a name="a-namevectorshrinktofita-vectorshrinktofit"></a><a name="vector__shrink_to_fit"></a>  Vector shrink_to_fit  
 Verwirft Überkapazität.  
  
```  
void shrink_to_fit();
```  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_shrink_to_fit.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   //vector <int>::iterator Iter;  
  
   v1.push_back( 1 );  
   cout << "Current capacity of v1 = "   
      << v1.capacity( ) << endl;  
   v1.reserve( 20 );  
   cout << "Current capacity of v1 = "   
      << v1.capacity( ) << endl;  
   v1.shrink_to_fit();  
   cout << "Current capacity of v1 = "   
      << v1.capacity( ) << endl;  
}  
```  
  
```Output  
Current capacity of v1 = 1  
Current capacity of v1 = 20  
Current capacity of v1 = 1  
```  
  
##  <a name="a-namevectorsizea-vectorsize"></a><a name="vector__size"></a>  Vector:: Size  
 Gibt die Anzahl von Elementen in dem Vektor zurück.  
  
```  
size_type size() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Länge des Vektors.  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_size.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1;  
   vector <int>::size_type i;  
  
   v1.push_back( 1 );  
   i = v1.size( );  
   cout << "Vector length is " << i << "." << endl;  
  
   v1.push_back( 2 );  
   i = v1.size( );  
   cout << "Vector length is now " << i << "." << endl;  
}  
```  
  
```Output  
Vector length is 1.  
Vector length is now 2.  
```  
  
##  <a name="a-namevectorsizetypea-vectorsizetype"></a><a name="vector__size_type"></a>  Vector:: size_type  
 Ein Typ, der die Anzahl von Elementen in einem Vektor zählt.  
  
```  
typedef typename Allocator::size_type size_type;  
```  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Kapazität](#vector__capacity).  
  
##  <a name="a-namevectorswapa-vectorswap"></a><a name="vector__swap"></a>  Vector:: Swap  
 Tauscht die Elemente zweier Vektoren aus.  
  
```  
void swap(
    vector<Type, Allocator>& right);

friend void swap(
    vector<Type, Allocator>& left,  
    vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` right`  
 Ein Vektor, in dem die auszutauschenden Elemente bereitgestellt werden, oder ein Vektor, dessen Elemente mit denen des Vektors ` left` ausgetauscht werden sollen.  
  
 ` left`  
 Ein Vektor, dessen Elemente mit denen des Vektors ` right` ausgetauscht werden sollen.  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_swap.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;     
   vector <int> v1, v2;  
  
   v1.push_back( 1 );  
   v1.push_back( 2 );  
   v1.push_back( 3 );  
  
   v2.push_back( 10 );  
   v2.push_back( 20 );  
  
   cout << "The number of elements in v1 = " << v1.size( ) << endl;  
   cout << "The number of elements in v2 = " << v2.size( ) << endl;  
   cout << endl;  
  
   v1.swap( v2 );  
  
   cout << "The number of elements in v1 = " << v1.size( ) << endl;  
   cout << "The number of elements in v2 = " << v2.size( ) << endl;  
}  
```  
  
```Output  
The number of elements in v1 = 3  
The number of elements in v2 = 2  
  
The number of elements in v1 = 2  
The number of elements in v2 = 3  
```  
  
##  <a name="a-namevectorvaluetypea-vectorvaluetype"></a><a name="vector__value_type"></a>  Vector:: value_type  
 Ein Typ, der den in einem Vektor gespeicherten Datentyp darstellt.  
  
```  
typedef typename Allocator::value_type value_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 `value_type` ist ein Synonym für den Vorlagenparameter **Typ**.  
  
### <a name="example"></a>Beispiel  
  
```  
// vector_value_type.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   vector<int>::value_type AnInt;  
   AnInt = 44;  
   cout << AnInt << endl;  
}  
```  
  
```Output  
44  
```  
  
##  <a name="a-namevectorvectora-vectorvector"></a><a name="vector__vector"></a>  Vector:: Vector  
 Erstellt einen Vektor einer bestimmten Größe bzw. mit Elementen eines bestimmten Werts oder mit einer bestimmten Zuweisung oder als vollständige bzw. teilweise Kopie eines anderen Vektors.  
  
```  
vector();

explicit vector(
    const Allocator& Al);

explicit vector(
    size_type Count);

vector(
    size_type Count,  
    const Type& Val);

vector(
    size_type Count,  
    const Type& Val,  
    const Allocator& Al);

vector(
    const vector& Right);

vector(
    vector&& Right);

vector(
    initializer_list<Type> IList,  
    const _Allocator& Al);

template <class InputIterator>  
vector(
 InputIterator First,  
    InputIterator Last);

template <class InputIterator>  
vector(
 InputIterator First,  
    InputIterator Last,  
    const Allocator& Al);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|`Al`|Die mit diesem Objekt zu verwendende Zuweisungsklasse. [Get_allocator](#vector__get_allocator) Gibt die zuweisungsklasse für das Objekt zurück.|  
|`Count`|Die Anzahl der Elemente im erstellten Vektor.|  
|`Val`|Der Wert der Elemente im erstellten Vektor.|  
|`Right`|Der Vektor, dessen Kopie der erstellte Vektor ist.|  
|`First`|Die Position des ersten Elements in dem zu kopierenden Elementbereich.|  
|`Last`|Die Position des ersten Elements nach dem zu kopierenden Elementbereich.|  
|`IList`|Das initializer_list-Element, in dem die zu kopierenden Elemente enthalten sind.|  
  
### <a name="remarks"></a>Hinweise  
 Alle Konstruktoren speichern ein Zuweisungsobjekt ( `Al`) und der Vektor initialisiert.  
  
 Die ersten beiden Konstruktoren geben einen leeren ursprünglichen Vektor an. Der zweite gibt explizit den Allocator-Typ ( `Al`) verwendet werden.  
  
 Der dritte Konstruktor gibt eine Wiederholung einer angegebenen Anzahl ( `Count`) von Elementen des Standardwerts für die Klasse `Type`.  
  
 Die vierten und fünften Konstruktoren geben eine Wiederholung von ( `Count`) Elemente des Werts `Val`.  
  
 Der sechste Konstruktor gibt eine Kopie des Vektors `Right` an.  
  
 Mit dem siebten Konstruktor wird der `Right`-Vektor verschoben.  
  
 Beim achten Konstruktor wird zum Angeben des Elements ein initializer_list-Element verwendet.  
  
 Der neunten und zehnten Konstruktoren kopieren den Bereich [ `First`, `Last`) eines Vektors.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// vector_ctor.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    vector <int>::iterator v1_Iter, v2_Iter, v3_Iter, v4_Iter, v5_Iter, v6_Iter;  
  
    // Create an empty vector v0  
    vector <int> v0;  
  
    // Create a vector v1 with 3 elements of default value 0  
    vector <int> v1(3);  
  
    // Create a vector v2 with 5 elements of value 2  
    vector <int> v2(5, 2);  
  
    // Create a vector v3 with 3 elements of value 1 and with the allocator   
    // of vector v2  
    vector <int> v3(3, 1, v2.get_allocator());  
  
    // Create a copy, vector v4, of vector v2  
    vector <int> v4(v2);  
  
    // Create a new temporary vector for demonstrating copying ranges  
    vector <int> v5(5);  
    for (auto i : v5) {  
        v5[i] = i;  
    }  
  
    // Create a vector v6 by copying the range v5[ first,  last)  
    vector <int> v6(v5.begin() + 1, v5.begin() + 3);  
  
    cout << "v1 =";  
    for (auto& v : v1){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    cout << "v2 =";  
    for (auto& v : v2){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    cout << "v3 =";  
    for (auto& v : v3){  
        cout << " " << v;  
    }  
    cout << endl;  
    cout << "v4 =";  
    for (auto& v : v4){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    cout << "v5 =";  
    for (auto& v : v5){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    cout << "v6 =";  
    for (auto& v : v6){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    // Move vector v2 to vector v7  
    vector <int> v7(move(v2));  
    vector <int>::iterator v7_Iter;  
  
    cout << "v7 =";  
    for (auto& v : v7){  
        cout << " " << v;  
    }  
    cout << endl;  
  
    vector<int> v8{ { 1, 2, 3, 4 } };  
    for (auto& v : v8){  
        cout << " " << v ;  
    }  
    cout << endl;  
}  
  
```  
  
```Output  
v1 = 0 0 0v2 = 2 2 2 2 2v3 = 1 1 1v4 = 2 2 2 2 2v5 = 0 1 2 3 4v6 = 1 2v7 = 2 2 2 2 21 2 3 4  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)

