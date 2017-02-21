---
title: "valarray-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "valarray"
  - "std.valarray"
  - "std::valarray"
  - "valarray/std::valarray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "valarray-Klasse"
ms.assetid: 19b862f9-5d09-4003-8844-6ddd02c1a3a7
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# valarray-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse beschreibt ein Objekt, das eine Sequenz von Elementen vom Typ steuert **Typ** die als Array gespeichert, für schnelle mathematische Vorgänge entworfen und rechnerischen Leistung optimiert.  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse ist eine Darstellung des mathematischen Konzepts einer sortierten Menge von Werten, und die Elemente werden fortlaufend ab null nummeriert. Die Klasse wird als nahezu Container beschrieben, da es einige unterstützt, aber nicht alle Funktionen, erstklassige, wie z. B. sequenzcontainer [Vektor](vector%20Class.md), unterstützen. Die Klasse unterscheidet sich in zwei wichtigen Aspekten von der vector-Vorlagenklasse:  
  
-   Zahlreiche arithmetische Operationen zwischen entsprechende Elemente definiert **Valarray \< Type>** Objekte vom gleichen Typ und Länge, wie z. B. *Xarr* = cos ( *Yarr*) + sin ( *Zarr*).  
  
-   Definiert eine Vielzahl von interessanten Art und Weise zu abonnieren einer **Valarray \< Type>** -Objekt, durch das Überladen [Operator &#91; &#93;](#valarray__operator_at).  
  
 Ein Objekt der Klasse **Typ**:  
  
-   Es hat einen öffentlichen Standardkonstruktor, Destruktor, Kopierkonstruktor und Zuweisungsoperator mit üblichem Verhalten.  
  
-   Es definiert nach Bedarf die arithmetischen Operatoren und mathematischen Funktionen, die für die Gleitkommatypen definiert sind (mit üblichem Verhalten).  
  
 Insbesondere dürfen keine feinen Unterschiede zwischen einer Kopierkonstruktion und einer Standardkonstruktion bestehen, auf die eine Zuweisung folgt. Keiner der Vorgänge für Objekte der Klasse **Typ** Ausnahmen auslösen.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[valarray](#valarray__valarray)|Erstellt ein `valarray`-Objekt einer bestimmten Größe oder mit Elementen eines bestimmten Werts oder als Kopie eines anderen `valarray`-Objekts oder als Teilmenge eines anderen `valarray`-Objekts.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[Werttyp](#valarray__value_type)|Ein Typ, der den Typ der in einem `valarray`-Objekt gespeicherten Elemente darstellt.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[Anwenden](#valarray__apply)|Wendet eine angegebene Funktion auf jedes Element eines `valarray`-Objekts an.|  
|[cshift](#valarray__cshift)|Verschiebt zyklisch alle Elemente in einem `valarray`-Objekt um eine angegebene Anzahl von Positionen.|  
|[frei](#valarray__free)|Gibt den Arbeitsspeicher frei, der vom `valarray`-Objekt verwendet wird.|  
|[Max](#valarray__max)|Sucht nach dem größten Element in einem `valarray`-Objekt.|  
|[Min.](#valarray__min)|Sucht nach dem kleinsten Element in einem `valarray`-Objekt.|  
|[Ändern der Größe](#valarray__resize)|Ändert die Anzahl von Elementen in einem `valarray`-Objekt in die jeweils angegebene Anzahl, wozu Elemente nach Bedarf hinzugefügt oder entfernt werden.|  
|[Umschalttaste gedrückt](#valarray__shift)|Verschiebt alle Elemente in einem `valarray`-Objekt um eine angegebene Anzahl von Positionen.|  
|[Größe](#valarray__size)|Ermittelt die Anzahl von Elementen in einem `valarray`-Objekt.|  
|[Summe](#valarray__sum)|Bestimmt die Summe aller Elemente in einem `valarray`-Objekt mit einer Länge ungleich null.|  
|[Swap](#valarray__swap)||  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator!](#valarray__operator_not)|Ein unärer Operator, der die logischen `NOT`-Werte jedes Elements eines `valarray`-Objekts abruft.|  
|[Operator% =](#valarray__operator_mod_eq)|Ruft den Rest der Division der Elemente eines Arrays elementweise entweder entsprechend einem angegebenen `valarray`-Objekt oder entsprechend einem Wert des Elementtyps ab.|  
|[Operator & =](#valarray__operator_amp__eq)|Ruft das bitweise `AND`-Ergebnis von Elementen eines Arrays entweder mit den entsprechenden Elementen in einem angegebenen `valarray`-Objekt oder mit einem Wert des Elementtyps ab.|  
|[Operator >> =](#valarray__operator_gt__gt__eq)|Verschiebt die Bits für jedes Element eines `valarray`-Operanden um eine angegebene Anzahl von Positionen oder um einen elementweisen Betrag, der durch ein zweites `valarray`-Objekt angegeben ist, nach rechts.|  
|[Operator << =](#valarray__operator_lt__lt__eq)|Verschiebt die Bits für jedes Element eines `valarray`-Operanden um eine angegebene Anzahl von Positionen oder um einen elementweisen Betrag, der durch ein zweites `valarray`-Objekt angegeben ist, nach links.|  
|[Operator * =](#valarray__operator_star_eq)|Multipliziert die Elemente eines angegebenen `valarray`-Objekts oder einen Wert des Elementtyps elementweise mit einem `valarray`-Operanden.|  
|[Operator +](#valarray__operator_add)|Ein unärer Operator, der ein Pluszeichen auf jedes Element in einem `valarray`-Objekt anwendet.|  
|[Operator +=](#valarray__operator_add_eq)|Fügt die Elemente eines angegebenen `valarray`-Objekts oder einen Wert des Elementtyps elementweise einem `valarray`-Operanden hinzu.|  
|[Operator-](#valarray__operator-)|Ein unärer Operator, der ein Minuszeichen auf jedes Element in einem `valarray`-Objekt anwendet.|  
|[Operator =](#valarray__operator-_eq)|Subtrahiert die Elemente eines angegebenen `valarray`-Objekts oder einen Wert des Elementtyps elementweise von einem `valarray`-Operanden.|  
|[Operator / =](#valarray__operator__eq)|Dividiert einen `valarray`-Operanden elementweise durch die Elemente eines angegebenen `valarray`-Objekts oder durch einen Wert des Elementtyps.|  
|[Operator =](#valarray__operator_eq)|Ordnet einem `valarray`-Objekt Elemente zu, deren Werte entweder direkt oder als Teil eines anderen `valarray`-Objekts oder durch ein `slice_array`-, `gslice_array`-, `mask_array`- oder `indirect_array`-Objekt angegeben sind.|  
|[Operator &#91; &#93;](#valarray__operator_at)|Gibt einen Verweis auf ein Element oder auf den Wert zurück, den es am angegebenen Index oder in der angegebenen Teilmenge hat.|  
|[Operator ^ =](#valarray__operator_xor_eq)|Ruft die logische elementweisen exklusiver or -Operator ( `XOR`) eines Arrays mit einer angegebenen Valarray oder ein Wert, der den Elementtyp.|  
|[Operator &#124; =](#valarray__operator_or_eq)|Ruft das bitweise `OR`-Ergebnis von Elementen eines Arrays entweder mit den entsprechenden Elementen in einem angegebenen `valarray`-Objekt oder mit einem Wert des Elementtyps ab.|  
|[Operator ~](#valarray__operator_dtor)|Ein unärer Operator, der die bitweisen `NOT`-Werte jedes Elements eines `valarray`-Objekts abruft.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \< Valarray>  
  
 **Namespace:** std  
  
##  <a name="a-namevalarrayapplya-valarrayapply"></a><a name="valarray__apply"></a>  valarray:: Apply  
 Wendet eine angegebene Funktion auf jedes Element ein Wertarray.  
  
```  
valarray<Type> apply(Type _Func(Type)) const;

valarray<Type> apply(Type _Func(constType&)) const;
```  
  
### <a name="parameters"></a>Parameter  
 *_Func(Type)*  
 Das Funktionsobjekt auf jedes Element der Operand Wertarray angewendet werden.  
  
 *_Func(const Type&)*  
 Das Funktionsobjekt für Const auf jedes Element der Operand Wertarray angewendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wertarray, dessen Elemente hatten `_Func` element-wise auf die Elemente der Wertarray Operanden angewendet.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt ein Objekt der Klasse [Valarray](../standard-library/valarray-class.md)**\< Typ>**, Länge [Größe](#valarray__size), jedes, dessen Elemente `I` ist **Func**(( **\*dies**) [ `I`]).  
  
### <a name="example"></a>Beispiel  
  
```  
// valarray_apply.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
using namespace std;  
  
int __cdecl MyApplyFunc( int n )  
{  
   return n*2;  
}  
  
int main( int argc, char* argv[] )  
{  
   valarray<int> vaR(10), vaApplied(10);  
   int i;  
  
   for ( i = 0; i < 10; i += 3 )  
      vaR[i] = i;  
  
   for ( i = 1; i < 10; i += 3 )  
      vaR[i] = 0;  
  
   for ( i = 2; i < 10; i += 3 )  
      vaR[i] = -i;  
  
   cout << "The initial Right valarray is: (";  
   for   ( i=0; i < 10; ++i )  
      cout << " " << vaR[i];  
   cout << " )" << endl;  
  
   vaApplied = vaR.apply( MyApplyFunc );  
  
   cout << "The element-by-element result of "  
       << "applying MyApplyFunc to vaR is the\nvalarray: ( ";  
   for ( i = 0; i < 10; ++i )  
      cout << " " << vaApplied[i];  
   cout << " )" << endl;  
}  
\* Output:   
The initial Right valarray is: ( 0 0 -2 3 0 -5 6 0 -8 9 )  
The element-by-element result of applying MyApplyFunc to vaR is the  
valarray: (  0 0 -4 6 0 -10 12 0 -16 18 )  
*\  
```  
  
##  <a name="a-namevalarraycshifta-valarraycshift"></a><a name="valarray__cshift"></a>  valarray:: cshift  
 Alle Elemente in einem Valarray verschiebt zyklisch eine angegebene Anzahl von Positionen.  
  
```  
valarray<Type> cshift(int count) const;
```  
  
### <a name="parameters"></a>Parameter  
 ` count`  
 Die Anzahl der stellen die Elemente sind vorwärts verschoben werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine neue, in dem alle Elemente wurden verschoben, Wertarray ` count` Positionen zyklisch nach vorn Wertarray, in Bezug auf ihre Positionen im Wertarray Operanden nach links.  
  
### <a name="remarks"></a>Hinweise  
 Ein positiver Wert von ` count` verschiebt die Elemente zyklisch Links ` count` platziert.  
  
 Ein negativer Wert von ` count` verschiebt die Elemente zyklisch rechten ` count` platziert.  
  
### <a name="example"></a>Beispiel  
  
```  
// valarray_cshift.cpp  
// compile with: /EHsc  
  
#include <valarray>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    int i;  
  
    valarray<int> va1(10), va2(10);  
    for (i = 0; i < 10; i+=1)  
        va1[i] = i;  
    for (i = 0; i < 10; i+=1)  
        va2[i] = 10 - i;  
  
    cout << "The operand valarray va1 is: (";  
    for (i = 0; i < 10; i++)  
        cout << " " << va1[i];  
    cout << ")" << endl;  
  
    // A positive parameter shifts elements right  
    va1 = va1.cshift(4);  
    cout << "The cyclically shifted valarray va1 is:\nva1.cshift (4) = (";  
    for (i = 0; i < 10; i++)  
        cout << " " << va1[i];  
    cout << ")" << endl;  
  
    cout << "The operand valarray va2 is: (";  
    for (i = 0; i < 10; i++)  
        cout << " " << va2[i];  
    cout << ")" << endl;  
  
    // A negative parameter shifts elements left  
    va2 = va2.cshift(-4);  
    cout << "The cyclically shifted valarray va2 is:\nva2.shift (-4) = (";  
    for (i = 0; i < 10; i++)  
        cout << " " << va2[i];  
    cout << ")" << endl;  
}  
\* Output:   
The operand valarray va1 is: ( 0 1 2 3 4 5 6 7 8 9)  
The cyclically shifted valarray va1 is:  
va1.cshift (4) = ( 4 5 6 7 8 9 0 1 2 3)  
The operand valarray va2 is: ( 10 9 8 7 6 5 4 3 2 1)  
The cyclically shifted valarray va2 is:  
va2.shift (-4) = ( 4 3 2 1 10 9 8 7 6 5)  
*\  
```  
  
##  <a name="a-namevalarrayfreea-valarrayfree"></a><a name="valarray__free"></a>  valarray:: Free  
 Gibt den Arbeitsspeicher frei von Wertarray verwendet.  
  
```  
void free();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese nicht Standard-Funktion ist ein leeres Wertarray zuweisen. Zum Beispiel:  
  
```  
valarray<T> v;  
v = valarray<T>();

// equivalent to v.free()  
```  
  
##  <a name="a-namevalarraymaxa-valarraymax"></a><a name="valarray__max"></a>  valarray:: Max  
 Das größte Element in einem Valarray gefunden.  
  
```  
Type max() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der maximale Wert der Elemente im Wertarray Operanden.  
  
### <a name="remarks"></a>Hinweise  
 Die Member-Funktion vergleicht Werte durch Anwenden **Operator \<** oder **Operator >** zwischen Paare von Elementen der Klasse **Typ**, für welche Operatoren für das Element angegeben werden, müssen **Typ**.  
  
### <a name="example"></a>Beispiel  
  
```  
// valarray_max.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i, MaxValue;  
  
   valarray<int> vaR ( 10 );  
   for ( i = 0 ; i < 10 ; i += 3 )  
      vaR [ i ] =  i;  
   for ( i = 1 ; i < 10 ; i += 3 )  
      vaR [ i ] =  2*i - 1;  
   for ( i = 2 ; i < 10 ; i += 3 )  
      vaR [ i ] =  10 - i;  
  
   cout << "The operand valarray is: ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   MaxValue = vaR.max (  );  
   cout << "The largest element in the valarray is: "  
        << MaxValue  << "." << endl;  
}  
\* Output:   
The operand valarray is: ( 0 1 8 3 7 5 6 13 2 9 ).  
The largest element in the valarray is: 13.  
*\  
```  
  
##  <a name="a-namevalarraymina-valarraymin"></a><a name="valarray__min"></a>  valarray:: Min  
 Sucht das kleinste Element in ein Wertarray.  
  
```  
Type min() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Mindestwert der Elemente im Wertarray Operanden.  
  
### <a name="remarks"></a>Hinweise  
 Die Member-Funktion vergleicht Werte durch Anwenden **Operator \<** oder **Operator >** zwischen Paare von Elementen der Klasse **Typ**, für welche Operatoren für das Element angegeben werden, müssen **Typ**.  
  
### <a name="example"></a>Beispiel  
  
```  
// valarray_min.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i, MinValue;  
  
   valarray<int> vaR ( 10 );  
   for ( i = 0 ; i < 10 ; i += 3 )  
      vaR [ i ] =  -i;  
   for ( i = 1 ; i < 10 ; i += 3 )  
      vaR [ i ] =  2*i;  
   for ( i = 2 ; i < 10 ; i += 3 )  
      vaR [ i ] =  5 - i;  
  
   cout << "The operand valarray is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   MinValue = vaR.min ( );  
   cout << "The smallest element in the valarray is: "  
        << MinValue  << "." << endl;  
}  
\* Output:   
The operand valarray is: ( 0 2 3 -3 8 0 -6 14 -3 -9 ).  
The smallest element in the valarray is: -9.  
*\  
```  
  
##  <a name="a-namevalarrayoperatornota-valarrayoperator"></a><a name="valarray__operator_not"></a>  valarray:: Operator!  
 Ein unärer Operator, der die logische erhält **NICHT** Werte der einzelnen Elemente in ein Wertarray.  
  
```  
valarray<bool> operator!() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Valarray von booleschen Werten, die die Negation der Elementwerte des Operanden Wertarray sind.  
  
### <a name="remarks"></a>Hinweise  
 Die logische Operation **NICHT** negiert Elemente, da Nullen in Einsen konvertiert und alle ungleich NULL-Werte als solche in Bezug auf und sie in Nullen konvertiert. Zurückgegebene Wertarray von booleschen Werten ist die gleiche Größe wie die Operanden Wertarray.  
  
 Es gibt auch eine bitweise **NICHT**[valarray:: Operator ~](#valarray__operator_dtor) die auf der Ebene der einzelnen Bits in der binären Darstellung des negiert `char` und `int` Elemente ein Wertarray.  
  
### <a name="example"></a>Beispiel  
  
```  
// valarray_op_lognot.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 );  
   valarray<bool> vaNOT ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL [ i ] =  0;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL [ i ] =  i-1;  
  
   cout << "The initial valarray is:  ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   vaNOT = !vaL;  
   cout << "The element-by-element result of "  
        << "the logical NOT operator! is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaNOT [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).  
The element-by-element result of the logical NOT operator! is the  
 valarray: ( 1 1 1 0 1 0 1 0 1 0 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatormodeqa-valarrayoperator"></a><a name="valarray__operator_mod_eq"></a>  valarray:: Operator% =  
 Ruft den Rest der Division element-wise die Elemente eines Arrays, eine angegebene Valarray oder als Wert vom Typ Elements ab.  
  
```  
valarray<Type>& operator%=(const valarray<Type>& right);

valarray<Type>& operator%=(const Type& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` right`  
 Die Valarray oder Wert für einen Elementtyp, der Operand Wertarray, die Operanden Wertarray element-wise, unterteilen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wertarray, dessen Elemente den Rest der elementweisen Division zweier Wertarray Operanden werden, durch ` right.`  
  
### <a name="example"></a>Beispiel  
  
```  
// valarray_class_op_rem.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 6 ), vaR ( 6 );  
   for ( i = 0 ; i < 6 ; i += 2 )  
      vaL [ i ] =  53;  
   for ( i = 1 ; i < 6 ; i += 2 )  
      vaL [ i ] =  -67;  
   for ( i = 0 ; i < 6 ; i++ )  
      vaR [ i ] =  3*i+1;  
  
   cout << "The initial valarray is: ( ";  
      for ( i = 0 ; i < 6 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial  right valarray is: ( ";  
      for ( i = 0 ; i < 6 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaL %= vaR;  
   cout << "The remainders from the element-by-element "  
        << "division is the\n valarray: ( ";  
      for ( i = 0 ; i < 6 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is: ( 53 -67 53 -67 53 -67 ).  
The initial  right valarray is: ( 1 4 7 10 13 16 ).  
The remainders from the element-by-element division is the  
 valarray: ( 0 -3 4 -7 1 -3 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatorampeqa-valarrayoperatoramp"></a><a name="valarray__operator_amp__eq"></a>  valarray:: Operator&amp;=  
 Ruft die bitweise **UND** von Elementen in einem Array mit den entsprechenden Elementen in einer angegebenen Valarray oder ein Wert vom Typ Elements.  
  
```  
valarray<Type>& operator&=(const valarray<Type>& right);

valarray<Type>& operator&=(const Type& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` right`  
 Der Valarray oder den Wert des Elementtyps identisch mit dem der Operand Wertarray, die kombiniert werden, elementweisen, durch die logische **UND** mit Operanden Wertarray.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wertarray, dessen Elemente die elementweisen sind, logische **UND** des Operanden Wertarray durch ` right.`  
  
### <a name="remarks"></a>Hinweise  
 Eine bitweise Operation kann nur verwendet werden, zum Bearbeiten von Bits in `char` und `int` Datentypen und Varianten und nicht auf **Float**, **doppelte**, **Longdouble**, `void`, `bool`, oder andere komplexeren Datentypen.  
  
 Bitweise AND hat die gleichen Wahrheitstabelle als logischen **UND** gelten jedoch für den Datentyp auf der Ebene der einzelnen Bits. Bits angegeben *b*1 und *b*2 *b*1 **UND** *b*2 **true** Wenn beide Bits zutreffen; **false** mindestens false ist.  
  
### <a name="example"></a>Beispiel  
  
```  
// valarray_class_op_bitand.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 ), vaR ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL [ i ] =  0;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL [ i ] =  i-1;  
   for ( i = 0 ; i < 10 ; i++ )  
      vaR [ i ] =  i;  
  
   cout << "The initial valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaL &= vaR;  
   cout << "The element-by-element result of "  
        << "the logical AND operator&= is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is:  ( 0 0 0 2 0 4 0 6 0 8 ).  
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The element-by-element result of the logical AND operator&= is the  
 valarray: ( 0 0 0 2 0 4 0 6 0 8 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatorgtgteqa-valarrayoperatorgtgt"></a><a name="valarray__operator_gt__gt__eq"></a>  valarray:: Operator&gt;&gt;=  
 Rechts-Schichten die Bits für jedes Element ein Wertarray Operand eine angegebene Anzahl von Positionen oder durch einen elementweisen durch eine zweite Valarray angegebenen Betrag.  
  
```  
valarray<Type>& operator>>=(const valarray<Type>& right);

valarray<Type>& operator>>=(const Type& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` right`  
 Der Wert, der angibt, des Betrag der Verschiebung nach rechts oder Valarray anzugeben, dessen Elemente den elementweisen Betrag der Verschiebung nach rechts.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wertarray worden sein, dessen Elemente nach rechts den im angegebenen Abstand verschoben wurden ` right`.  
  
### <a name="remarks"></a>Hinweise  
 Zahlen mit Vorzeichen haben ihre Zeichen beibehalten.  
  
### <a name="example"></a>Beispiel  
  
```  
// valarray_class_op_rs.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 8 ), vaR ( 8 );  
   for ( i = 0 ; i < 8 ; i += 2 )  
      vaL [ i ] =  64;  
   for ( i = 1 ; i < 8 ; i += 2 )  
      vaL [ i ] =  -64;  
   for ( i = 0 ; i < 8 ; i++ )  
      vaR [ i ] =  i;  
  
   cout << "The initial operand valarray is: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The  right valarray is: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaL >>= vaR;  
   cout << "The element-by-element result of "  
        << "the right shift is the\n valarray: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial operand valarray is: ( 64 -64 64 -64 64 -64 64 -64 ).  
The  right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the right shift is the  
 valarray: ( 64 -32 16 -8 4 -2 1 -1 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatorltlteqa-valarrayoperatorltlt"></a><a name="valarray__operator_lt__lt__eq"></a>  valarray:: Operator&lt;&lt;=  
 Links-Schichten die Bits für jedes Element ein Wertarray Operand eine angegebene Anzahl von Positionen oder durch einen elementweisen durch eine zweite Valarray angegebenen Betrag.  
  
```  
valarray<Type>& operator<<=(const valarray<Type>& right);

valarray<Type>& operator<<=(const Type& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` right`  
 Der Wert, der angibt, des Betrag der Verschiebung nach links oder Valarray anzugeben, dessen Elemente den elementweisen Betrag der Verschiebung nach links.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wertarray, dessen Elemente verschoben wurden haben, verbleiben in angegeben ` right`.  
  
### <a name="remarks"></a>Hinweise  
 Zahlen mit Vorzeichen haben ihre Zeichen beibehalten.  
  
### <a name="example"></a>Beispiel  
  
```  
// valarray_class_op_ls.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 8 ), vaR ( 8 );  
   for ( i = 0 ; i < 8 ; i += 2 )  
      vaL [ i ] =  1;  
   for ( i = 1 ; i < 8 ; i += 2 )  
      vaL [ i ] =  -1;  
   for ( i = 0 ; i < 8 ; i++ )  
      vaR [ i ] =  i;  
  
   cout << "The initial operand valarray is: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The  right valarray is: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaL <<= vaR;  
   cout << "The element-by-element result of "  
        << "the left shift\n on the operand array is the valarray:\n ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial operand valarray is: ( 1 -1 1 -1 1 -1 1 -1 ).  
The  right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the left shift  
 on the operand array is the valarray:  
 ( 1 -2 4 -8 16 -32 64 -128 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatorstareqa-valarrayoperator"></a><a name="valarray__operator_star_eq"></a>  valarray:: Operator * =  
 Multipliziert die Elemente einer angegebenen Valarray oder ein Wert vom Typ Elements element-wise, um ein Wertarray Operanden.  
  
```  
valarray<Type>& operator*=(const valarray<Type>& right);

valarray<Type>& operator*=(const Type& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` right`  
 Die Valarray oder der Wert für einen Elementtyp, der Operand Wertarray, die Operanden Wertarray element-wise, multiplizieren.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wertarray, dessen Elemente elementweisen Produkts von Operanden Wertarray sind, und ` right.`  
  
### <a name="example"></a>Beispiel  
  
```  
// valarray_op_emult.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 8 ), vaR ( 8 );  
   for ( i = 0 ; i < 8 ; i += 2 )  
      vaL [ i ] =  2;  
   for ( i = 1 ; i < 8 ; i += 2 )  
      vaL [ i ] =  -1;  
   for ( i = 0 ; i < 8 ; i++ )  
      vaR [ i ] =  i;  
  
   cout << "The initial valarray is: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaL *= vaR;  
   cout << "The element-by-element result of "  
        << "the multiplication is the\n valarray: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).  
The initial Right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the multiplication is the  
 valarray: ( 0 -1 4 -3 8 -5 12 -7 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatoradda-valarrayoperator"></a><a name="valarray__operator_add"></a>  valarray:: Operator +  
 Ein unärer Operator, der ein Pluszeichen für jedes Element in einem Valarray gilt.  
  
```  
valarray<Type> operator+() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wertarray, dessen Elemente sowie die des Operanden Arrays sind.  
  
### <a name="example"></a>Beispiel  
  
```  
// valarray_op_eplus.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 );  
   valarray<int> vaPLUS ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL [ i ] =  -i;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL [ i ] =  i-1;  
  
   cout << "The initial valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   vaPLUS = +vaL;  
   cout << "The element-by-element result of "  
        << "the operator+ is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaPLUS [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is:  ( 0 0 -2 2 -4 4 -6 6 -8 8 ).  
The element-by-element result of the operator+ is the  
 valarray: ( 0 0 -2 2 -4 4 -6 6 -8 8 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatoraddeqa-valarrayoperator"></a><a name="valarray__operator_add_eq"></a>  valarray:: Operator +=  
 Fügt die Elemente einer angegebenen Valarray oder ein Wert vom Typ Elements element-wise, auf ein Wertarray Operanden.  
  
```  
valarray<Type>& operator+=(const valarray<Type>& right);

valarray<Type>& operator+=(const Type& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` right`  
 Die Valarray oder Wert eines Elementtyps identisch mit dem der Operand Wertarray, die, element-wise, Operand Wertarray hinzugefügt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wertarray, dessen Elemente die elementweisen Summe der Operanden Wertarray sind, und ` right.`  
  
### <a name="example"></a>Beispiel  
  
```  
// valarray_op_eadd.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 8 ), vaR ( 8 );  
   for ( i = 0 ; i < 8 ; i += 2 )  
      vaL [ i ] =  2;  
   for ( i = 1 ; i < 8 ; i += 2 )  
      vaL [ i ] =  -1;  
   for ( i = 0 ; i < 8 ; i++ )  
      vaR [ i ] =  i;  
  
   cout << "The initial valarray is: ( ";  
      for (i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial  right valarray is: ( ";  
      for (i = 0 ; i < 8 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaL += vaR;  
   cout << "The element-by-element result of "  
        << "the sum is the\n valarray: ( ";  
      for (i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is: ( 2 -1 2 -1 2 -1 2 -1 ).  
The initial  right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the sum is the  
 valarray: ( 2 0 4 2 6 4 8 6 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperator-a-valarrayoperator-"></a><a name="valarray__operator-"></a>  valarray:: Operator-  
 Ein unärer Operator, der ein Minuszeichen für jedes Element in einem Valarray gilt.  
  
```  
valarray<Type> operator-() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wertarray, dessen Elemente abzüglich des Operanden Arrays sind.  
  
### <a name="example"></a>Beispiel  
  
```  
// valarray_op_eminus.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 );  
   valarray<int> vaMINUS ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL [ i ] =  -i;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL [ i ] =  i-1;  
  
   cout << "The initial valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   vaMINUS = -vaL;  
   cout << "The element-by-element result of "  
        << "the operator+ is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaMINUS [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is:  ( 0 0 -2 2 -4 4 -6 6 -8 8 ).  
The element-by-element result of the operator+ is the  
 valarray: ( 0 0 2 -2 4 -4 6 -6 8 -8 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperator-eqa-valarrayoperator-"></a><a name="valarray__operator-_eq"></a>  valarray:: Operator =  
 Subtrahiert die Elemente einer angegebenen Valarray oder ein Wert vom Typ Elements element-wise, aus der ein Wertarray Operanden.  
  
```  
valarray<Type>& operator-=(const valarray<Type>& right);

valarray<Type>& operator-=(const Type& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` right`  
 Die Valarray oder der Wert für einen Elementtyp, der Operand Wertarray, die, element-wise, vom Operanden Wertarray subtrahiert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wertarray, dessen Elemente die elementweisen Differenz der Operand Wertarray sind, und ` right.`  
  
### <a name="example"></a>Beispiel  
  
```  
// valarray_op_esub.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 8 ), vaR ( 8 );  
   for ( i = 0 ; i < 8 ; i += 2 )  
      vaL [ i ] =  10;  
   for ( i = 1 ; i < 8 ; i += 2 )  
      vaL [ i ] =  0;  
   for ( i = 0 ; i < 8 ; i++ )  
      vaR [ i ] =  i;  
  
   cout << "The initial valarray is: ( ";  
      for (i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial  right valarray is: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaL -= vaR;  
   cout << "The element-by-element result of "  
        << "the difference is the\n valarray: ( ";  
      for ( i = 0 ; i < 8 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is: ( 10 0 10 0 10 0 10 0 ).  
The initial  right valarray is: ( 0 1 2 3 4 5 6 7 ).  
The element-by-element result of the difference is the  
 valarray: ( 10 -1 8 -3 6 -5 4 -7 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatoreqa-valarrayoperator"></a><a name="valarray__operator__eq"></a>  valarray:: Operator / =  
 Teilt ein Wertarray Operand element-wise durch die Elemente einer angegebenen Valarray oder ein Wert vom Typ Elements.  
  
```  
valarray<Type>& operator/=(const valarray<Type>& right);

valarray<Type>& operator/=(const Type& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` right`  
 Die Valarray oder der Wert für einen Elementtyp, der Operand Wertarray, die, element-wise, Wertarray Operanden geteilt werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wertarray, dessen Elemente die elementweisen Quotienten Wertarray Operanden sind, geteilt durch ` right.`  
  
### <a name="example"></a>Beispiel  
  
```  
// valarray_op_ediv.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<double> vaL ( 6 ), vaR ( 6 );  
   for ( i = 0 ; i < 6 ; i += 2 )  
      vaL [ i ] =  100;  
   for ( i = 1 ; i < 6 ; i += 2 )  
      vaL [ i ] =  -100;  
   for ( i = 0 ; i < 6 ; i++ )  
      vaR [ i ] =  2*i;  
  
   cout << "The initial valarray is: ( ";  
      for (i = 0 ; i < 6 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
      for (i = 0 ; i < 6 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaL /= vaR;  
   cout << "The element-by-element result of "  
        << "the quotient is the\n valarray: ( ";  
      for (i = 0 ; i < 6 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray is: ( 100 -100 100 -100 100 -100 ).  
The initial Right valarray is: ( 0 2 4 6 8 10 ).  
The element-by-element result of the quotient is the  
 valarray: ( 1.#INF -50 25 -16.6667 12.5 -10 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatoreqa-valarrayoperator"></a><a name="valarray__operator_eq"></a>  valarray:: Operator =  
 Ein Wertarray, deren Werte, entweder direkt oder als Teil von einigen anderen Valarray oder ein Slice_array, Gslice_array, Mask_array oder Indirect_array angegeben sind-Elementen zugewiesen.  
  
```  
valarray<Type>& operator=(const valarray<Type>& right);

valarray<Type>& operator=(valarray<Type>&& right);

valarray<Type>& operator=(const Type& val);

valarray<Type>& operator=(const slice_array<Type>& _Slicearray);

valarray<Type>& operator=(const gslice_array<Type>& _Gslicearray);

valarray<Type>& operator=(const mask_array<Type>& _Maskarray);

valarray<Type>& operator=(const indirect_array<Type>& _Indarray);
```  
  
### <a name="parameters"></a>Parameter  
 ` right`  
 Valarray Operand Wertarray kopiert werden soll.  
  
 ` val`  
 Der Wert, der die Elemente der Operand Wertarray zugewiesen werden soll.  
  
 `_Slicearray`  
 Die Slice_array-Operand Wertarray kopiert werden soll.  
  
 `_Gslicearray`  
 Die Gslice_array-Operand Wertarray kopiert werden soll.  
  
 `_Maskarray`  
 Die Mask_array-Operand Wertarray kopiert werden soll.  
  
 `_Indarray`  
 Die Indirect_array-Operand Wertarray kopiert werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Der erste Memberoperator ersetzt die kontrollierte Sequenz mit einer Kopie der Sequenz von ` right`.  
  
 Der zweite Memberoperator ist identisch mit der ersten, aber mit einem [Rvalue-Verweisdeklarator: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
 Der dritte Memberoperator ersetzt jedes Element der kontrollierten Sequenz mit einer Kopie des ` val`.  
  
 Ersetzen Sie die verbleibenden Member-Operatoren die Elemente der kontrollierten Sequenz durch ihre Argumente, die nur von generiert werden ausgewählt [Operator &#91; &#93;](#valarray__operator_at).  
  
 Wenn der Wert eines Elements in der gesteuerten-Ersatzsequenz für ein Element in die ursprüngliche gesteuerte Sequenz abhängig ist, ist das Ergebnis nicht definiert.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Länge der kontrollierten Sequenz geändert wird, ist das Ergebnis in der Regel nicht definiert. In dieser Implementierung ist jedoch die Auswirkungen nur für ungültig zu erklärende Zeiger oder Verweise auf Elemente in der kontrollierten Sequenz.  
  
### <a name="example"></a>Beispiel  
  
```  
// valarray_op_assign.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> va ( 10 ), vaR ( 10 );  
   for ( i = 0 ; i < 10 ; i += 1 )  
      va [ i ] = i;  
   for ( i = 0 ; i < 10 ; i+=1 )  
      vaR [ i ] = 10 -  i;  
  
   cout << "The operand valarray va is:";  
   for ( i = 0 ; i < 10 ; i++ )  
      cout << " " << va [ i ];  
   cout << endl;  
  
   cout << "The operand valarray vaR is:";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << " " << vaR [ i ];  
   cout << endl;  
  
   // Assigning vaR to va with the first member functon  
   va = vaR;  
   cout << "The reassigned valarray va is:";  
   for ( i = 0 ; i < 10 ; i++ )  
      cout << " " << va [ i ];  
   cout << endl;  
  
   // Assigning elements of value 10 to va  
   // with the second member functon  
   va = 10;  
   cout << "The reassigned valarray va is:";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << " " << va [ i ];  
   cout << endl;  
}  
\* Output:   
The operand valarray va is: 0 1 2 3 4 5 6 7 8 9  
The operand valarray vaR is: 10 9 8 7 6 5 4 3 2 1  
The reassigned valarray va is: 10 9 8 7 6 5 4 3 2 1  
The reassigned valarray va is: 10 10 10 10 10 10 10 10 10 10  
*\  
```  
  
##  <a name="a-namevalarrayoperatorata-valarrayoperator"></a><a name="valarray__operator_at"></a>  valarray:: Operator]  
 Gibt einen Verweis auf ein Element oder auf den Wert zurück, den es am angegebenen Index oder in der angegebenen Teilmenge hat.  
  
```  
Type& operator[](size_t _Off);

slice_array<Type> operator[](slice _Slicearray);

gslice_array<Type> operator[](const gslice& _Gslicearray);

mask_array<Type> operator[](const valarray<bool>& _Boolarray);

indirect_array<Type> operator[](const valarray<size_t>& _Indarray);

Type operator[](size_t _Off) const;

 
valarray<Type> operator[](slice _Slice) const;

 
valarray<Type> operator[](const gslice& _Gslicearray) const;

 
valarray<Type> operator[](const valarray<bool>& _Boolarray) const;

 
valarray<Type> operator[](const valarray<size_t>& _Indarray) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Off`  
 Der Index des Elements, das ein Wert zugewiesen werden.  
  
 `_Slicearray`  
 Ein Slice_array von ein Wertarray, der angibt, eine Teilmenge ausgewählt oder an eine neue Wertarray zurückgegeben werden sollen.  
  
 `_Gslicearray`  
 Ein Gslice_array von ein Wertarray, der angibt, eine Teilmenge ausgewählt oder an eine neue Wertarray zurückgegeben werden sollen.  
  
 *_Boolarray*  
 Eine Bool_array von ein Wertarray, der angibt, eine Teilmenge ausgewählt oder an eine neue Wertarray zurückgegeben werden sollen.  
  
 `_Indarray`  
 Ein Indirect_array von ein Wertarray, der angibt, eine Teilmenge ausgewählt oder an eine neue Wertarray zurückgegeben werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf ein Element oder der Wert am angegebenen Index oder eine angegebene Teilmenge.  
  
### <a name="remarks"></a>Hinweise  
 Die Member-Operator wird überladen, um bieten mehrere Methoden zur Auswahl von Sequenzen von Elementen aus, die von *\****dies**. Die erste Gruppe von fünf Member-Operatoren funktionieren in Verbindung mit verschiedenen Überladungen von [Operator =](#valarray__operator_eq) (und andere Operatoren zuweisen) zum selektiven Austausch (slicing) der kontrollierten Sequenz. Die ausgewählten Elemente müssen vorhanden sein.  
  
 Beim Kompilieren mit _SECURE_SCL 1 wird ein Laufzeitfehler auftreten, wenn Sie versuchen, ein Element außerhalb der Grenzen des Wertarray zuzugreifen.  Weitere Informationen finden Sie unter [Checked Iterators](../standard-library/checked-iterators.md) .  
  
### <a name="example"></a>Beispiel  
  Beispiele finden Sie [Slice:: Slice](../standard-library/slice-class.md#slice__slice) und [gslice:: gslice](../standard-library/gslice-class.md#gslice__gslice) für ein Beispiel für das Deklarieren und verwenden Sie den Operator.  
  
##  <a name="a-namevalarrayoperatorxoreqa-valarrayoperator"></a><a name="valarray__operator_xor_eq"></a>  valarray:: Operator ^ =  
 Ruft die logische elementweisen exklusiver or -Operator ( **XOR**) eines Arrays mit einer angegebenen Valarray oder ein Wert, der den Elementtyp.  
  
```  
valarray<Type>& operator|=(const valarray<Type>& right);

valarray<Type>& operator|=(const Type& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` right`  
 Der Valarray oder den Wert des Elementtyps identisch mit dem der Operand Wertarray, die kombiniert werden, elementweisen, durch die logische exklusive **XOR** mit Operanden Wertarray.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wertarray, dessen Elemente die elementweisen, exklusive logische sind **XOR** der Operand Wertarray und ` right.`  
  
### <a name="remarks"></a>Hinweise  
 Ausschließliches logisches oder, als **XOR**, hat die folgende Semantik: bestehenden Elementen *e*1 und *e*2, *e*1 **XOR** *e*2 **true** trifft genau eines der Elemente; **false** Wenn beide Elemente falsch sind oder wenn beide Elemente zutrifft.  
  
### <a name="example"></a>Beispiel  
  
```  
// valarray_op_exor.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 ), vaR ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL [ i ] =  1;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL [ i ] =  0;  
   for ( i = 0 ; i < 10 ; i += 3 )  
      vaR [ i ] =  i;  
   for ( i = 1 ; i < 10 ; i += 3 )  
      vaR [ i ] =  i-1;  
   for ( i = 2 ; i < 10 ; i += 3 )  
      vaR [ i ] =  i-1;  
  
   cout << "The initial operand valarray is:  ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The  right valarray is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaL ^= vaR;  
   cout << "The element-by-element result of "  
        << "the bitwise XOR operator^= is the\n valarray: ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial operand valarray is:  ( 1 0 1 0 1 0 1 0 1 0 ).  
The  right valarray is: ( 0 0 1 3 3 4 6 6 7 9 ).  
The element-by-element result of the bitwise XOR operator^= is the  
 valarray: ( 1 0 0 3 2 4 7 6 6 9 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatororeqa-valarrayoperator124"></a><a name="valarray__operator_or_eq"></a>  valarray:: Operator &#124; =  
 Ruft die bitweise `OR` von Elementen in einem Array mit den entsprechenden Elementen in einer angegebenen Valarray oder ein Wert vom Typ Elements.  
  
```  
valarray<Type>& operator|=(const valarray<Type>& right);

valarray<Type>& operator|=(const Type& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` right`  
 Der Valarray oder den Wert des Elementtyps identisch mit dem der Operand Wertarray, die kombiniert werden, elementweisen, indem der bitweise `OR` mit Operanden Wertarray.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wertarray bitweise, dessen Elemente die elementweisen sind `OR` des Operanden Wertarray durch ` right.`  
  
### <a name="remarks"></a>Hinweise  
 Eine bitweise Operation kann nur verwendet werden, zum Bearbeiten von Bits in `char` und `int` Datentypen und Varianten und nicht auf **Float**, **doppelte**, **Longdouble**, `void`, `bool`, oder andere komplexeren Datentypen.  
  
 Der bitweise `OR` hat die gleichen Wahrheitstabelle als logischen `OR` gelten jedoch für den Datentyp auf der Ebene der einzelnen Bits. Bits angegebenen *b*1 und *b*2 *b*1 `OR` *b*2 **true** Wenn mindestens eines der Bits true ist; **false** beide false sind.  
  
### <a name="example"></a>Beispiel  
  
```  
// valarray_class_op_bitor.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 ), vaR ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL [ i ] =  1;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL [ i ] =  0;  
   for ( i = 0 ; i < 10 ; i += 3 )  
      vaR [ i ] =  i;  
   for ( i = 1 ; i < 10 ; i += 3 )  
      vaR [ i ] =  i-1;  
   for ( i = 2 ; i < 10 ; i += 3 )  
      vaR [ i ] =  i-1;  
  
   cout << "The initial operand valarray is:\n ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The  right valarray is:\n ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaL |= vaR;  
   cout << "The element-by-element result of "  
        << "the logical OR\n operator|= is the valarray:\n ( ";  
      for (i = 0 ; i < 10 ; i++ )  
         cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial operand valarray is:  
 ( 1 0 1 0 1 0 1 0 1 0 ).  
The  right valarray is:  
 ( 0 0 1 3 3 4 6 6 7 9 ).  
The element-by-element result of the logical OR  
 operator|= is the valarray:  
 ( 1 0 1 3 3 4 7 6 7 9 ).  
*\  
```  
  
##  <a name="a-namevalarrayoperatordtora-valarrayoperator"></a><a name="valarray__operator_dtor"></a>  valarray:: Operator ~  
 Ein unärer Operator, der den bitweisen erhält **NICHT** Werte der einzelnen Elemente in ein Wertarray.  
  
```  
valarray<Type> operator~() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Valarray von booleschen Werten, die das bitweise **NICHT** der Elementwerte der Operanden Wertarray.  
  
### <a name="remarks"></a>Hinweise  
 Eine bitweise Operation kann nur verwendet werden, zum Bearbeiten von Bits in `char` und `int` Datentypen und Varianten und nicht auf **Float**, **doppelte**, **Longdouble**, `void`, `bool` oder andere komplexeren Datentypen.  
  
 Der bitweise **NICHT** hat die gleichen Wahrheitstabelle als das logische **NICHT** gelten jedoch für den Datentyp auf der Ebene der einzelnen Bits. Bit angegeben *b*, ~ *b* ist true, wenn *b* ist "false", und false, wenn *b* gilt. Das logische **NICHT**[Operator!](#valarray__operator_not) gilt für eine Elementebene zählen alle ungleich NULL-Werte als **true**, und das Ergebnis ist ein Wertarray von booleschen Werten. Der bitweise **NOToperator ~**, dagegen kann dazu führen, dass ein Wertarray Werte als 0 oder 1, je nach Ergebnis der bitweisen Operation.  
  
### <a name="example"></a>Beispiel  
  
```  
// valarray_op_bitnot.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<unsigned short int> vaL1 ( 10 );  
   valarray<unsigned short int> vaNOT1 ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL1 [ i ] =  i;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL1 [ i ] =  5*i;  
  
   cout << "The initial valarray <unsigned short int> is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL1 [ i ] << " ";  
   cout << ")." << endl;  
  
   vaNOT1 = ~vaL1;  
   cout << "The element-by-element result of "  
        << "the bitwise NOT operator~ is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaNOT1 [ i ] << " ";  
   cout << ")." << endl << endl;  
  
   valarray<int> vaL2 ( 10 );  
   valarray<int> vaNOT2 ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      vaL2 [ i ] =  i;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      vaL2 [ i ] =  -2 * i;  
  
   cout << "The initial valarray <int> is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaL2 [ i ] << " ";  
   cout << ")." << endl;  
  
   vaNOT2 = ~vaL2;  
   cout << "The element-by-element result of "  
        << "the bitwise NOT operator~ is the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaNOT2 [ i ] << " ";  
   cout << ")." << endl;  
  
   // The negative numbers are represented using  
   // the two's complement approach, so adding one  
   // to the flipped bits returns the negative elements  
   vaNOT2 = vaNOT2 + 1;  
   cout << "The element-by-element result of "  
        << "adding one\n is the negative of the "  
        << "original elements the\n valarray: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << vaNOT2 [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial valarray <unsigned short int> is:  ( 0 5 2 15 4 25 6 35 8 45 ).  
The element-by-element result of the bitwise NOT operator~ is the  
 valarray: ( 65535 65530 65533 65520 65531 65510 65529 65500 65527 65490 ).  
  
The initial valarray <int> is:  ( 0 -2 2 -6 4 -10 6 -14 8 -18 ).  
The element-by-element result of the bitwise NOT operator~ is the  
 valarray: ( -1 1 -3 5 -5 9 -7 13 -9 17 ).  
The element-by-element result of adding one  
 is the negative of the original elements the  
 valarray: ( 0 2 -2 6 -4 10 -6 14 -8 18 ).  
*\  
```  
  
##  <a name="a-namevalarrayresizea-valarrayresize"></a><a name="valarray__resize"></a>  valarray:: Resize  
 Ändert die Anzahl der Elemente in einem „valarray“ auf eine bestimmte Anzahl.  
  
```  
void resize(
    size_t _Newsize);

void resize(
    size_t _Newsize,   
    const Type val);
```  
  
### <a name="parameters"></a>Parameter  
 `_Newsize`  
 Die Anzahl der Elemente im „valarray“, dessen Größe angepasst wird.  
  
 ` val`  
 Der Wert, der an die Elemente des „valarray“ übergeben wird, dessen Größe angepasst wird.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion initialisiert Elemente mit ihrem standardmäßigen Konstruktor.  
  
 Zeiger oder Verweise auf Elemente in der kontrollierten Sequenz werden ungültig.  
  
### <a name="example"></a>Beispiel  
  Im folgenden Beispiel wird die Verwendung der Memberfunktion „valarray::resize“ gezeigt.  
  
```  
// valarray_resize.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    int i;  
    size_t size1, sizeNew;  
  
    valarray<int> va1(10);  
    for (i = 0; i < 10; i+=1)  
        va1[i] = i;  
  
    cout << "The valarray contains ( ";  
        for (i = 0; i < 10; i++)  
            cout << va1[i] << " ";  
    cout << ")." << endl;  
  
    size1 = va1.size();  
    cout << "The number of elements in the valarray is: "  
         << size1  << "." <<endl << endl;  
  
    va1.resize(15, 10);  
  
    cout << "The valarray contains ( ";  
        for (i = 0; i < 15; i++)  
            cout << va1[i] << " ";  
    cout << ")." << endl;  
    sizeNew = va1.size();  
    cout << "The number of elements in the resized valarray is: "  
         << sizeNew  << "." <<endl << endl;  
}  
\* Output:   
The valarray contains ( 0 1 2 3 4 5 6 7 8 9 ).  
The number of elements in the valarray is: 10.  
  
The valarray contains ( 10 10 10 10 10 10 10 10 10 10 10 10 10 10 10 ).  
The number of elements in the resized valarray is: 15.  
*\  
```  
  
##  <a name="a-namevalarrayshifta-valarrayshift"></a><a name="valarray__shift"></a>  valarray:: Shift  
 Alle Elemente in einem Valarray verschiebt eine angegebene Anzahl von stellen.  
  
```  
valarray<Type> shift(int count) const;
```  
  
### <a name="parameters"></a>Parameter  
 ` count`  
 Die Anzahl der stellen die Elemente sind vorwärts verschoben werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine neue, in dem alle Elemente wurden verschoben, Wertarray ` count` Positionen nach vorn Wertarray, in Bezug auf ihre Positionen im Wertarray Operanden nach links.  
  
### <a name="remarks"></a>Hinweise  
 Ein positiver Wert von ` count` verschiebt die Elemente bleiben ` count` platziert, die mit 0 (null) ausfüllen.  
  
 Ein negativer Wert von ` count` verschiebt die Elemente nach rechts ` count` platziert, die mit 0 (null) ausfüllen.  
  
### <a name="example"></a>Beispiel  
  
```  
// valarray_shift.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> va1 ( 10 ), va2 ( 10 );  
   for ( i = 0 ; i < 10 ; i += 1 )  
      va1 [ i ] =  i;  
   for ( i = 0 ; i < 10 ; i += 1 )  
      va2 [ i ] = 10 -  i;  
  
   cout << "The operand valarray va1(10) is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va1 [ i ] << " ";  
   cout << ")." << endl;  
  
   // A positive parameter shifts elements left  
   va1 = va1.shift ( 4 );  
   cout << "The shifted valarray va1 is: va1.shift (4) = ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va1 [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The operand valarray va2(10) is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va2 [ i ] << " ";  
   cout << ")." << endl;  
  
   // A negative parameter shifts elements right  
   va2 = va2.shift ( - 4 );  
   cout << "The shifted valarray va2 is: va2.shift (-4) = ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va2 [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The operand valarray va1(10) is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The shifted valarray va1 is: va1.shift (4) = ( 4 5 6 7 8 9 0 0 0 0 ).  
The operand valarray va2(10) is: ( 10 9 8 7 6 5 4 3 2 1 ).  
The shifted valarray va2 is: va2.shift (-4) = ( 0 0 0 0 10 9 8 7 6 5 ).  
*\  
```  
  
##  <a name="a-namevalarraysizea-valarraysize"></a><a name="valarray__size"></a>  valarray:: Size  
 Gibt die Anzahl von Elementen in einem Wertarray zurück.  
  
```  
size_t size() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Operandenwertarray.  
  
### <a name="example"></a>Beispiel  
  Im folgenden Beispiel wird die Verwendung der Memberfunktion „valarray::size“ gezeigt.  
  
```  
// valarray_size.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    int i;  
    size_t size1, size2;  
  
    valarray<int> va1(10), va2(12);  
    for (i = 0; i < 10; i += 1)  
        va1[i] =  i;  
    for (i = 0; i < 10; i += 1)  
        va2[i] =  i;  
  
    cout << "The operand valarray va1(10) is: ( ";  
        for (i = 0; i < 10; i++)  
            cout << va1[i] << " ";  
    cout << ")." << endl;  
  
    size1 = va1.size();  
    cout << "The number of elements in the valarray va1 is: va1.size = "  
         << size1  << "." <<endl << endl;  
  
    cout << "The operand valarray va2(12) is: ( ";  
        for (i = 0; i < 10; i++)  
            cout << va2[i] << " ";  
    cout << ")." << endl;  
  
    size2 = va2.size();  
    cout << "The number of elements in the valarray va2 is: va2.size = "  
         << size2  << "." << endl << endl;  
  
    // Initializing two more elements to va2  
    va2[10] = 10;  
    va2[11] = 11;  
    cout << "After initializing two more elements,\n "  
         << "the operand valarray va2(12) is now: ( ";  
        for (i = 0; i < 12; i++)  
            cout << va2[i] << " ";  
    cout << ")." << endl;  
    cout << "The number of elements in the valarray va2 is still: "  
         << size2  << "." << endl;  
}  
\* Output:   
The operand valarray va1(10) is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The number of elements in the valarray va1 is: va1.size = 10.  
  
The operand valarray va2(12) is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The number of elements in the valarray va2 is: va2.size = 12.  
  
After initializing two more elements,  
 the operand valarray va2(12) is now: ( 0 1 2 3 4 5 6 7 8 9 10 11 ).  
The number of elements in the valarray va2 is still: 12.  
*\  
```  
  
##  <a name="a-namevalarraysuma-valarraysum"></a><a name="valarray__sum"></a>  valarray:: Sum  
 Bestimmt die Summe aller Elemente in einem Valarray Länge ungleich NULL.  
  
```  
Type sum() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Summe der Elemente des Operanden Wertarray.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die Länge größer als eins ist, fügt die Memberfunktion Werte der Summe durch Anwenden `operator+=` zwischen Paare von Elementen der Klasse **Typ**, welcher Operator, daher muss angegeben werden für Elemente des Typs **Typ**.  
  
### <a name="example"></a>Beispiel  
  
```  
// valarray_sum.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   int sumva = 0;  
  
   valarray<int> va ( 10 );  
   for ( i = 0 ; i < 10 ; i+=1 )  
      va [ i ] =  i;  
  
   cout << "The operand valarray va (10) is: ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
  
   sumva = va.sum ( );  
   cout << "The sum of elements in the valarray is: "  
        << sumva  << "." <<endl;  
}  
\* Output:   
The operand valarray va (10) is: ( 0 1 2 3 4 5 6 7 8 9 ).  
The sum of elements in the valarray is: 45.  
*\  
```  
  
##  <a name="a-namevalarrayswapa-valarrayswap"></a><a name="valarray__swap"></a>  valarray:: Swap  
 Tauscht die Elemente zweier `valarray`n.  
  
```  
void swap(valarray& right);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|` right`|Ein `valarray`-Objekt, das die auszutauschenden Elemente bereitgestellt.|  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion tauscht die kontrollierten Sequenzen zwischen `*this` und ` right` aus. Sie führt dies in einer konstanten Zeit aus, sie löst keine Ausnahmen aus, und sie macht keine Verweise, Zeiger oder Iteratoren ungültig, die Elemente in den beiden kontrollierten Sequenzen bestimmen.  
  
##  <a name="a-namevalarrayvalarraya-valarrayvalarray"></a><a name="valarray__valarray"></a>  valarray:: valarray  
 Erstellt ein Wertarray einer bestimmten Größe bzw. eins mit Elementen eines bestimmten Werts oder als Kopie eines anderen Wertarrays oder als Teilmenge eines anderen Wertarrays.  
  
```  
valarray();

explicit valarray(
    size_t Count);

valarray(
    const Type& Val,   
    size_t Count);

valarray(
    const Type* Ptr,   
    size_t Count);

valarray(
    const valarray<Type>& Right);

valarray(
    const slice_array<Type>& SliceArray);

valarray(
    const gslice_array<Type>& GsliceArray);

valarray(
    const mask_array<Type>& MaskArray);

valarray(
    const indirect_array<Type>& IndArray);

valarray(
    valarray<Type>&& Right);

valarray(
    initializer_list<Type> IList);
```  
  
### <a name="parameters"></a>Parameter  
 `Count`  
 Die Anzahl von Elementen im Wertarray.  
  
 `Val`  
 Der beim Initialisieren der Elemente im Wertarray zu verwendende Wert.  
  
 `Ptr`  
 Zeiger auf die beim Initialisieren der Elemente im Wertarray zu verwendenden Werte.  
  
 `Right`  
 Ein vorhandenes Wertarray, mit dem das neue Wertarray initialisiert wird.  
  
 `SliceArray`  
 Ein slice_array-Element, dessen Elementwerte beim Initialisieren der Elemente des zu erstellenden Wertarrays verwendet werden sollen.  
  
 `GsliceArray`  
 Ein gslice_array-Element, dessen Elementwerte beim Initialisieren der Elemente des zu erstellenden Wertarrays verwendet werden sollen.  
  
 `MaskArray`  
 Ein mask_array-Element, dessen Elementwerte beim Initialisieren der Elemente des zu erstellenden Wertarrays verwendet werden sollen.  
  
 `IndArray`  
 Ein indirect_array-Element, dessen Elementwerte beim Initialisieren der Elemente des zu erstellenden Wertarrays verwendet werden sollen.  
  
 `IList`  
 Das initializer_list-Element, in dem die zu kopierenden Elemente enthalten sind.  
  
### <a name="remarks"></a>Hinweise  
 Der erste (standardmäßige) Konstruktor initialisiert das Objekt in ein leeres Array. Mit den folgenden drei Konstruktoren wird jeweils wie folgt das Objekt in einem Array von `Count`-Elementen initialisiert:  
  
-   Bei expliziten `valarray(size_t Count)` wird jedes Element mit dem Standardkonstruktor initialisiert.  
  
-   Bei `valarray(const Type& Val, Count)` wird jedes Element mit `Val` initialisiert.  
  
-   Für `valarray(const Type* Ptr, Count)`, das Element an Position `I` wird initialisiert, wobei `Ptr`[ `I`].  
  
 Jeder verbleibende Konstruktor initialisiert das Objekt in einem Valarray \< Type> -Objekt, indem die im Argument angegebene Teilmenge bestimmt.  
  
 Der letzte Konstruktor entspricht dem neben dem letzten, jedoch mit einer [Rvalue-Verweisdeklarator: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
### <a name="example"></a>Beispiel  
  
```  
// valarray_ctor.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    int i;  
  
    // The second member function  
    valarray<int> va(10);  
    for (auto i : va){  
        va[i] = 2 * (i + 1);  
    }  
  
    cout << "The operand valarray va is:\n(";  
    for (auto i : va) {  
        cout << " " << va[i];  
    }  
    cout << " )" << endl;  
  
    slice Slice(2, 4, 3);  
  
    // The fifth member function  
    valarray<int> vaSlice = va[Slice];  
  
    cout << "The new valarray initialized from the slice is vaSlice ="  
        << "\nva[slice( 2, 4, 3)] = (";  
    for (int i = 0; i < 3; i++) {  
        cout << " " << vaSlice[i];  
    }  
    cout << " )" << endl;  
  
    valarray<int> va2{{ 1, 2, 3, 4 }};  
    for (auto& v : va2){  
        cout << v << " ";  
    }  
    cout << endl;  
}  
  
```  
  
```Output  
The operand valarray va is:( 0 2 2 2 2 2 2 2 2 2 )The new valarray initialized from the slice is vaSlice =va[slice( 2, 4, 3)] = ( 0 0 0 )1 2 3 4  
```  
  
##  <a name="a-namevalarrayvaluetypea-valarrayvaluetype"></a><a name="valarray__value_type"></a>  valarray:: value_type  
 Ein Typ, der den Typ der in einem Valarray gespeicherten Elements darstellt.  
  
```  
typedef Type value_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter **Typ**.  
  
### <a name="example"></a>Beispiel  
  
```  
// valarray_value_type.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
   valarray<int> va ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )  
      va [ i ] =  i;  
   for ( i = 1 ; i < 10 ; i += 2 )  
      va [ i ] =  -1;  
  
   cout << "The initial operand valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
  
   // value_type declaration and initialization:  
   valarray<int>::value_type Right = 10;  
  
   cout << "The decalared value_type Right is: "   
           << Right << endl;  
   va *= Right;  
   cout << "The resulting valarray is:  ( ";  
      for ( i = 0 ; i < 10 ; i++ )  
         cout << va [ i ] << " ";  
   cout << ")." << endl;  
}  
\* Output:   
The initial operand valarray is:  ( 0 -1 2 -1 4 -1 6 -1 8 -1 ).  
The decalared value_type Right is: 10  
The resulting valarray is:  ( 0 -10 20 -10 40 -10 60 -10 80 -10 ).  
*\  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)

