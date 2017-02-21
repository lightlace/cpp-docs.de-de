---
title: "vector&lt;bool&gt;-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vector<bool>"
  - "std.vector<bool>"
  - "std::vector<bool>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector < Bool >-Klasse"
ms.assetid: 8028c8ed-ac9c-4f06-aba1-5de45c00aafb
caps.latest.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 29
---
# vector&lt;bool&gt;-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die `vector<bool>` -Klasse ist eine teilweise Spezialisierung von [Vektor](vector%20Class.md) für Elemente des Typs `bool`. Sie verfügt über eine Zuweisung für den zugrunde liegenden Typ, der von der Spezialisierung verwendet wird, die Leerzeichenoptimierung durch Speichern von einem `bool`-Wert pro Bit bereitstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Allocator = allocator<bool>>  
class vector<bool, Allocator>  
```  
  
## <a name="remarks"></a>Hinweise  
 Diese Spezialisierung einer Klassenvorlage verhält sich wie Vektor, mit Ausnahme der Unterschiede, die in diesem Artikel erläutert.  
  
 Vorgänge, die den `bool`-Typ betreffen, entsprechen den Werten im Containerspeicher. `allocator_traits::construct` wird nicht verwendet, um diese Werte zu erstellen.  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[const_pointer](#vector_lt_bool_gt___const_pointer)|Eine Typedef für ein `const_iterator`-Element, das als konstanter Zeiger auf ein boolesches Element des `vector<bool>`-Elements dienen kann.|  
|[const_reference](#vector_lt_bool_gt___const_reference)|Eine Typedef für `bool`. Nach der Initialisierung werden keine Updates auf den ursprünglichen Wert berücksichtigt.|  
|[Zeiger](#vector_lt_bool_gt___pointer)|Eine Typedef für ein `iterator`-Element, das als Zeiger auf ein boolesches Element des `vector<bool>`-Elements dienen kann.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[Kippen](#vector_lt_bool_gt___flip)|Kehrt alle Bits im `vector<bool>`-Element um.|  
|[Swap](#vector_lt_bool_gt___swap)|Tauscht die Elemente zweier `vector<bool>`n.|  
|[Operator &#91; &#93;](#vector_lt_bool_gt___operator_at)|Gibt einen simulierten Verweis auf das `vector<bool>`-Element an einer angegebenen Position zurück.|  
|`at`|Die gleiche Funktion wie die nicht spezialisierte [Vektor](vector%20Class.md):: bei der Funktion, mit der Ausnahme, dass die It die Proxyklasse verwendet [Vector \< Bool>:: Reference](#vector_lt_bool_gt___reference_class). Siehe auch [Operator &#91; &#93;](#vector_lt_bool_gt___operator_at).|  
|`front`|Die gleiche Funktion wie die nicht spezialisierte [Vektor](vector%20Class.md):: Front-Funktion, mit der Ausnahme, dass die Proxyklasse [Vector \< Bool>:: Reference](#vector_lt_bool_gt___reference_class). Siehe auch [Operator &#91; &#93;](#vector_lt_bool_gt___operator_at).|  
|`back`|Die gleiche Funktion wie die nicht spezialisierte [Vektor](vector%20Class.md):: Funktion zurück, mit der Ausnahme, dass die Proxyklasse [Vector \< Bool>:: Reference](#vector_lt_bool_gt___reference_class). Siehe auch [Operator &#91; &#93;](#vector_lt_bool_gt___operator_at).|  
  
### <a name="proxy-class"></a>Proxyklasse  
  
|||  
|-|-|  
|[Vector \< Bool> -Klasse](#vector_lt_bool_gt___reference_class)|Eine Klasse, die als Proxy auftritt, um `bool&`-Verhalten zu simulieren, und deren Objekte Verweise auf Elemente (einzelne Bits) innerhalb eines `vector<bool>`-Objekts bereitstellen können.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header**: \< Vektor>  
  
 **Namespace:** std  
  
##  <a name="a-namevectorltboolgtconstpointera-vectorboolconstpointer"></a><a name="vector_lt_bool_gt___const_pointer"></a>  Vector \< Bool>:: Const_pointer  
 Ein Typ, der ein Objekt beschreibt, das als konstanter Zeiger auf ein boolesches Element der Sequenz dienen kann, die im `vector<bool>`-Objekt enthalten ist.  
  
```  
typedef const_iterator const_pointer;  
```  
  
##  <a name="a-namevectorltboolgtconstreferencea-vectorboolconstreference"></a><a name="vector_lt_bool_gt___const_reference"></a>  Vector \< Bool>:: Const_reference  
 Ein Typ, der ein Objekt beschreibt, das als konstanter Verweis auf ein boolesches Element der Sequenz dienen kann, die im `vector<bool>`-Objekt enthalten ist.  
  
```  
typedef bool const_reference;  
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen und Codebeispiele finden Sie unter [Vektor&lt;Bool&gt;:: Reference =](#vector_lt_bool_gt___reference_operator_eq).  
  
##  <a name="a-namevectorltboolgtflipa-vectorboolflip"></a><a name="vector_lt_bool_gt___flip"></a>  Vector \< Bool>:: kippen  
 Kehrt alle Bits in `vector<bool>` um.  
  
```  
void flip();
```  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// vector_bool_flip.cpp  
// compile with: /EHsc /W4  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    cout << boolalpha; // format output for subsequent code  
  
    vector<bool> vb = { true, false, false, true, true };  
    cout << "The vector is:" << endl << "    ";  
    for (const auto& b : vb) {  
        cout << b << " ";  
    }  
    cout << endl;  
  
    vb.flip();  
  
    cout << "The flipped vector is:" << endl << "    ";  
    for (const auto& b : vb) {  
        cout << b << " ";  
    }  
    cout << endl;  
}  
  
