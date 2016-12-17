---
title: "money_put-Klasse"
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
  - "std::money_put"
  - "xlocmon/std::money_put"
  - "money_put"
  - "std.money_put"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "money_put-Klasse"
ms.assetid: f439fd56-c9b1-414c-95e1-66c918c6eee6
caps.latest.revision: 19
caps.handback.revision: "19"
ms.author: "corob"
manager: "ghogen"
---
# money_put-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet dienen kann, um Konvertierungen von monetären Werten in Sequenzen vom Typ `CharType` zu steuern.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class CharType,  
    class OutputIterator = ostreambuf_iterator<CharType>>  
class money_put : public locale::facet;  
```  
  
#### <a name="parameters"></a>Parameter  
 `CharType`  
 Der Typ, der innerhalb eines Programms zum Codieren von Zeichen in einem Gebietsschema verwendet wird.  
  
 `OutputIterator`  
 Der Typ des Iterators, in den die monetären Put-Funktionen ihre Ausgabe schreiben.  
  
## <a name="remarks"></a>Hinweise  
 Wie bei jedem Gebietsschemafacet hat die statische Objekt-ID einen anfänglichen gespeicherten Wert von NULL. Beim erste Versuch, den gespeicherten Wert zuzugreifen speichert einen eindeutigen positiven Wert in **Id.**  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[money_put](#money_put__money_put)|Der Konstruktor für Objekte des Typs `money_put`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#money_put__char_type)|Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.|  
|[iter_type](#money_put__iter_type)|Ein Typ, der einen Ausgabeiterator beschreibt.|  
|[string_type](#money_put__string_type)|Ein Typ, der eine Zeichenfolge beschreibt, die Zeichen vom Typ `CharType` enthält.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[do_put](#money_put__do_put)|Eine virtuelle Funktion, die aufgerufen wird, um entweder eine Zahl oder eine Zeichenfolge in eine Zeichenfolge zu konvertieren, die einen monetären Wert darstellt.|  
|[Put](#money_put__put)|Konvertiert entweder eine Zahl oder eine Zeichenfolge in eine Zeichenfolge, die einen monetären Wert darstellt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \< Gebietsschema>  
  
 **Namespace:** std  
  
##  <a name="a-namemoneyputchartypea-moneyputchartype"></a><a name="money_put__char_type"></a>  money_put:: char_type  
 Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter **CharType**.  
  
##  <a name="a-namemoneyputdoputa-moneyputdoput"></a><a name="money_put__do_put"></a>  money_put:: do_put  
 Eine virtuelle Funktion, die aufgerufen wird, um entweder eine Zahl oder eine Zeichenfolge in eine Zeichenfolge zu konvertieren, die einen monetären Wert darstellt.  
  
```  
virtual iter_type do_put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,   
    const string_type& val) const;

 
virtual iter_type do_put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,  
    long double val) const;
