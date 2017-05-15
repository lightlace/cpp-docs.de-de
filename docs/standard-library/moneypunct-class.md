---
title: moneypunct-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- moneypunct
- xlocmon/std::moneypunct
- locale/std::moneypunct::char_type
- locale/std::moneypunct::string_type
- locale/std::moneypunct::curr_symbol
- locale/std::moneypunct::decimal_point
- locale/std::moneypunct::do_curr_symbol
- locale/std::moneypunct::do_decimal_point
- locale/std::moneypunct::do_frac_digits
- locale/std::moneypunct::do_grouping
- locale/std::moneypunct::do_neg_format
- locale/std::moneypunct::do_negative_sign
- locale/std::moneypunct::do_pos_format
- locale/std::moneypunct::do_positive_sign
- locale/std::moneypunct::do_thousands_sep
- locale/std::moneypunct::frac_digits
- locale/std::moneypunct::grouping
- locale/std::moneypunct::neg_format
- locale/std::moneypunct::negative_sign
- locale/std::moneypunct::pos_format
- locale/std::moneypunct::positive_sign
- locale/std::moneypunct::thousands_sep
dev_langs:
- C++
helpviewer_keywords:
- moneypunct class
ms.assetid: cf2650da-3e6f-491c-95d5-23e57f582ee6
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 9567db1b823f373a5ea26e6d113cc9176901453d
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="moneypunct-class"></a>moneypunct-Klasse
Die Vorlagenklasse beschreibt ein Objekt, das als Gebietsschemafacet dienen kann, um die Sequenzen vom Typ `CharType` zu beschreiben, die verwendet werden, um ein monetäres Eingabefeld oder ein monetäres Ausgabefeld darzustellen. Wenn der Vorlagenparameter `Intl` `true` ist, werden internationale Konventionen beachtet.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class CharType, bool Intl>  
class moneypunct;  
```  
  
#### <a name="parameters"></a>Parameter  
 `CharType`  
 Der Typ, der innerhalb eines Programms verwendet wird, um Zeichen zu codieren.  
  
 `Intl`  
 Ein Flag, das festlegt, ob internationale Konventionen beachtet werden sollen.  
  
## <a name="remarks"></a>Hinweise  
 Wie bei jedem Gebietsschemafacet hat die statische Objekt-ID einen anfänglichen gespeicherten Wert von NULL. Beim ersten Versuch, auf den gespeicherten Wert zuzugreifen, wird in **id** ein eindeutiger positiver Wert gespeichert.  
  
 Das konstante statische Objekt „intl“ speichert den Wert des Vorlagenparameters **Intl**.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[moneypunct](#moneypunct)|Konstruktor von Objekten des Typs `moneypunct`.|  
  
### <a name="typedefs"></a>TypeDefs  
  
|||  
|-|-|  
|[char_type](#char_type)|Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.|  
|[string_type](#string_type)|Ein Typ, der eine Zeichenfolge beschreibt, die Zeichen vom Typ `CharType` enthält.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[curr_symbol](#curr_symbol)|Gibt eine gebietsschemaspezifische Sequenz von Elementen zurück, die als Währungssymbol verwendet werden soll.|  
|[decimal_point](#decimal_point)|Gibt eine gebietsschemaspezifische Sequenz von Elementen zurück, die als Dezimalzeichen verwendet werden soll.|  
|[do_curr_symbol](#do_curr_symbol)|Eine geschützte virtuelle Memberfunktion, die eine gebietsschemaspezifische Sequenz von Elementen zurückgibt, die als Währungssymbol verwendet werden soll.|  
|[do_decimal_point](#do_decimal_point)|Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine gebietsschemaspezifische Sequenz von Elementen zurückzugeben, die als Dezimaltrennzeichen verwendet werden soll.|  
|[do_frac_digits](#do_frac_digits)|Die geschützte virtuelle Memberfunktion gibt eine gebietsschemaspezifische Anzahl von Ziffern zurück, die rechts vom Dezimaltrennzeichen angezeigt werden sollen.|  
|[do_grouping](#do_grouping)|Die geschützte virtuelle Memberfunktion gibt eine gebietsschemaspezifische Regel zur Bestimmung zurück, wie Ziffern auf der linken Seite eines Dezimaltrennzeichens gruppiert werden.|  
|[do_neg_format](#do_neg_format)|Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine gebietsschemaspezifische Regel zur Formatierung von Ausgaben mit negativen Zahlen zurückzugeben.|  
|[do_negative_sign](#do_negative_sign)|Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine gebietsschemaspezifische Sequenz von Elementen zurückzugeben, die als Minuszeichen verwendet werden soll.|  
|[do_pos_format](#do_pos_format)|Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine gebietsschemaspezifische Regel zur Formatierung von Ausgaben mit positiven Zahlen zurückzugeben.|  
|[do_positive_sign](#do_positive_sign)|Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine gebietsschemaspezifische Sequenz von Elementen zurückzugeben, die als Pluszeichen verwendet werden soll.|  
|[do_thousands_sep](#do_thousands_sep)|Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine gebietsschemaspezifische Sequenz von Elementen zurückzugeben, die als Tausendertrennzeichen verwendet werden soll.|  
|[frac_digits](#frac_digits)|Gibt eine gebietsschemaspezifische Anzahl von Ziffern zurück, die auf der rechten Seite eines Dezimaltrennzeichens angezeigt werden sollen.|  
|[grouping](#grouping)|Gibt eine gebietsschemaspezifische Regel zur Bestimmung zurück, wie Ziffern auf der linken Seite eines Dezimaltrennzeichens gruppiert werden sollen.|  
|[neg_format](#neg_format)|Gibt eine gebietsschemaspezifische Regel zur Formatierung von Ausgaben mit negativen Zahlen zurück.|  
|[negative_sign](#negative_sign)|Gibt eine gebietsschemaspezifische Sequenz von Elementen zurück, die als Minuszeichen verwendet werden soll.|  
|[pos_format](#pos_format)|Gibt eine gebietsschemaspezifische Regel zur Formatierung von Ausgaben mit positiven Zahlen zurück.|  
|[positive_sign](#positive_sign)|Gibt eine gebietsschemaspezifische Sequenz von Elementen zurück, die als Pluszeichen verwendet werden soll.|  
|[thousands_sep](#thousands_sep)|Gibt eine gebietsschemaspezifische Sequenz von Elementen zurück, die als Tausendertrennzeichen verwendet werden soll.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<locale>  
  
 **Namespace:** std  
  
##  <a name="char_type"></a> moneypunct::char_type  
 Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter **CharType**.  
  
##  <a name="curr_symbol"></a> moneypunct::curr_symbol  
 Gibt eine gebietsschemaspezifische Sequenz von Elementen zurück, die als Währungssymbol verwendet werden soll.  
  
```  
string_type curr_symbol() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Zeichenfolge, die das Währungssymbol enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [do_curr_symbol](#do_curr_symbol) zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// moneypunct_curr_symbol.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const moneypunct < char, true > &mpunct = use_facet < moneypunct < char, true > >(loc);  
   cout << loc.name( ) << " international currency symbol "<<  mpunct.curr_symbol( ) << endl;  
  
   const moneypunct < char, false> &mpunct2 = use_facet < moneypunct < char, false> >(loc);  
   cout << loc.name( ) << " domestic currency symbol "<<  mpunct2.curr_symbol( ) << endl;  
};  
```  
  
##  <a name="decimal_point"></a> moneypunct::decimal_point  
 Gibt eine gebietsschemaspezifische Sequenz von Elementen zurück, die als Dezimalzeichen verwendet werden soll.  
  
```  
CharType decimal_point() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine gebietsschemaspezifische Sequenz von Elementen, die als Dezimaltrennzeichen verwendet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [do_decimal_point](#do_decimal_point) zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// moneypunct_decimal_pt.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc("german_germany");  
  
   const moneypunct < char, true > &mpunct = use_facet   
      < moneypunct < char, true > >(loc);  
   cout << loc.name( ) << " international decimal point "  
        << mpunct.decimal_point( ) << endl;  
  
   const moneypunct < char, false> &mpunct2 = use_facet   
      < moneypunct < char, false> >(loc);  
   cout << loc.name( ) << " domestic decimal point "  
        << mpunct2.decimal_point( ) << endl;  
}  
```  
  
```Output  
German_Germany.1252 international decimal point ,  
German_Germany.1252 domestic decimal point ,  
```  
  
##  <a name="do_curr_symbol"></a> moneypunct::do_curr_symbol  
 Eine geschützte virtuelle Memberfunktion, die eine gebietsschemaspezifische Sequenz von Elementen zurückgibt, die als Währungssymbol verwendet werden soll.  
  
```  
virtual string_type do_curr_symbol() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine gebietsschemaspezifische Sequenz von Elementen, die als Dezimaltrennzeichen verwendet werden soll.  
  
