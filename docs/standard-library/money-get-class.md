---
title: money_get-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xlocmon/std::money_get
- money_get
- locale/std::money_get::char_type
- locale/std::money_get::iter_type
- locale/std::money_get::string_type
- locale/std::money_get::do_get
- locale/std::money_get::get
dev_langs:
- C++
helpviewer_keywords:
- money_get class
ms.assetid: 692d3374-3fe7-4b46-8aeb-f8d91ed66b2e
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 824f12ed51bfd5f29e759a50fb3ead0a669da0ab
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="moneyget-class"></a>money_get-Klasse
Die Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet dienen kann, um Konvertierungen von Sequenzen des Typs `CharType` in monetäre Werte zu steuern.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>  
class money_get : public locale::facet;
```  
  
#### <a name="parameters"></a>Parameter  
 `CharType`  
 Der Typ, der innerhalb eines Programms zum Codieren von Zeichen in einem Gebietsschema verwendet wird.  
  
 `InputIterator`  
 Der Typ des Iterators, von dem die get-Funktionen ihre Eingabe lesen.  
  
## <a name="remarks"></a>Hinweise  
 Wie bei jedem Gebietsschemafacet hat die statische Objekt-ID einen anfänglichen gespeicherten Wert von NULL. Beim ersten Versuch, auf den gespeicherten Wert zuzugreifen, wird in **id** ein eindeutiger positiver Wert gespeichert.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[money_get](#money_get)|Der Konstruktor für Objekte vom Typ `money_get`, die verwendet werden, um numerische Werte aus Sequenzen zu extrahieren, die monetäre Werte darstellen.|  
  
### <a name="typedefs"></a>TypeDefs  
  
|||  
|-|-|  
|[char_type](#char_type)|Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.|  
|[iter_type](#iter_type)|Ein Typ, der einen Eingabeiterator beschreibt.|  
|[string_type](#string_type)|Ein Typ, der eine Zeichenfolge beschreibt, die Zeichen vom Typ `CharType` enthält.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[do_get](#do_get)|Eine virtuelle Funktion, die aufgerufen wird, um einen Zahlenwert aus einer Zeichenfolge zu extrahieren, die einen monetären Wert darstellt.|  
|[get](#get)|Extrahiert einen numerischen Wert aus einer Zeichenfolge, die einen monetären Wert darstellt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<locale>  
  
 **Namespace:** std  
  
##  <a name="char_type"></a> money_get::char_type  
 Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter **CharType**.  
  
##  <a name="do_get"></a> money_get::do_get  
 Eine virtuelle Funktion, die aufgerufen wird, um einen Zahlenwert aus einer Zeichenfolge zu extrahieren, die einen monetären Wert darstellt.  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    long double& val) const virtual iter_type do_get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    string_type& val) const
```  
  
### <a name="parameters"></a>Parameter  
 `first`  
 Der Eingabeiterator, der den Anfang der zu konvertierenden Sequenz adressiert.  
  
 `last`  
 Der Eingabeiterator, der das Ende der zu konvertierenden Sequenz adressiert.  
  
 `Intl`  
 Ein boolescher Wert, der den Typ des in der Sequenz vorgesehenen Währungssymbols angibt (**TRUE**, wenn international; **FALSE**, wenn national).  
  
 `Iosbase`  
 Ein Formatkennzeichen, das bei Verwendung angibt, dass das Währungssymbol optional ist. Ansonsten ist das Währungssymbol erforderlich.  
  
 `State`  
 Je nachdem, ob die Vorgänge erfolgreich waren, legt dieses Element die entsprechenden Bitmaskenelemente für den Streamstatus fest.  
  
 `val`  
 Eine Zeichenfolge zum Speichern der konvertierten Sequenz.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Eingabeiterator,der das erste Element nach dem Eingabefeld für den monetären Wert adressiert.  
  
