---
title: "money_get-Klasse"
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
  - "xlocmon/std::money_get"
  - "money_get"
  - "std.money_get"
  - "std::money_get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "money_get-Klasse"
ms.assetid: 692d3374-3fe7-4b46-8aeb-f8d91ed66b2e
caps.latest.revision: 18
caps.handback.revision: "18"
ms.author: "corob"
manager: "ghogen"
---
# money_get-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

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
 Wie bei jedem Gebietsschemafacet hat die statische Objekt-ID einen anfänglichen gespeicherten Wert von NULL. Beim erste Versuch, den gespeicherten Wert zuzugreifen speichert einen eindeutigen positiven Wert in **Id.**  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[money_get](#money_get__money_get)|Der Konstruktor für Objekte vom Typ `money_get`, die verwendet werden, um numerische Werte aus Sequenzen zu extrahieren, die monetäre Werte darstellen.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#money_get__char_type)|Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.|  
|[iter_type](#money_get__iter_type)|Ein Typ, der einen Eingabeiterator beschreibt.|  
|[string_type](#money_get__string_type)|Ein Typ, der eine Zeichenfolge beschreibt, die Zeichen vom Typ `CharType` enthält.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[do_get](#money_get__do_get)|Eine virtuelle Funktion, die aufgerufen wird, um einen Zahlenwert aus einer Zeichenfolge zu extrahieren, die einen monetären Wert darstellt.|  
|[Erhalten](#money_get__get)|Extrahiert einen numerischen Wert aus einer Zeichenfolge, die einen monetären Wert darstellt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \< Gebietsschema>  
  
 **Namespace:** std  
  
##  <a name="a-namemoneygetchartypea-moneygetchartype"></a><a name="money_get__char_type"></a>  money_get:: char_type  
 Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter **CharType**.  
  
##  <a name="a-namemoneygetdogeta-moneygetdoget"></a><a name="money_get__do_get"></a>  money_get:: do_get  
 Virtuelle Funktion, die aufgerufen wird, um extrahiert einen numerischen Wert aus einer Zeichenfolge, die einen monetären Wert darstellt.  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    bool _Intl,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const virtual iter_type do_get(iter_type first,
    iter_type last,
    bool _Intl,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    string_type& val) const
```  
  
### <a name="parameters"></a>Parameter  
 `first`  
 Eingabeiterator, der den Anfang der Sequenz konvertiert werden.  
  
 `last`  
 Geben Sie ein Iterator, der das Ende der Sequenz konvertiert werden.  
  
 `_Intl`  
 Ein boolescher Wert, der den Typ des in der Sequenz erwartet Währungssymbol: **true** Wenn internationale **false** Wenn inländischen.  
  
 `_Iosbase`  
 Ein Format kennzeichnen, die bei der Gruppe gibt an, dass das Währungssymbol optional ist. Andernfalls ist es erforderlich.  
  
 `_State`  
 Legt die entsprechende Bitmaske Elemente für den Status der Stream nach, ob die Vorgänge erfolgreich oder nicht war.  
  
 `val`  
 Eine Zeichenfolge, die Speichern der konvertierten Sequenz.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein eingabeiterator, der das erste Element nach dem Monetäres Eingabefeld Adressierung.  
  
### <a name="remarks"></a>Hinweise  
 Die erste als geschützte virtuelle Memberfunktion sequenzielle Elemente ab, die auf den ersten in der Sequenz entsprechen versucht [ `first`, `last`), bis er eine vollständige erkannt, Eingabe monetären nicht leeren Feld. Wenn erfolgreich, wird dieses Feld auf eine Sequenz von einer oder mehreren Dezimalstellen, optional ein Minuszeichen vorangestellt umgewandelt ( `–`), um die Menge darzustellen und speichert das Ergebnis in der [String_type](#money_get__string_type) Objekt `val`. Es gibt einen Iterator, der das erste Element nach dem Monetäres Eingabefeld festlegen. Die Funktion speichert, andernfalls eine leere Sequenz in `val` und `ios_base::failbit` in `_State`. Es gibt einen Iterator, der das erste Element nach einem Präfix von einem gültigen Monetäres Eingabefeld festlegen. In beiden Fällen, wenn der Rückgabewert gleich `last`, die Funktion legt `ios_base::eofbit` in `_State`.  
  
 Die zweite als geschützte virtuelle Memberfunktion verhält sich wie die erste, gelingt die Sequenz Ziffer optional mit Vorzeichen in einen Wert vom Typ konvertiert `long double` und speichert diesen Wert in `val`.  
  
 Das Format der ein Monetäres Eingabefeld richtet sich nach der [gebietsschemafacet](../standard-library/locale-class.md#facet_class)**Fac** zurückgegebene effektive [Use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) < [Moneypunct](../standard-library/moneypunct-class.md)\< **CharType**, **Intl**>> ( **Iosbase**. [Getloc](../standard-library/ios-base-class.md#ios_base__getloc)).  
  
 Dies gilt insbesondere in folgenden Fällen:  
  
- **FAc**. [Neg_format](../standard-library/moneypunct-class.md#moneypunct__neg_format) bestimmt die Reihenfolge, in denen Komponenten des Felds auftreten.  
  
- **FAc**. [Curr_symbol](../standard-library/moneypunct-class.md#moneypunct__curr_symbol) bestimmt die Reihenfolge der Elemente, aus denen ein Währungssymbol besteht.  
  
- **FAc**. [Positive_sign](../standard-library/moneypunct-class.md#moneypunct__positive_sign) bestimmt die Reihenfolge der Elemente, aus denen ein positiven Vorzeichen besteht.  
  
- **FAc**. [Negative_sign](../standard-library/moneypunct-class.md#moneypunct__negative_sign) bestimmt die Reihenfolge der Elemente, aus denen ein negativen Vorzeichen besteht.  
  
- **FAc**. [Gruppieren von](../standard-library/moneypunct-class.md#moneypunct__grouping) bestimmt, wie Ziffern auf der linken Seite des Dezimaltrennzeichens gruppiert werden.  
  
- **FAc**. [Thousands_sep](../standard-library/moneypunct-class.md#moneypunct__thousands_sep) bestimmt das Element, das Zifferngruppen links vom Dezimaltrennzeichen.  
  
- **FAc**. [Decimal_point](../standard-library/moneypunct-class.md#moneypunct__decimal_point) bestimmt das Element an, die die ganzzahligen Ziffern von der Bruchziffern trennt.  
  
- **FAc**. [Frac_digits](../standard-library/moneypunct-class.md#moneypunct__frac_digits) bestimmt die Anzahl der bedeutenden Ziffern rechts vom Dezimaltrennzeichen. Beim Analysieren der Geldbetrag mit Weitere Bruchziffern als für aufgerufen werden, indem `frac_digits`, `do_get` beendet die Analyse nach Verbrauch höchstens `frac_digits` Zeichen.  
  
 Wenn die Zeichenfolge Zeichen ( **Fac**. `negative_sign` oder **Fac**. `positive_sign`) verfügt über mehr als ein Element, nur das erste Element entspricht, in dem das Element gleich **money_base::sign** im Formatmuster angezeigt ( **Fac**. `neg_format`). Alle übrigen Elemente werden am Ende der Monetäres Eingabefeld zugeordnet. Wenn keine Zeichenfolge ein erstes Element verfügt, das nächste Element in der Monetäres Eingabefeld entspricht, stammt die Zeichenfolge für die Anmeldung als leer, und die Anmeldung positiv ist.  
  
 Wenn **Iosbase**. [Flags](../standard-library/ios-base-class.md#ios_base__flags) & [Showbase](../Topic/%3Cios%3E%20functions.md#showbase) ungleich NULL ist, wird die Zeichenfolge **Fac**. `curr_symbol` Where übereinstimmen muss das Element gleich **money_base::symbol** im Formatmuster angezeigt wird. Andernfalls gilt: Wenn **money_base::symbol** tritt am Ende des Formatmusters, und wenn keine Elemente der Zeichenfolge Zeichen übereinstimmen weiterhin, wird das Währungssymbol stimmt nicht überein. Das Währungssymbol entspricht, andernfalls optional.  
  
 Wenn keine Instanzen von **Fac**. `thousands_sep` treten in der Wertteil des Monetäres Eingabefeld (, in dem das Element, das **money_base::value** im Formatmuster angezeigt wird), ist keine Gruppierung Einschränkung auferlegt werden. Andernfalls Gruppierung Einschränkungen aufgrund von **Fac**. **Gruppieren von** wird erzwungen. Beachten Sie, dass die resultierende Ziffern eine ganze Zahl, deren niederwertigen darstellt **Fac**. `frac_digits` Dezimalstellen gelten rechts neben dem Dezimaltrennzeichen an.  
  
 Beliebig viele Leerstellen abgeglichen wird, in dem das Element gleich **money_base::space** in das Formatmuster angezeigt wird, wenn sie nicht am Ende des Formatmusters angezeigt wird. Andernfalls wird keine interne Leerzeichen verglichen. Ein Element *ch* wird als Leerzeichen betrachtet, wenn [Use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) < [Ctype](../standard-library/ctype-class.md)\< **CharType**>> ( **Iosbase**. [Getloc](../standard-library/ios-base-class.md#ios_base__getloc)). [ist](../standard-library/ctype-class.md#ctype__is)( **ctype_base::space**, *ch*) ist **true**.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [abrufen](#money_get__get), welche `do_get`.  
  
##  <a name="a-namemoneygetgeta-moneygetget"></a><a name="money_get__get"></a>  money_get:: Get  
 Extrahiert einen numerischen Wert aus einer Zeichenfolge, die einen monetären Wert darstellt.  
  
```
iter_type get(iter_type first,
    iter_type last,
    bool _Intl,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;

iter_type get(iter_type first,
    iter_type last,
    bool _Intl,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    string_type& val) const;
```  
  
### <a name="parameters"></a>Parameter  
 `first`  
 Eingabeiterator, der den Anfang der Sequenz konvertiert werden.  
  
 `last`  
 Geben Sie ein Iterator, der das Ende der Sequenz konvertiert werden.  
  
 `_Intl`  
 Ein boolescher Wert, der den Typ des in der Sequenz erwartet Währungssymbol: **true** Wenn internationale **false** Wenn inländischen.  
  
 `_Iosbase`  
 Ein Format kennzeichnen, die bei der Gruppe gibt an, dass das Währungssymbol optional ist. Andernfalls ist es erforderlich  
  
 `_State`  
 Legt die entsprechende Bitmaske Elemente für den Status der Stream nach, ob die Vorgänge erfolgreich waren.  
  
 `val`  
 Eine Zeichenfolge, die Speichern der konvertierten Sequenz.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein eingabeiterator, der das erste Element nach dem Monetäres Eingabefeld Adressierung.  
  
### <a name="remarks"></a>Hinweise  
 Beide Memberfunktionen geben [Do_get](#money_get__do_get)( `first``,` `last``,` `_Intl`, `_Iosbase`, `_State`, `val`).  
  
### <a name="example"></a>Beispiel  
  
```  
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
  
##  <a name="a-namemoneygetitertypea-moneygetitertype"></a><a name="money_get__iter_type"></a>  money_get:: iter_type  
 Ein Typ, der einen Eingabeiterator beschreibt.  
  
```
typedef InputIterator iter_type;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter **InputIterator**.  
  
##  <a name="a-namemoneygetmoneygeta-moneygetmoneyget"></a><a name="money_get__money_get"></a>  money_get:: money_get  
 Der Konstruktor für Objekte vom Typ `money_get`, die verwendet werden, um numerische Werte aus Sequenzen zu extrahieren, die monetäre Werte darstellen.  
  
```
explicit money_get(size_t _Refs = 0);
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
  
 Der Konstruktor initialisiert die Basisobjekt mit **Gebietsschema::**[Facet](../standard-library/locale-class.md#facet_class)( **_***Refs*).  
  
##  <a name="a-namemoneygetstringtypea-moneygetstringtype"></a><a name="money_get__string_type"></a>  money_get:: string_type  
 Ein Typ, der eine Zeichenfolge mit Zeichen vom Typ beschreibt **CharType**.  
  
```
typedef basic_string<CharType, Traits, Allocator> string_type;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [Basic_string](../standard-library/basic-string-class.md).  
  
## <a name="see-also"></a>Siehe auch  
 [\< Gebietsschema>](../standard-library/locale.md)   
 [Facet-Klasse](../standard-library/locale-class.md#facet_class)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)