```  
  
### <a name="parameters"></a>Parameter  
 ` next`  
 Ein Iterator, der das erste Element der eingefügten Zeichenfolge adressiert.  
  
 `_Intl`  
 Ein boolescher Wert, der den Typ des in der Sequenz erwartet Währungssymbol: **true** Wenn internationale **false** Wenn inländischen.  
  
 `_Iosbase`  
 Ein Format kennzeichnen, die bei der Gruppe gibt an, dass das Währungssymbol optional ist. Andernfalls ist es erforderlich  
  
 `_Fill`  
 Ein Zeichen, die für den Abstand verwendet wird.  
  
 ` val`  
 Ein String-Objekt konvertiert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Ausgabeiterator die Adressen die Position hinter dem letzten Element erzeugt.  
  
### <a name="remarks"></a>Hinweise  
 Die erste als geschützte virtuelle Memberfunktion generiert sequenzielle Elemente ab ` next` erzeugt ein Monetäres Ausgabefeld aus der [String_type](#money_put__string_type) Objekt ` val`. Die Sequenz von ` val` müssen beginnen, eine oder mehrere Dezimalstellen, optional mit vorangestelltem ein Minuszeichen (-), die den Zeitraum darstellt. Die Funktion gibt einen Iterator, der das erste Element nach dem generierten Monetäres Ausgabefeld festlegen.  
  
 Die zweite als geschützte virtuelle Memberfunktion verhält sich wie die erste, außer, dass die It effektiv erste konvertiert ` val` in eine Folge von Dezimalziffern optional wird ein Minuszeichen vorangestellt dann konvertiert, wie oben beschrieben.  
  
 Das Format der ein Monetäres Ausgabefeld richtet sich nach der [gebietsschemafacet](../standard-library/locale-class.md#facet_class) Fac zurückgegebene (effektiv) [Use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) < [Moneypunct](../standard-library/moneypunct-class.md)\< **CharType**, **Intl**>> ( **Iosbase**. [Getloc](../standard-library/ios-base-class.md#ios_base__getloc)).  
  
 Dies gilt insbesondere in folgenden Fällen:  
  
- **FAc**. [Pos_format](../standard-library/moneypunct-class.md#moneypunct__pos_format) bestimmt die Reihenfolge, in der Komponenten des Felds für einen nicht negativen Wert generiert werden.  
  
- **FAc**. [Neg_format](../standard-library/moneypunct-class.md#moneypunct__neg_format) bestimmt die Reihenfolge, in der Komponenten des Felds für einen negativen Wert generiert werden.  
  
- **FAc**. [Curr_symbol](../standard-library/moneypunct-class.md#moneypunct__curr_symbol) bestimmt die Reihenfolge der Elemente, die für ein Währungssymbol zu generieren.  
  
- **FAc**. [Positive_sign](../standard-library/moneypunct-class.md#moneypunct__positive_sign) bestimmt die Reihenfolge der Elemente, die für ein positiven Vorzeichen zu generieren.  
  
- **FAc**. [Negative_sign](../standard-library/moneypunct-class.md#moneypunct__negative_sign) bestimmt die Reihenfolge der Elemente, die für ein negativen Vorzeichen zu generieren.  
  
- **FAc**. [Gruppieren von](../standard-library/moneypunct-class.md#moneypunct__grouping) bestimmt, wie Ziffern auf der linken Seite des Dezimaltrennzeichens gruppiert werden.  
  
- **FAc**. [Thousands_sep](../standard-library/moneypunct-class.md#moneypunct__thousands_sep) bestimmt das Element, das Zifferngruppen links vom Dezimaltrennzeichen.  
  
- **FAc**. [Decimal_point](../standard-library/moneypunct-class.md#moneypunct__decimal_point) bestimmt das Element an, die die ganzzahligen Ziffern von jedem Bruchziffern trennt.  
  
- **FAc**. [Frac_digits](../standard-library/moneypunct-class.md#moneypunct__frac_digits) bestimmt die Anzahl der bedeutenden Ziffern rechts vom Dezimaltrennzeichen.  
  
 Wenn die Zeichenfolge Zeichen ( **Fac**. `negative_sign` oder **Fac**. `positive_sign`) verfügt über mehr als ein Element, nur das erste Element wird generiert, in dem das Element gleich **money_base::sign** im Formatmuster angezeigt ( **Fac**. `neg_format` oder **Fac**. `pos_format`). Alle übrigen Elemente werden am Ende der Monetäres Ausgabefeld generiert.  
  
 Wenn **Iosbase**. [Flags](../standard-library/ios-base-class.md#ios_base__flags) & [Showbase](../Topic/%3Cios%3E%20functions.md#showbase) ungleich NULL ist, wird die Zeichenfolge **Fac**. `curr_symbol` wird generiert, in dem das Element gleich **money_base::symbol** im Formatmuster angezeigt wird. Andernfalls wird kein Währungssymbol generiert.  
  
 Wenn keine Gruppierung Einschränkungen vom auferlegt werden **Fac**. **Gruppieren von** (das erste Element hat den Wert CHAR_MAX), dann werden keine Instanzen des **Fac**. `thousands_sep` werden in der Value-Teil der Monetäres Ausgabefeld generiert (wobei das Element, das **money_base::value** im Formatmuster angezeigt wird). Wenn **Fac**. `frac_digits` ist 0 (null), wird keine Instanz des **Fac**. `decimal_point` wird nach den Dezimalstellen generiert. Die resultierende Monetäres Ausgabefeld platziert, andernfalls die untere **Fac**. `frac_digits` die Dezimalstellen rechts vom Dezimaltrennzeichen.  
  
 Auffüllung für alle numerischen Ausgabefeld, außer dass bei tritt **Iosbase**. **Flags** & **Iosbase**. [interne](../Topic/%3Cios%3E%20functions.md#internal) ist ungleich NULL, interne Abstand wird generiert, in dem das Element gleich **money_base::space** in das Formatmuster angezeigt wird, wenn er angezeigt wird. Andernfalls tritt ein interner Abstand vor der generierten Sequenz. Auffüllzeichen ist **Füllung**.  
  
 Ruft die Funktion **Iosbase**. **Breite**(0), um die Breite des Felds auf 0 (null) zurückgesetzt.  
  
### <a name="example"></a>Beispiel  
  Finden Sie im Beispiel für [put](#money_put__put), bei dem die virtuelle Memberfunktion, indem aufgerufen wird **put**.  
  
##  <a name="a-namemoneyputitertypea-moneyputitertype"></a><a name="money_put__iter_type"></a>  money_put:: iter_type  
 Ein Typ, der einen Ausgabeiterator beschreibt.  
  
```  
typedef OutputIterator iter_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter **OutputIterator.**  
  