### <a name="remarks"></a>Hinweise  
 Die erste virtuelle geschützte Memberfunktion versucht, sequenzielle Elemente zuzuordnen. Sie beginnt zuerst in der Sequenz [ `first`, `last`), bis sie ein vollständiges, nicht leeres Eingabefeld für monetäre Werte erkannt hat. Ist dies erfolgreich, konvertiert sie dieses Feld zur Darstellung der Menge in eine Sequenz aus einer oder mehreren Dezimalstellen (optional mit vorangestelltem `-`) und speichert das Ergebnis im [string_type](#string_type)-Objekt `val`. Sie gibt einen Iterator zurück, der das erste Element nach dem Eingabefeld für monetäre Werte festlegt. Andernfalls speichert die Funktion eine leere Sequenz in `val` und legt `State` für `ios_base::failbit` fest. Sie gibt einen Iterator zurück, der das erste Element nach jedem Präfix eines gültigen Eingabefelds für monetäre Werte festlegt. In beiden Fällen legt die Funktion `State` für `ios_base::eofbit` fest, wenn der Rückgabewert `last` entspricht.  
  
 Die zweite geschützte virtuelle Memberfunktion verhält sich wie die erste. Gelingt dies, konvertiert sie die Zahlenfolge mit optionalem Vorzeichen allerdings in einen Wert des Typs `long double` und speichert diesen Wert in `val`.  
  
 Das Format eines Eingabefelds für monetäre Werte richtet sich nach dem [Gebietsschemafacet](../standard-library/locale-class.md#facet_class) **fac**, das durch den effektiven Aufruf [use_facet](../standard-library/locale-functions.md#use_facet) < [moneypunct](../standard-library/moneypunct-class.md)\< **CharType**, **intl**>>( **iosbase**. [getloc](../standard-library/ios-base-class.md#getloc)) zurückgegeben wird.  
  
 Dies gilt insbesondere in folgenden Fällen:  
  
- **fac**. [neg_format](../standard-library/moneypunct-class.md#neg_format) bestimmt die Reihenfolge, in der Komponenten des Felds auftreten.  
  
- **fac**. [curr_symbol](../standard-library/moneypunct-class.md#curr_symbol) bestimmt die Sequenz der Elemente, aus der ein Währungssymbol besteht.  
  
- **fac**. [positive_sign](../standard-library/moneypunct-class.md#positive_sign) bestimmt die Sequenz der Elemente, aus der ein positiven Vorzeichen besteht.  
  
- **fac**. [negative_sign](../standard-library/moneypunct-class.md#negative_sign) bestimmt die Sequenz der Elemente, aus der ein negativen Vorzeichen besteht.  
  
- **fac**. [grouping](../standard-library/moneypunct-class.md#grouping) bestimmt, wie Ziffern auf der linken Seite des Dezimaltrennzeichens gruppiert werden.  
  
- **fac**. [thousands_sep](../standard-library/moneypunct-class.md#thousands_sep) bestimmt das Element, das Gruppen von Ziffern auf der linken Seite eines Dezimaltrennzeichens trennt.  
  
- **fac**. [decimal_point](../standard-library/moneypunct-class.md#decimal_point) bestimmt das Element, das ganzzahlige Ziffern von Bruchziffern trennt.  
  
- **fac**. [frac_digits](../standard-library/moneypunct-class.md#frac_digits) bestimmt die Anzahl signifikanter Ziffern auf der rechten Seite eines Dezimaltrennzeichens. Wird ein Geldbetrag mit mehr Bruchziffern analysiert, als durch `frac_digits` aufgerufen werden, beendet `do_get` die Analyse, wenn höchstens `frac_digits`-Zeichen verbraucht wurden.  
  
 Wenn die Zeichenfolge ( **fac**. `negative_sign` oder **fac**. `positive_sign`) über mehr als ein Element verfügt, wird nur das erste Element zugeordnet, bei dem das dem **money_base::sign** entsprechende Element im Formatmuster ( **fac**. `neg_format`) angezeigt wird. Alle übrigen Elemente werden am Ende des Eingabefelds für monetäre Werte zugeordnet. Wenn keine Zeichenfolge über ein erstes Element verfügt, das dem nächsten Element im Eingabefeld für monetäre Werte entspricht, wird die Zeichenfolge als leer angenommen. Das Vorzeichen ist in diesem Fall positiv.  
  
 Wenn **iosbase**. [flags](../standard-library/ios-base-class.md#flags) & [showbase](../standard-library/ios-functions.md#showbase) ungleich null ist, muss die Zeichenfolge **fac**. `curr_symbol` dort zugeordnet werden, wo das dem **money_base::symbol** entsprechende Element im Formatmuster angezeigt wird. Andernfalls gilt: Wenn **money_base::symbol** am Ende des Formatmusters auftritt und keine weiteren Elemente der Zeichenfolge verbleiben, wird das Währungssymbol nicht zugeordnet. Ansonsten wird das Währungssymbol optional zugeordnet.  
  
 Wenn keine Instanzen von **fac**. `thousands_sep` im Wertteil des Eingabefelds für monetäre Werte (in dem das dem **money_base::symbol** entsprechende Element im Formatmuster angezeigt wird) auftritt, erfolgt keine Gruppierungseinschränkung. Andernfalls werden alle durch **fac**. **grouping** auferlegte Gruppierungseinschränkungen erzwungen. Bitte beachten Sie, dass die resultierende Ziffernsequenz einer ganzen Zahl entspricht, deren niederwertige **fac**. `frac_digits`-Dezimalstellen auf der rechten Seite des Dezimaltrennzeichens berücksichtigt werden.  
  
 Dort, wo das dem **money_base::space** entsprechende Element im Formatmuster angezeigt wird, werden beliebig viele Leerstellen zugeordnet, wenn das Element nicht am Ende des Formatmusters angezeigt wird. Andernfalls werden keine internen Leerzeichen zugeordnet. Ein Element *ch* gilt als Leerzeichen, wenn [use_facet](../standard-library/locale-functions.md#use_facet) < [Ctype](../standard-library/ctype-class.md) \< **CharType**> >( **iosbase**. [getloc](../standard-library/ios-base-class.md#getloc)). [is](../standard-library/ctype-class.md#is)( **ctype_base::space**, *ch*) **TRUE** ist.  
  
### <a name="example"></a>Beispiel  
  Informationen hierzu finden Sie im Beispiel für [get](#get), das `do_get` aufruft.  
  
##  <a name="get"></a> money_get::get  
 Extrahiert einen numerischen Wert aus einer Zeichenfolge, die einen monetären Wert darstellt.  
  
```
iter_type get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    long double& val) const;

iter_type get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    string_type& val) const;
```  
  
### <a name="parameters"></a>Parameter  
 `first`  
 Der Eingabeiterator, der den Anfang der zu konvertierenden Sequenz adressiert.  
  
 `last`  
 Der Eingabeiterator, der das Ende der zu konvertierenden Sequenz adressiert.  
  
 `Intl`  
 Ein boolescher Wert, der den Typ des in der Sequenz vorgesehenen Währungssymbols angibt (**TRUE**, wenn international; **FALSE**, wenn national).  
  
 `Iosbase`  
 Ein Formatkennzeichen, das bei Verwendung angibt, dass das Währungssymbol optional ist. Ansonsten ist das Währungssymbol erforderlich.  
  
 `State`  
 Je nachdem, ob die Vorgänge erfolgreich waren, legt dieses Element die entsprechenden Bitmaskenelemente für den Streamstatus fest.  
  
 `val`  
 Eine Zeichenfolge zum Speichern der konvertierten Sequenz.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Eingabeiterator,der das erste Element nach dem Eingabefeld für den monetären Wert adressiert.  
  
### <a name="remarks"></a>Hinweise  
 Beide Memberfunktionen geben [do_get](#do_get)( `first``,` `last``,` `Intl`, `Iosbase`, `State`, `val`) zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// money_get_get.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
  
int main( )  
{  
   locale loc( "german_germany" );  
  
   basic_stringstream< char > psz;  
   psz << use_facet<moneypunct<char, 1> >(loc).curr_symbol() << "-1.000,56";  
   basic_stringstream< char > psz2;  
   psz2 << "-100056" << use_facet<moneypunct<char, 1> >(loc).curr_symbol();  
  
   ios_base::iostate st = 0;  
   long double fVal;  
  
   psz.flags( psz.flags( )|ios_base::showbase );   
   // Which forced the READING the currency symbol  
   psz.imbue(loc);  
   use_facet < money_get < char > >( loc ).  
      get( basic_istream<char>::_Iter( psz.rdbuf( ) ),     
           basic_istream<char>::_Iter( 0 ), true, psz, st, fVal );  
  
   if ( st & ios_base::failbit )  
      cout << "money_get(" << psz.str( ) << ", intl = 1) FAILED"  
           << endl;  
   else  
      cout << "money_get(" << psz.str( ) << ", intl = 1) = "   
           << fVal/100.0 << endl;  
  
   use_facet < money_get < char > >( loc ).  
      get(basic_istream<char>::_Iter(psz2.rdbuf( )),     
          basic_istream<char>::_Iter(0), false, psz2, st, fVal);  
  
   if ( st & ios_base::failbit )  
      cout << "money_get(" << psz2.str( ) << ", intl = 0) FAILED"   
           << endl;  
   else  
      cout << "money_get(" << psz2.str( ) << ", intl = 0) = "   
           << fVal/100.0 << endl;  
};  
```  
  
##  <a name="iter_type"></a> money_get::iter_type  
 Ein Typ, der einen Eingabeiterator beschreibt.  
  
```
typedef InputIterator iter_type;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter **InputIterator**.  
  
##  <a name="money_get"></a> money_get::money_get  
 Der Konstruktor für Objekte vom Typ `money_get`, die verwendet werden, um numerische Werte aus Sequenzen zu extrahieren, die monetäre Werte darstellen.  
  
```
explicit money_get(size_t _Refs = 0);
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
  
 Der Konstruktor initialisiert sein Basisobjekt mit **locale::**[facet](../standard-library/locale-class.md#facet_class)( **_***Refs*).  
  
##  <a name="string_type"></a> money_get::string_type  
 Ein Typ, der eine Zeichenfolge beschreibt, die Zeichen des Typs **CharType** enthält.  
  
```
typedef basic_string<CharType, Traits, Allocator> string_type;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [basic_string](../standard-library/basic-string-class.md).  
  
## <a name="see-also"></a>Siehe auch  
 [\<locale>](../standard-library/locale.md)   
 [facet-Klasse](../standard-library/locale-class.md#facet_class)   
 [Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)