### <a name="example"></a>Beispiel  
  Informationen hierzu finden Sie im Beispiel für [curr_symbol](#curr_symbol), bei dem die virtuelle Memberfunktion durch `curr_symbol` aufgerufen wird.  
  
##  <a name="do_decimal_point"></a> moneypunct::do_decimal_point  
 Eine geschützte virtuelle Memberfunktion, die eine gebietsschemaspezifische Sequenz von Elementen zurückgibt, die als Dezimaltrennzeichen verwendet werden soll.  
  
```  
virtual CharType do_decimal_point() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine gebietsschemaspezifische Sequenz von Elementen, die als Dezimaltrennzeichen verwendet werden soll.  
  
### <a name="example"></a>Beispiel  
  Informationen hierzu finden Sie im Beispiel für [decimal_point](#decimal_point), bei dem die virtuelle Memberfunktion durch `decimal_point` aufgerufen wird.  
  
##  <a name="do_frac_digits"></a> moneypunct::do_frac_digits  
 Eine geschützte virtuelle Memberfunktion, die eine gebietsschemaspezifische Anzahl von Ziffern zurückgibt, die auf der rechten Seiten des Dezimaltrennzeichens angezeigt werden sollen.  
  
```  
virtual int do_frac_digits() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine gebietsschemaspezifische Anzahl von Ziffern zurück, die auf der rechten Seiten des Dezimaltrennzeichens angezeigt werden sollen.  
  
### <a name="example"></a>Beispiel  
  Informationen hierzu finden Sie im Beispiel für [frac_digits](#frac_digits), bei dem die virtuelle Memberfunktion durch `frac_digits` aufgerufen wird.  
  
##  <a name="do_grouping"></a> moneypunct::do_grouping  
 Eine geschützte virtuelle Memberfunktion, die eine gebietsschemaspezifische Regel zurückgibt, mit der festgelegt wird, wie Ziffern auf der linken Seite eines Dezimaltrennzeichens gruppiert werden.  
  
```  
virtual string do_grouping() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine gebietsschemaspezifische Regel, die festlegt, wie Ziffern auf der linken Seite eines Dezimaltrennzeichens gruppiert werden.  
  
### <a name="example"></a>Beispiel  
  Informationen hierzu finden Sie im Beispiel für [grouping](#grouping), bei dem die virtuelle Memberfunktion durch **grouping** aufgerufen wird.  
  
##  <a name="do_neg_format"></a> moneypunct::do_neg_format  
 Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine gebietsschemaspezifische Regel zur Formatierung von Ausgaben mit negativen Zahlen zurückzugeben.  
  
```  
virtual pattern do_neg_format() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die geschützte virtuelle Memberfunktion gibt eine gebietsschemaspezifische Regel zurück, mit der festgelegt wird, wie für einen negativen Betrag Ausgabefelder für monetäre Werte generiert werden. Alle vier Elemente von **pattern::field** können die folgenden Werte aufweisen:  
  
- **none**, um auf null oder mehr Leerzeichen abzustimmen bzw. nichts zu generieren.  
  
- **sign**, um auf ein positives bzw. negatives Vorzeichen abzustimmen oder um ein positives bzw. negatives Vorzeichen zu generieren.  
  
- **space**, um auf null oder mehr Leerzeichen abzustimmen bzw. um ein Leerzeichen zu generieren.  
  
- **symbol**, um auf ein Währungssymbol abzustimmen bzw. um ein Währungssymbol zu generieren.  
  
- **value**, um auf einen monetären Wert abzustimmen bzw. um einen monetären Wert zu generieren.  
  
 Die Komponenten eines Ausgabefelds für monetäre Werte werden generiert, und die Komponenten eines Eingabefelds für monetäre Werte werden in der Reihenfolge zugeordnet, in der diese Elemente in **pattern::field** angezeigt werden. Die einzelnen Werte **sign**, **symbol**, **value** und **none** bzw. **space** müssen jeweils einmal angezeigt werden. Der Wert **none** darf nicht an erster Stelle angezeigt werden. Der Wert **space** darf weder an erster noch an letzter Stelle angezeigt werden. Wenn **Intl** TRUE ist, lautet die Reihenfolge: **symbol**, **sign**, **none**, **value**.  
  
 Die Vorlagenversion von `moneypunct`\< **CharType**, **Intl**> returns `{`**money_base::symbol**, **money_base::sign**, **money_base::value**, **money_base::none**`}`.  
  
### <a name="example"></a>Beispiel  
  Informationen hierzu finden Sie im Beispiel für [neg_format](#neg_format), bei dem die virtuelle Memberfunktion durch `neg_format` aufgerufen wird.  
  
##  <a name="do_negative_sign"></a> moneypunct::do_negative_sign  
 Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine gebietsschemaspezifische Sequenz von Elementen zurückzugeben, die als Minuszeichen verwendet werden soll.  
  
```  
virtual string_type do_negative_sign() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine gebietsschemaspezifische Sequenz von Elementen, die als negatives Vorzeichen verwendet werden soll.  
  
### <a name="example"></a>Beispiel  
  Informationen hierzu finden Sie im Beispiel für [negative_sign](#negative_sign), bei dem die virtuelle Memberfunktion durch `negative_sign` aufgerufen wird.  
  
##  <a name="do_pos_format"></a> moneypunct::do_pos_format  
 Eine geschützte virtuelle Memberfunktion, die aufgerufen wird, um eine gebietsschemaspezifische Regel zur Formatierung von Ausgaben mit positiven Zahlen zurückzugeben.  
  
```  
virtual pattern do_pos_format() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die geschützte virtuelle Memberfunktion gibt eine gebietsschemaspezifische Regel zurück, die festlegt, wie für einen positiven Betrag Ausgabefelder für monetäre Werte generiert werden. (Die Regel legt zudem fest, wie die Komponenten eines Eingabefelds für monetäre Werte zugeordnet werden.) Die Codierung ist dieselbe wie für [do_neg_format](#do_neg_format).  
  
 Die Vorlagenversion von moneypunct\< **CharType**, **Inputlterator**> returns `{`**money_base::symbol**, **money_base::sign**, **money_base::value**, **money_base::none**`}`.  
  
### <a name="example"></a>Beispiel  
  Informationen hierzu finden Sie im Beispiel für [pos_format](#pos_format), bei dem die virtuelle Memberfunktion durch `pos_format` aufgerufen wird.  
  
##  <a name="do_positive_sign"></a> moneypunct::do_positive_sign  
 Eine geschützte virtuelle Memberfunktion, die eine gebietsschemaspezifische Sequenz von Elementen zurückgibt, die als positives Vorzeichen verwendet werden soll.  
  
```  
virtual string_type do_positive_sign() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine gebietsschemaspezifische Sequenz von Elementen, die als positives Vorzeichen verwendet werden soll.  
  
### <a name="example"></a>Beispiel  
  Informationen hierzu finden Sie im Beispiel für [positive_sign](#positive_sign), bei dem die virtuelle Memberfunktion durch `positive_sign` aufgerufen wird.  
  
##  <a name="do_thousands_sep"></a> moneypunct::do_thousands_sep  
 Eine geschützte virtuelle Memberfunktion, die ein gebietsschemaspezifisches Element zurückgibt, das auf der linken Seite eines Dezimalzeichens als Gruppentrennzeichen verwendet werden soll.  
  
```  
virtual CharType do_thousands_sep() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein gebietsschemaspezifisches Element, das auf der linken Seite eines Dezimalzeichens als Gruppentrennzeichen verwendet werden soll.  
  
### <a name="example"></a>Beispiel  
  Informationen hierzu finden Sie im Beispiel für [thousands_sep](#thousands_sep), bei dem die virtuelle Memberfunktion durch `thousands_sep` aufgerufen wird.  
  
##  <a name="frac_digits"></a> moneypunct::frac_digits  
 Gibt eine gebietsschemaspezifische Anzahl von Ziffern zurück, die auf der rechten Seite eines Dezimaltrennzeichens angezeigt werden sollen.  
  
```  
int frac_digits() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine gebietsschemaspezifische Anzahl von Ziffern zurück, die auf der rechten Seiten des Dezimaltrennzeichens angezeigt werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [do_frac_digits](#do_frac_digits) zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// moneypunct_frac_digits.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const moneypunct <char, true> &mpunct =   
       use_facet <moneypunct <char, true> >(loc);  
   for (unsigned int i = 0; i <mpunct.grouping( ).length( ); i++ )  
   {  
      cout << loc.name( ) << " international grouping:\n the "  
           << i <<"th group to the left of the radix character "  
           << "is of size " << (int)(mpunct.grouping ( )[i])   
           << endl;  
   }  
   cout << loc.name( ) << " international frac_digits\n to the right"  
        << " of the radix character: "  
        << mpunct.frac_digits ( ) << endl << endl;  
  
   const moneypunct <char, false> &mpunct2 =   
       use_facet <moneypunct <char, false> >(loc);  
   for (unsigned int i = 0; i <mpunct2.grouping( ).length( ); i++ )  
   {  
      cout << loc.name( ) << " domestic grouping:\n the "  
           << i <<"th group to the left of the radix character "  
           << "is of size " << (int)(mpunct2.grouping ( )[i])   
           << endl;  
   }  
   cout << loc.name( ) << " domestic frac_digits\n to the right"  
        << " of the radix character: "  
        << mpunct2.frac_digits ( ) << endl << endl;  
}  
```  
  
```Output  
German_Germany.1252 international grouping:  
 the 0th group to the left of the radix character is of size 3  
German_Germany.1252 international frac_digits  
 to the right of the radix character: 2  
  
German_Germany.1252 domestic grouping:  
 the 0th group to the left of the radix character is of size 3  
German_Germany.1252 domestic frac_digits  
 to the right of the radix character: 2  
```  
  
##  <a name="grouping"></a> moneypunct::grouping  
 Gibt eine gebietsschemaspezifische Regel zur Bestimmung zurück, wie Ziffern auf der linken Seite eines Dezimaltrennzeichens gruppiert werden sollen.  
  
```  
string grouping() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine gebietsschemaspezifische Regel, die festlegt, wie Ziffern auf der linken Seite eines Dezimaltrennzeichens gruppiert werden.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [do_grouping](#do_grouping) zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// moneypunct_grouping.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const moneypunct <char, true> &mpunct =   
       use_facet <moneypunct <char, true> >( loc );  
   for (unsigned int i = 0; i <mpunct.grouping( ).length( ); i++ )  
   {  
      cout << loc.name( ) << " international grouping:\n the "  
           << i <<"th group to the left of the radix character "  
           << "is of size " << (int)(mpunct.grouping ( )[i])   
           << endl;  
   }  
   cout << loc.name( ) << " international frac_digits\n to the right"  
        << " of the radix character: "  
        << mpunct.frac_digits ( ) << endl << endl;  
  
   const moneypunct <char, false> &mpunct2 =   
       use_facet <moneypunct <char, false> >( loc );  
   for (unsigned int i = 0; i <mpunct2.grouping( ).length( ); i++ )  
   {  
      cout << loc.name( ) << " domestic grouping:\n the "  
           << i <<"th group to the left of the radix character "  
           << "is of size " << (int)(mpunct2.grouping ( )[i])   
           << endl;  
   }  
   cout << loc.name( ) << " domestic frac_digits\n to the right"  
        << " of the radix character: "  
        << mpunct2.frac_digits ( ) << endl << endl;  
}  
```  
  
```Output  
German_Germany.1252 international grouping:  
 the 0th group to the left of the radix character is of size 3  
German_Germany.1252 international frac_digits  
 to the right of the radix character: 2  
  
German_Germany.1252 domestic grouping:  
 the 0th group to the left of the radix character is of size 3  
German_Germany.1252 domestic frac_digits  
 to the right of the radix character: 2  
```  
  
##  <a name="moneypunct"></a> moneypunct::moneypunct  
 Konstruktor von Objekten des Typs `moneypunct`.  
  
```  
explicit moneypunct(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `_Refs`  
 Integerwert, der zum Angeben des Speicherverwaltungstyps für das Objekt verwendet wird.  
  
### <a name="remarks"></a>Hinweise  
 Mögliche Werte für den `_Refs`-Parameter und ihre Bedeutung:  
  
-   0: Die Lebensdauer des Objekts wird von den Gebietsschemas verwaltet, in denen es enthalten ist.  
  
-   1: Die Lebensdauer des Objekts muss manuell verwaltet werden.  
  
-   \>1: Diese Werte sind nicht definiert.  
  
 Direkte Beispiele sind nicht möglich, da der Destruktor geschützt ist.  
  
 Der Konstruktor initialisiert sein Basisobjekt mit [locale::facet](../standard-library/locale-class.md#facet_class)(_ *Refs*).  
  
##  <a name="neg_format"></a> moneypunct::neg_format  
 Gibt eine gebietsschemaspezifische Regel zur Formatierung von Ausgaben mit negativen Zahlen zurück.  
  
```  
pattern neg_format() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine gebietsschemaspezifische Regel zur Formatierung von Ausgaben mit negativen Beträgen.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [do_neg_format](#do_neg_format) zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// moneypunct_neg_format.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
  
using namespace std;  
  
int main( ) {  
   locale loc( "german_germany" );  
  
   const moneypunct <char, true> &mpunct =   
      use_facet <moneypunct <char, true > >(loc);  
   cout << loc.name( ) << " international negative number format: "  
        << mpunct.neg_format( ).field[0]   
        << mpunct.neg_format( ).field[1]   
        << mpunct.neg_format( ).field[2]   
        << mpunct.neg_format( ).field[3] << endl;  
  
   const moneypunct <char, false> &mpunct2 =   
      use_facet <moneypunct <char, false> >(loc);  
   cout << loc.name( ) << " domestic negative number format: "  
        << mpunct2.neg_format( ).field[0]   
        << mpunct2.neg_format( ).field[1]   
        << mpunct2.neg_format( ).field[2]   
        << mpunct2.neg_format( ).field[3] << endl;  
}  
```  
  
##  <a name="negative_sign"></a> moneypunct::negative_sign  
 Gibt eine gebietsschemaspezifische Sequenz von Elementen zurück, die als Minuszeichen verwendet werden soll.  
  
```  
string_type negative_sign() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine gebietsschemaspezifische Sequenz von Elementen zurück, die als Minuszeichen verwendet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [do_negative_sign](#do_negative_sign) zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// moneypunct_neg_sign.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
  
using namespace std;  
  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const moneypunct <char, true> &mpunct =   
      use_facet <moneypunct <char, true> >(loc);  
   cout << loc.name( ) << " international negative sign: "  
        << mpunct.negative_sign( ) << endl;  
  
   const moneypunct <char, false> &mpunct2 =   
      use_facet <moneypunct <char, false> >(loc);  
   cout << loc.name( ) << " domestic negative sign: "  
        << mpunct2.negative_sign( ) << endl;  
  
   locale loc2( "French" );  
  
   const moneypunct <char, true> &mpunct3 =   
      use_facet <moneypunct <char, true> >(loc2);  
   cout << loc2.name( ) << " international negative sign: "  
        << mpunct3.negative_sign( ) << endl;  
  
   const moneypunct <char, false> &mpunct4 =   
      use_facet <moneypunct <char, false> >(loc2);  
   cout << loc2.name( ) << " domestic negative sign: "  
        << mpunct4.negative_sign( ) << endl;  
};  
```  
  
```Output  
German_Germany.1252 international negative sign: -  
German_Germany.1252 domestic negative sign: -  
French_France.1252 international negative sign: -  
French_France.1252 domestic negative sign: -  
```  
  
##  <a name="pos_format"></a> moneypunct::pos_format  
 Gibt eine gebietsschemaspezifische Regel zur Formatierung von Ausgaben mit positiven Zahlen zurück.  
  
```  
pattern pos_format() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine gebietsschemaspezifische Regel zur Formatierung von Ausgaben mit positiven Beträgen.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [do_pos_format](#do_pos_format) zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// moneypunct_pos_format.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
  
using namespace std;  
  
int main() {  
   locale loc( "german_germany" );  
  
   const moneypunct <char, true> &mpunct =   
      use_facet <moneypunct <char, true> >(loc);  
   cout << loc.name( ) << " international positive number format: "  
        << mpunct.pos_format( ).field[0]   
        << mpunct.pos_format( ).field[1]   
        << mpunct.pos_format( ).field[2]   
        << mpunct.pos_format( ).field[3] << endl;  
  
   const moneypunct <char, false> &mpunct2 =   
      use_facet <moneypunct <char, false> >(loc);  
   cout << loc.name( ) << " domestic positive number format: "  
        << mpunct2.pos_format( ).field[0]   
        << mpunct2.pos_format( ).field[1]   
        << mpunct2.pos_format( ).field[2]   
        << mpunct2.pos_format( ).field[3] << endl;  
}  
```  
  
##  <a name="positive_sign"></a> moneypunct::positive_sign  
 Gibt eine gebietsschemaspezifische Sequenz von Elementen zurück, die als Pluszeichen verwendet werden soll.  
  
```  
string_type positive_sign() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine gebietsschemaspezifische Sequenz von Elementen, die als positive Vorzeichen verwendet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [do_positive_sign](#do_positive_sign) zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// moneypunct_pos_sign.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
  
using namespace std;  
  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const moneypunct <char, true> &mpunct =   
      use_facet <moneypunct <char, true > >(loc);  
   cout << loc.name( ) << " international positive sign:"  
        << mpunct.positive_sign( ) << endl;  
  
   const moneypunct <char, false> &mpunct2 =   
      use_facet <moneypunct <char, false> >(loc);  
   cout << loc.name( ) << " domestic positive sign:"  
        << mpunct2.positive_sign( ) << endl;  
  
   locale loc2( "French" );  
  
   const moneypunct <char, true> &mpunct3 =   
      use_facet <moneypunct <char, true> >(loc2);  
   cout << loc2.name( ) << " international positive sign:"  
        << mpunct3.positive_sign( ) << endl;  
  
   const moneypunct <char, false> &mpunct4 =   
      use_facet <moneypunct <char, false> >(loc2);  
   cout << loc2.name( ) << " domestic positive sign:"  
        << mpunct4.positive_sign( ) << endl;  
};  
```  
  
```Output  
German_Germany.1252 international positive sign:  
German_Germany.1252 domestic positive sign:  
French_France.1252 international positive sign:  
French_France.1252 domestic positive sign:  
```  
  
##  <a name="string_type"></a> moneypunct::string_type  
 Ein Typ, der eine Zeichenfolge beschreibt, die Zeichen des Typs **CharType** enthält.  
  
```  
typedef basic_string<CharType, Traits, Allocator> string_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [basic_string](../standard-library/basic-string-class.md), deren Objekte Kopien der Interpunktionssequenzen speichern können.  
  
##  <a name="thousands_sep"></a> moneypunct::thousands_sep  
 Gibt eine gebietsschemaspezifische Sequenz von Elementen zurück, die als Tausendertrennzeichen verwendet werden soll.  
  
```  
CharType thousands_sep() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine gebietsschemaspezifische Sequenz von Elementen, die als Tausendertrennzeichen verwendet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [do_thousands_sep](#do_thousands_sep) zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// moneypunct_thou_sep.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const moneypunct <char, true> &mpunct =   
       use_facet <moneypunct <char, true > >(loc);  
   cout << loc.name( ) << " international thousands separator: "  
        << mpunct.thousands_sep( ) << endl;  
  
   const moneypunct <char, false> &mpunct2 =   
      use_facet <moneypunct <char, false> >(loc);  
   cout << loc.name( ) << " domestic thousands separator: "  
        << mpunct2.thousands_sep( ) << endl << endl;  
  
   locale loc2( "english_canada" );  
  
   const moneypunct <char, true> &mpunct3 =   
       use_facet <moneypunct <char, true> >(loc2);  
   cout << loc2.name( ) << " international thousands separator: "  
        << mpunct3.thousands_sep( ) << endl;  
  
   const moneypunct <char, false> &mpunct4 =   
      use_facet <moneypunct <char, false> >(loc2);  
   cout << loc2.name( ) << " domestic thousands separator: "  
        << mpunct4.thousands_sep( ) << endl;  
}  
```  
  
```Output  
German_Germany.1252 international thousands separator: .  
German_Germany.1252 domestic thousands separator: .  
  
English_Canada.1252 international thousands separator: ,  
English_Canada.1252 domestic thousands separator: ,  
```  
  
## <a name="see-also"></a>Siehe auch  
 [\<locale>](../standard-library/locale.md)   
 [Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)


