---
title: "numpunct-Klasse"
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
  - "xlocnum/std::numpunct"
  - "std::numpunct"
  - "numpunct"
  - "std.numpunct"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "numpunct-Klasse"
ms.assetid: 73fb93cc-ac11-4c98-987c-bfa6267df596
caps.latest.revision: 22
caps.handback.revision: "22"
ms.author: "corob"
manager: "ghogen"
---
# numpunct-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Vorlagenklasse, die ein Objekt beschreibt, das als lokales Facet dienen kann, um die Sequenzen vom Typ `CharType` zu beschreiben, mit denen Informationen zur Formatierung und Interpunktion von numerischen und booleschen Ausdrücken dargestellt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class CharType>  
class numpunct : public locale::facet;  
```  
  
#### <a name="parameters"></a>Parameter  
 `CharType`  
 Der Typ, der innerhalb eines Programms zum Codieren von Zeichen in einem Gebietsschema verwendet wird.  
  
## <a name="remarks"></a>Hinweise  
 Wie bei jedem Gebietsschemafacet hat die statische Objekt-ID einen anfänglichen gespeicherten Wert von NULL. Beim erste Versuch, den gespeicherten Wert zuzugreifen speichert einen eindeutigen positiven Wert in **Id.**  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[numpunct](#numpunct__numpunct)|Der Konstruktor für Objekte des Typs `numpunct`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#numpunct__char_type)|Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.|  
|[string_type](#numpunct__string_type)|Ein Typ, der eine Zeichenfolge beschreibt, die Zeichen vom Typ `CharType` enthält.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[decimal_point](#numpunct__decimal_point)|Gibt ein gebietsschemaspezifisches Element zurück, das als Dezimaltrennzeichen verwendet werden soll.|  
|[do_decimal_point](#numpunct__do_decimal_point)|Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um ein gebietsschemaspezifisches Element zurückzugeben, das als Dezimaltrennzeichen verwendet werden soll.|  
|[do_falsename](#numpunct__do_falsename)|Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine Zeichenfolge zurückzugeben, die als Textdarstellung des Werts `false` verwendet werden soll.|  
|[do_grouping](#numpunct__do_grouping)|Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine gebietsschemaspezifische Regel zur Bestimmung zurückzugeben, wie Ziffern auf der linken Seite eines Dezimaltrennzeichens gruppiert werden.|  
|[do_thousands_sep](#numpunct__do_thousands_sep)|Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um ein gebietsschemaspezifisches Element zurückzugeben, das als Tausendertrennzeichen verwendet werden soll.|  
|[do_truename](#numpunct__do_truename)|Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine Zeichenfolge zurückzugeben, die als Textdarstellung des Werts `true` verwendet werden soll.|  
|[falsename](#numpunct__falsename)|Gibt eine Zeichenfolge zurück, die als Textdarstellung des Werts `false` verwendet werden soll.|  
|[Gruppieren](#numpunct__grouping)|Gibt eine gebietsschemaspezifische Regel zur Bestimmung zurück, wie Ziffern auf der linken Seite eines Dezimaltrennzeichens gruppiert werden sollen.|  
|[thousands_sep](#numpunct__thousands_sep)|Gibt ein gebietsschemaspezifisches Element zurück, das als Tausendertrennzeichen verwendet werden soll.|  
|[TrueName](#numpunct__truename)|Gibt eine Zeichenfolge zurück, die als Textdarstellung des Werts `true` verwendet werden soll.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \< Gebietsschema>  
  
 **Namespace:** std  
  
##  <a name="a-namenumpunctchartypea-numpunctchartype"></a><a name="numpunct__char_type"></a>  numpunct:: char_type  
 Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter **CharType.**  
  
##  <a name="a-namenumpunctdecimalpointa-numpunctdecimalpoint"></a><a name="numpunct__decimal_point"></a>  numpunct:: decimal_point  
 Gibt ein gebietsschemaspezifisches Element zurück, das als Dezimaltrennzeichen verwendet werden soll.  
  
```  
CharType decimal_point() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Gebietsschema-Element, das als Dezimaltrennzeichen verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [Do_decimal_point](#numpunct__do_decimal_point).  
  
### <a name="example"></a>Beispiel  
  
```  
// numpunct_decimal_point.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const numpunct <char> &npunct =   
   use_facet <numpunct <char> >( loc);  
   cout << loc.name( ) << " decimal point "<<   
   npunct.decimal_point( ) << endl;  
   cout << loc.name( ) << " thousands separator "   
   << npunct.thousands_sep( ) << endl;  
};  
```  
  
```Output  
German_Germany.1252 decimal point ,  
German_Germany.1252 thousands separator .  
```  
  
##  <a name="a-namenumpunctdodecimalpointa-numpunctdodecimalpoint"></a><a name="numpunct__do_decimal_point"></a>  numpunct:: do_decimal_point  
 Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um ein gebietsschemaspezifisches Element zurückzugeben, das als Dezimaltrennzeichen verwendet werden soll.  
  
```  
virtual CharType do_decimal_point() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Gebietsschema-Element, das als Dezimaltrennzeichen verwendet.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Decimal_point](#numpunct__decimal_point), bei dem die virtuelle Memberfunktion, indem aufgerufen wird `decimal_point`.  
  
##  <a name="a-namenumpunctdofalsenamea-numpunctdofalsename"></a><a name="numpunct__do_falsename"></a>  numpunct:: do_falsename  
 Die geschützte virtuelle Memberfunktion gibt eine Sequenz, die als eine Textdarstellung des Werts verwenden **false**.  
  
```  
virtual string_type do_falsename() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die eine Sequenz, die als eine Textdarstellung des Werts verwenden **false**.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt die Zeichenfolge "False", um die Darstellung des Werts **false** in allen Gebietsschemas.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Falsename](#numpunct__falsename), bei dem die virtuelle Memberfunktion, indem aufgerufen wird `falsename`.  
  
##  <a name="a-namenumpunctdogroupinga-numpunctdogrouping"></a><a name="numpunct__do_grouping"></a>  numpunct:: do_grouping  
 Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine gebietsschemaspezifische Regel zur Bestimmung zurückzugeben, wie Ziffern auf der linken Seite eines Dezimaltrennzeichens gruppiert werden.  
  
```  
virtual string do_grouping() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine gebietsschemaspezifische Regel zur Bestimmung, wie Ziffern auf der linken Seite des Dezimaltrennzeichens gruppiert werden.  
  
### <a name="remarks"></a>Hinweise  
 Die geschützte virtuelle Memberfunktion gibt eine gebietsschemaspezifische Regel zur Bestimmung zurück, wie Ziffern auf der linken Seite eines Dezimaltrennzeichens gruppiert werden. Die Codierung ist dieselbe wie für **lconv::grouping**.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Gruppieren](#numpunct__grouping), bei dem die virtuelle Memberfunktion aufgerufen wird **Gruppieren**.  
  
##  <a name="a-namenumpunctdothousandssepa-numpunctdothousandssep"></a><a name="numpunct__do_thousands_sep"></a>  numpunct:: do_thousands_sep  
 Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um ein gebietsschemaspezifisches Element zurückzugeben, das als Tausendertrennzeichen verwendet werden soll.  
  
```  
virtual CharType do_thousands_sep() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein gebietsschemaspezifisches Element zurück, das als Tausendertrennzeichen verwendet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die geschützte virtuelle Memberfunktion gibt eine gebietsschemaspezifische Element vom Typ **CharType** als Gruppentrennzeichen links vom Dezimaltrennzeichen verwenden.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Thousands_sep](#numpunct__thousands_sep), bei dem die virtuelle Memberfunktion, indem aufgerufen wird `thousands_sep`.  
  
##  <a name="a-namenumpunctdotruenamea-numpunctdotruename"></a><a name="numpunct__do_truename"></a>  numpunct:: do_truename  
 Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine Zeichenfolge, die als eine Textdarstellung des Werts verwendet **true**.  
  
```  
virtual string_type do_truename() const;
```  
  
### <a name="remarks"></a>Hinweise  
 Eine Zeichenfolge, die als eine Textdarstellung des Werts verwendet **true**.  
  
 Alle Gebietsschemas eine Zeichenfolge "True", um die Darstellung des Werts zurückgeben **true**.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Truename](#numpunct__truename), bei dem die virtuelle Memberfunktion, indem aufgerufen wird `truename`.  
  
##  <a name="a-namenumpunctfalsenamea-numpunctfalsename"></a><a name="numpunct__falsename"></a>  numpunct:: falsename  
 Gibt eine Zeichenfolge, die als eine Textdarstellung des Werts verwendet **false**.  
  
```  
string_type falsename() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die eine Sequenz von **CharType**e zur Verwendung als eine Textdarstellung des Werts **false**.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt die Zeichenfolge "False", um die Darstellung des Werts **false** in allen Gebietsschemas.  
  
 Die Memberfunktion gibt [Do_falsename](#numpunct__do_falsename).  
  
### <a name="example"></a>Beispiel  
  
```  
// numpunct_falsename.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "English" );  
  
   const numpunct <char> &npunct = use_facet <numpunct <char> >( loc );  
   cout << loc.name( ) << " truename "<< npunct.truename( ) << endl;  
   cout << loc.name( ) << " falsename "<< npunct.falsename( ) << endl;  
  
   locale loc2( "French" );  
   const numpunct <char> &npunct2 = use_facet <numpunct <char> >(loc2);  
   cout << loc2.name( ) << " truename "<< npunct2.truename( ) << endl;  
   cout << loc2.name( ) << " falsename "<< npunct2.falsename( ) << endl;  
}  
```  
  
```Output  
English_United States.1252 truename true  
English_United States.1252 falsename false  
French_France.1252 truename true  
French_France.1252 falsename false  
```  
  
##  <a name="a-namenumpunctgroupinga-numpunctgrouping"></a><a name="numpunct__grouping"></a>  numpunct:: GROUPING  
 Gibt eine gebietsschemaspezifische Regel zur Bestimmung zurück, wie Ziffern auf der linken Seite eines Dezimaltrennzeichens gruppiert werden sollen.  
  
```  
string grouping() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine gebietsschemaspezifische Regel zur Bestimmung, wie Ziffern auf der linken Seite des Dezimaltrennzeichens gruppiert werden.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [Do_grouping](#numpunct__do_grouping).  
  
### <a name="example"></a>Beispiel  
  
```  
// numpunct_grouping.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany");  
  
   const numpunct <char> &npunct =   
       use_facet < numpunct <char> >( loc );  
   for (unsigned int i = 0; i < npunct.grouping( ).length( ); i++)  
   {  
      cout << loc.name( ) << " international grouping:\n the "  
           << i <<"th group to the left of the radix character "  
           << "is of size " << (int)(npunct.grouping ( )[i])   
           << endl;  
   }  
}  
```  
  
```Output  
German_Germany.1252 international grouping:  
 the 0th group to the left of the radix character is of size 3  
```  
  
##  <a name="a-namenumpunctnumpuncta-numpunctnumpunct"></a><a name="numpunct__numpunct"></a>  numpunct:: numpunct  
 Der Konstruktor für Objekte des Typs `numpunct`.  
  
```  
explicit numpunct(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `_Refs`  
 Integer-Wert verwendet, um den Typ der Verwaltung des Arbeitsspeichers für das Objekt angeben.  
  
### <a name="remarks"></a>Hinweise  
 Die möglichen Werte für die `_Refs` Parameter und ihre Bedeutung sind:  
  
-   0: die Lebensdauer des Objekts wird von der Gebietsschemas, die es enthalten verwaltet.  
  
-   1: die Lebensdauer des Objekts manuell verwaltet werden muss.  
  
-   \> 0: Diese Werte sind nicht definiert.  
  
 Keine direkte Beispiele sind möglich, da der Destruktor geschützt ist.  
  
 Der Konstruktor initialisiert die Basisobjekt mit **Gebietsschema::**[Facet](../standard-library/locale-class.md#facet_class)( `_Refs`).  
  
##  <a name="a-namenumpunctstringtypea-numpunctstringtype"></a><a name="numpunct__string_type"></a>  numpunct:: string_type  
 Ein Typ, der eine Zeichenfolge mit Zeichen vom Typ beschreibt **CharType**.  
  
```  
typedef basic_string<CharType, Traits, Allocator> string_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [Basic_string](../standard-library/basic-string-class.md) deren Objekte können Kopien der Interpunktion Sequenzen speichern.  
  
##  <a name="a-namenumpunctthousandssepa-numpunctthousandssep"></a><a name="numpunct__thousands_sep"></a>  numpunct:: thousands_sep  
 Gibt ein gebietsschemaspezifisches Element zurück, das als Tausendertrennzeichen verwendet werden soll.  
  
```  
CharType thousands_sep() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Gebietsschema-Element, das als Tausendertrennzeichen verwendet Trennzeichen.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [Do_thousands_sep](#numpunct__do_thousands_sep).  
  
### <a name="example"></a>Beispiel  
  
```  
// numpunct_thou_sep.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const numpunct <char> &npunct =   
   use_facet < numpunct < char > >( loc );  
   cout << loc.name( ) << " decimal point "<<   
   npunct.decimal_point( ) << endl;  
   cout << loc.name( ) << " thousands separator "   
   << npunct.thousands_sep( ) << endl;  
};  
```  
  
```Output  
German_Germany.1252 decimal point ,  
German_Germany.1252 thousands separator .  
```  
  
##  <a name="a-namenumpuncttruenamea-numpuncttruename"></a><a name="numpunct__truename"></a>  numpunct:: TrueName  
 Gibt eine Zeichenfolge, die als eine Textdarstellung des Werts verwendet **true**.  
  
```  
string_type falsename() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die als eine Textdarstellung des Werts verwendet **true**.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [Do_truename](#numpunct__do_truename).  
  
 Alle Gebietsschemas eine Zeichenfolge "True", um die Darstellung des Werts zurückgeben **true**.  
  
### <a name="example"></a>Beispiel  
  
```  
// numpunct_truename.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "English" );  
  
   const numpunct < char> &npunct = use_facet <numpunct <char> >( loc );  
   cout << loc.name( ) << " truename "<< npunct.truename( ) << endl;  
   cout << loc.name( ) << " falsename "<< npunct.falsename( ) << endl;  
  
   locale loc2("French");  
   const numpunct <char> &npunct2 = use_facet <numpunct <char> >( loc2 );  
   cout << loc2.name( ) << " truename "<< npunct2.truename( ) << endl;  
   cout << loc2.name( ) << " falsename "<< npunct2.falsename( ) << endl;  
}  
```  
  
```Output  
English_United States.1252 truename true  
English_United States.1252 falsename false  
French_France.1252 truename true  
French_France.1252 falsename false  
```  
  
## <a name="see-also"></a>Siehe auch  
 [\< Gebietsschema>](../standard-library/locale.md)   
 [Facet-Klasse](../standard-library/locale-class.md#facet_class)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)