```  
  
##  <a name="a-namevectorltboolgtoperatorata-vectorbooloperator"></a><a name="vector_lt_bool_gt___operator_at"></a>  Vector \< Bool>:: Operator]  
 Gibt einen simulierten Verweis auf das `vector<bool>`-Element an einer angegebenen Position zurück.  
  
```  
vector<bool>::reference operator[](size_type Pos);

vector&<bool&>::const_reference operator[](size_type Pos) const;
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|`Pos`|Die Position des `vector<bool>`-Elements.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [Vector \< Bool>:: Reference](#vector_lt_bool_gt___reference_class) oder [Vector \< Bool>:: Const_reference](#vector_lt_bool_gt___const_reference) -Objekt, das den Wert des indizierten Elements enthält.  
  
 Wenn die angegebene Position größer oder gleich der Größe des Containers ist, ist das Ergebnis nicht definiert.  
  
### <a name="remarks"></a>Hinweise  
 Beim Kompilieren mit festgelegtem `_ITERATOR_DEBUG_LEVEL`-Wert tritt ein Laufzeitfehler auf, wenn Sie versuchen, auf ein Element außerhalb der Grenzen des Vektors zuzugreifen.  Weitere Informationen finden Sie unter [Checked Iterators](../standard-library/checked-iterators.md).  
  
### <a name="example"></a>Beispiel  
  Dieses Codebeispiel veranschaulicht die korrekte Verwendung von `vector<bool>::operator[]` und zwei häufige Codierungsfehler, die auskommentiert werden. Diese Fehler verursachen Probleme, da die Adresse des `vector<bool>::reference`-Objekts, das `vector<bool>::operator[]` zurückgibt, nicht ausgeführt werden kann.  
  
```cpp  
  
// cl.exe /EHsc /nologo /W4 /MTd   
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    cout << boolalpha;  
    vector<bool> vb;  
  
    vb.push_back(true);  
    vb.push_back(false);  
  
    //    bool* pb = &vb[1]; // conversion error -                         do not use  
    //    bool& refb = vb[1];   // conversion error -                         do not use  
    bool hold = vb[1];  
    cout << "The second element of vb is " << vb[1] << endl;  
    cout << "The held value from the second element of vb is " << hold << endl;  
  
    // Note this doesn't modify hold.  
    vb[1] = true;  
    cout << "The second element of vb is " << vb[1] << endl;  
    cout << "The held value from the second element of vb is " << hold << endl;  
}  
  
```  
  
##  <a name="a-namevectorltboolgtpointera-vectorboolpointer"></a><a name="vector_lt_bool_gt___pointer"></a>  Vector \< Bool>:: Zeiger  
 Ein Typ, der ein Objekt beschreibt, das als Zeiger auf ein boolesches Element der Sequenz dienen kann, die im `vector<bool>`-Objekt enthalten ist.  
  
```  
typedef iterator pointer;  
```  
  
##  <a name="a-namevectorltboolgtreferenceclassa-vectorboolreference-class"></a><a name="vector_lt_bool_gt___reference_class"></a>  Vector \< Bool>:: reference-Klasse  
 Die `vector<bool>::reference` Klasse ist eine Proxyklasse, die von bereitgestellten der [Vector \< Bool> Klasse](../standard-library/vector-bool-class.md) simulieren `bool&`.  
  
### <a name="remarks"></a>Hinweise  
 Ein simulierter Verweis ist erforderlich, da C++ systemintern keine direkten Verweise auf Bits zulässt. `vector<bool>` verwendet nur ein Bit pro Element, auf das anhand dieser Proxyklasse verwiesen werden kann. Allerdings ist die Verweissimulation nicht vollständig, da bestimmte Zuweisungen ungültig sind. Z. B. weil die Adresse des der `vector<bool>::reference` Objekt kann nicht ausgeführt werden, wird den folgenden Code verwendet [Vector \< Bool>:: Operator &#91; &#93;](#vector_lt_bool_gt___operator_at) ist nicht korrekt:  
  
```cpp  
    vector<bool> vb;  
...  
    bool* pb = &vb[1]; // conversion error -         do not use  
    bool& refb = vb[1];   // conversion error -         do not use  
```  
  
###  <a name="a-namevectorltboolgtreferenceflipa-vectorboolreferenceflip"></a><a name="vector_lt_bool_gt___reference_flip"></a>  Vector \< Bool>:: Reference:: Flip  
 Hierdurch wird den booleschen Wert, der einen Verweis [Vector \< Bool>](../standard-library/vector-bool-class.md) Element.  
  
```  
void flip();
```  
  
#### <a name="remarks"></a>Hinweise  
  
#### <a name="example"></a>Beispiel  
  
```cpp  
// vector_bool_ref_flip.cpp  
// compile with: /EHsc /W4  
#include <vector>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    cout << boolalpha;  
  
    vector<bool> vb = { true, false, false, true, true };  
  
    cout << "The vector is: " << endl << "    ";  
    for (const auto& b : vb) {  
        cout << b << " ";  
    }  
    cout << endl;  
  
    vector<bool>::reference vbref = vb.front();  
    vbref.flip();  
  
    cout << "The vector with first element flipped is: " << endl << "    ";  
    for (const auto& b : vb) {  
        cout << b << " ";  
    }  
    cout << endl;  
}  
/* Output:  
The vector is:  
    true false false true true  
The vector with first element flipped is:  
    false false false true true  
    */  
  
```  
  
###  <a name="a-namevectorltboolgtreferenceoperatorboola-vectorboolreferenceoperator-bool"></a><a name="vector_lt_bool_gt___reference_operator_bool"></a>  Vector \< Bool>:: Reference Bool  
 Stellt eine implizite Konvertierung von `vector<bool>::reference` in `bool` bereit.  
  
''' Operator bool() const;
```  
  
#### Return Value  
 The Boolean value of the element of the vector<bool\> object.  
  
#### Remarks  
 The `vector<bool>` object cannot be modified by this operator.  
  
###  <a name="vector_lt_bool_gt___reference_operator_eq"></a>  vector<bool\>::reference::operator=  
 Assigns a Boolean value to a bit, or the value held by a referenced element to a bit.  
  
```  
Verweis & Operator = (const-Verweis und rechts).

Operator & Verweis =(bool Val);
```  
  
#### Parameters  
 `Right`  
 The element reference whose value is to be assigned to the bit.  
  
 `Val`  
 The Boolean value to be assigned to the bit.  
  
#### Example  
  
```cpp  
// vector_bool_ref_op_assign.cpp  
// compile with: /EHsc  
#include <vector>  
#include <iostream>  
#include <string>  
  
using namespace std;  
  
template <typename C> void print(const string& s, const C& c) {  
    cout << s;  
  
    for (const auto& e : c) {  
        cout << e << " ";  
    }  
  
    cout << endl;  
}  
  
int main()  
{  
    cout << boolalpha;  
  
    vector<bool> vb = { true, false, false, true, true };  
  
    print("The vector is: ", vb);  
  
    // Invoke vector<bool>::reference::operator=()  
    vector<bool>::reference refelem1 = vb[0];  
    vector<bool>::reference refelem2 = vb[1];  
    vector<bool>::reference refelem3 = vb[2];  
  
    bool b1 = refelem1;  
    bool b2 = refelem2;  
    bool b3 = refelem3;  
    cout << "The original value of the 1st element stored in a bool: " << b1 << endl;  
    cout << "The original value of the 2nd element stored in a bool: " << b2 << endl;  
    cout << "The original value of the 3rd element stored in a bool: " << b3 << endl;  
    cout << endl;  
  
    refelem2 = refelem1;  
  
    print("The vector after assigning refelem1 to refelem2 is now: ", vb);  
  
    refelem3 = true;  
  
    print("The vector after assigning false to refelem1 is now: ", vb);  
  
    // The initial values are still stored in the bool variables and remained unchanged  
    cout << "The original value of the 1st element still stored in a bool: " << b1 << endl;  
    cout << "The original value of the 2nd element still stored in a bool: " << b2 << endl;  
    cout << "The original value of the 3rd element still stored in a bool: " << b3 << endl;  
    cout << endl;  
}  
/* Output:  
The vector is: true false false true true  
The original value of the 1st element stored in a bool: true  
The original value of the 2nd element stored in a bool: false  
The original value of the 3rd element stored in a bool: false  
  
The vector after assigning refelem1 to refelem2 is now: true true false true true  
The vector after assigning false to refelem1 is now: true true true true true  
The original value of the 1st element still stored in a bool: true  
The original value of the 2nd element still stored in a bool: false  
The original value of the 3rd element still stored in a bool: false  
*/  
  
```  
  
##  <a name="a-namevectorltboolgtswapa-vectorboolswap"></a><a name="vector_lt_bool_gt___swap"></a>  Vector \< Bool>:: Swap  
 Statische Memberfunktion, die tauscht zwei Elemente mit booleschen Vektoren ( `vector<bool>`) mithilfe der Proxyklasse [Vector \< Bool>:: Reference](#vector_lt_bool_gt___reference_class).  
  
```  
 
static void swap(
    reference Left,  
    reference Right);
```  
  
### <a name="parameters"></a>Parameter  
 `Left`  
 Das Element, das mit dem `Right`-Element ausgetauscht werden soll.  
  
 `Right`  
 Das Element, das mit dem `Left`-Element ausgetauscht werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Diese Überladung unterstützt die besonderen Proxyanforderungen von `vector<bool>`. [Vektor](vector%20Class.md):: Swap hat die gleiche Funktionalität wie die Überladung einem Argument von `vector<bool>::swap()`.  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Standard Template Library](../misc/standard-template-library.md)