##  <a name="a-namemoneyputmoneyputa-moneyputmoneyput"></a><a name="money_put__money_put"></a>  money_put:: money_put  
 Der Konstruktor für Objekte des Typs `money_put`.  
  
```  
explicit money_put(size_t _Refs = 0);
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
  
##  <a name="a-namemoneyputputa-moneyputput"></a><a name="money_put__put"></a>  money_put:: Put  
 Konvertiert entweder eine Zahl oder eine Zeichenfolge in eine Zeichenfolge, die einen monetären Wert darstellt.  
  
```  
iter_type put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,   
    const string_type& val) const;

 
iter_type put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,  
    long double val) const;
```  
  
### <a name="parameters"></a>Parameter  
 ` next`  
 Ein Iterator, der das erste Element der eingefügten Zeichenfolge adressiert.  
  
 `_Intl`  
 Ein boolescher Wert, der den Typ des in der Sequenz erwartet Währungssymbol: **true** Wenn internationale **false** Wenn inländischen.  
  
 `_Iosbase`  
 Ein Format kennzeichnen, die bei der Gruppe gibt an, dass das Währungssymbol optional ist. Andernfalls ist es erforderlich  
  
 `_Fill`  
 Ein Zeichen, die für den Abstand verwendet wird.  
  
 ` val`  
 Ein String-Objekt konvertiert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Ausgabeiterator die Adressen die Position hinter dem letzten Element erzeugt.  
  
### <a name="remarks"></a>Hinweise  
 Beide Memberfunktionen geben [Do_put](#money_put__do_put)( ` next`, `_Intl`, `_Iosbase`, `_Fill`, ` val`).  
  
### <a name="example"></a>Beispiel  
  
```  
// money_put_put.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
//   locale loc( "german_germany" );  
   locale loc( "english_canada" );  
   basic_stringstream<char> psz, psz2;  
   ios_base::iostate st = 0;  
  
   psz2.imbue( loc );  
   psz2.flags( psz2.flags( )|ios_base::showbase ); // force the printing of the currency symbol  
   use_facet < money_put < char > >(loc).put(basic_ostream<char>::_Iter( psz2.rdbuf( ) ), true, psz2, st, 100012);  
   if (st & ios_base::failbit)  
      cout << "money_put( ) FAILED" << endl;  
   else  
      cout << "money_put( ) = \"" << psz2.rdbuf( )->str( ) <<"\""<< endl;     
  
   st = 0;  
};  
```  
  
```Output  
money_put( ) = "CAD1,000.12"  
```  
  
##  <a name="a-namemoneyputstringtypea-moneyputstringtype"></a><a name="money_put__string_type"></a>  money_put:: string_type  
 Ein Typ, der eine Zeichenfolge mit Zeichen vom Typ beschreibt **CharType**.  
  
```  
typedef basic_string<CharType, Traits, Allocator> string_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ beschreibt eine Spezialisierung der Vorlagenklasse [Basic_string](../standard-library/basic-string-class.md) deren Objekte können Sequenzen von Elementen aus der Quellsequenz speichern.  
  
## <a name="see-also"></a>Siehe auch  
 [\< Gebietsschema>](../standard-library/locale.md)   
 [Facet-Klasse](../standard-library/locale-class.md#facet_class)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)

