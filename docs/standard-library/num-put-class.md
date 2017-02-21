---
title: "num_put-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::num_put"
  - "xlocnum/std::num_put"
  - "num_put"
  - "std.num_put"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "num_put-Klasse"
ms.assetid: 36c5bffc-8283-4201-8ed4-78c4d81f8a17
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# num_put-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet dienen kann, um Konvertierungen von numerischen Werten in Sequenzen vom Typ `CharType` zu steuern.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class CharType,  
    class OutputIterator = ostreambuf_iterator<CharType>>  
class num_put : public locale::facet;  
```  
  
#### <a name="parameters"></a>Parameter  
 `CharType`  
 Der Typ, der innerhalb eines Programms zum Codieren von Zeichen in einem Gebietsschema verwendet wird.  
  
 `OutputIterator`  
 Der Typ des Iterators, in den die numerischen Put-Funktionen ihre Ausgabe schreiben.  
  
## <a name="remarks"></a>Hinweise  
 Wie bei jedem Gebietsschemafacet hat die statische Objekt-ID einen anfänglichen gespeicherten Wert von NULL. Beim erste Versuch, den gespeicherten Wert zuzugreifen speichert einen eindeutigen positiven Wert in **Id.**  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[num_put](#num_put__num_put)|Der Konstruktor für Objekte des Typs `num_put`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#num_put__char_type)|Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.|  
|[iter_type](#num_put__iter_type)|Ein Typ, der einen Ausgabeiterator beschreibt.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[do_put](#num_put__do_put)|Eine virtuelle Funktion, die aufgerufen wird, um eine Zahl in eine Sequenz von `CharType`-Objekten zu konvertieren, die die Zahl darstellt, die für ein bestimmtes Gebietsschema formatiert ist.|  
|[Put](#num_put__put)|Konvertiert eine Zahl in eine Sequenz von `CharType`-Objekten, die die Zahl darstellt, die für ein bestimmtes Gebietsschema formatiert wird.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \< Gebietsschema>  
  
 **Namespace:** std  
  
##  <a name="a-namenumputchartypea-numputchartype"></a><a name="num_put__char_type"></a>  num_put:: char_type  
 Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter **CharType**.  
  
##  <a name="a-namenumputdoputa-numputdoput"></a><a name="num_put__do_put"></a>  num_put:: do_put  
 Eine virtuelle Funktion, die aufgerufen wird, zum Umwandeln einer Zahl in eine Folge von **CharType**s die Anzahl für ein bestimmtes Gebietsschema formatiert.  
  
```  
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    bool val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    long val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    unsigned long val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    double val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    long double val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    const void* val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    const long long val) const;

virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    const unsigned long long val) const;
```  
  
### <a name="parameters"></a>Parameter  
 ` next`  
 Ein Iterator, der das erste Element der eingefügten Zeichenfolge adressiert.  
  
 `_Iosbase`  
 Der Datenstrom enthält Gebietsschema mit Numpunct Facets verwendet, um die Ausgabe und die Flags für das Formatieren der Ausgabe Satzzeichen voneinander getrennt wird angegeben.  
  
 `_Fill`  
 Ein Zeichen, die für den Abstand verwendet wird.  
  
 ` val`  
 Die Nummer oder Boolean-Typ, der ausgegeben werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Ausgabeiterator die Adressen die Position hinter dem letzten Element erzeugt.  
  
### <a name="remarks"></a>Hinweise  
 Die erste als geschützte virtuelle Memberfunktion generiert sequenzielle Elemente ab ` next` zu Integer Ausgabe-Felder aus dem Wert des ` val`. Die Funktion gibt einen Iterator Festlegen der nächsten Stelle zum Einfügen eines Elements über das Ausgabefeld generierte ganze Zahl zurück.  
  
 Die Ausgabe Ganzzahlfeld wird generiert, indem die gleichen Regeln, die die Druckfunktionen für das Generieren von `char` Elemente in einer Datei. Jedes solche Char-Element steht für eine entsprechende Element vom Typ zugeordnet **CharType** durch eine einfache 1: 1-Zuordnung. Bei eine Funktion ein Feld mit Leerzeichen oder die Ziffer 0, jedoch werden `do_put` verwendet stattdessen **Füllung**. Die entsprechende drucken Konvertierungsspezifikation wird wie folgt bestimmt:  
  
-   Wenn **Iosbase**. [Flags](../standard-library/ios-base-class.md#ios_base__flags) & `ios_base::basefield` == `ios_base::`[Okt](../Topic/%3Cios%3E%20functions.md#oct), ist die Konvertierungsspezifikation **lo**.  
  
-   Wenn **iosbase.flags** & **ios_base** == `ios_base::`[hex](../Topic/%3Cios%3E%20functions.md#hex), ist die Konvertierungsspezifikation **lx**.  
  
-   Andernfalls ist die Konvertierungsspezifikation **%ld**.  
  
 Wenn **Iosbase**. [Breite](../standard-library/ios-base-class.md#ios_base__width) ist ungleich NULL ist, wird eine Feldbreite dieses Werts vorangestellt. Die Funktion ruft dann **Iosbase**. **Breite**(0), um die Breite des Felds auf 0 (null) zurückgesetzt.  
  
 Auffüllung erfolgt nur, wenn die minimale Anzahl von Elementen *N* erforderlich, um anzugeben, das Ausgabefeld ist kleiner als **Iosbase**. [Breite](../standard-library/ios-base-class.md#ios_base__width). Auffüllen von Feldern besteht aus einer Folge von *N* – **Breite** Kopien von **Füllung**. Dann Padding erfolgt folgendermaßen:  
  
-   Wenn **Iosbase**. **Flags** & `ios_base::adjustfield` == `ios_base::`[linken](../Topic/%3Cios%3E%20functions.md#left), das Flag **–** vorangestellt wird. (Abstand tritt nach dem generierten Text.)  
  
-   Wenn **iosbase.flags** & **ios_base::adjustfield** == `ios_base::`[interne](../Topic/%3Cios%3E%20functions.md#internal), das Flag **0** vorangestellt wird. (Für ein Ausgabefeld numerische wird Leerraum, in denen die Druckfunktionen mit 0 aufgefüllt.)  
  
-   Andernfalls wird kein zusätzliches Flag vorangestellt. (Abstand tritt auf, bevor der generierten Sequenz.)  
  
 Zum Schluss:  
  
-   Wenn **Iosbase**. **Flags** & `ios_base::`[Showpos](../Topic/%3Cios%3E%20functions.md#showpos) ungleich NULL ist, wird das Flag **+** die Konvertierungsspezifikation vorangestellt wird.  
  
-   Wenn **Iosbase**. **Flags** & **Ios_base::**[Showbase](../Topic/%3Cios%3E%20functions.md#showbase) ungleich NULL ist, wird das Flag **#** die Konvertierungsspezifikation vorangestellt wird.  
  
 Das Format einer ganzen Zahl Ausgabe Feld hängt darüber hinaus von der [gebietsschemafacet](../standard-library/locale-class.md#facet_class)**Fac** vom Aufruf zurückgegebene [Use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) < [Numpunct](../standard-library/numpunct-class.md)\< **Elem**> ( **Iosbase**. [Getloc](../standard-library/ios-base-class.md#ios_base__getloc)). Dies gilt insbesondere in folgenden Fällen:  
  
- **FAc**. [Gruppieren von](../standard-library/numpunct-class.md#numpunct__grouping) bestimmt, wie Ziffern auf der linken Seite des Dezimaltrennzeichens gruppiert werden  
  
- **FAc**. [Thousands_sep](../standard-library/numpunct-class.md#numpunct__thousands_sep) bestimmt die Reihenfolge, die Zifferngruppen links vom Dezimaltrennzeichen  
  
 Wenn keine Gruppierung Einschränkungen vom auferlegt werden **Fac**. **Gruppieren von** (das erste Element hat den Wert CHAR_MAX), dann werden keine Instanzen des **Fac**. `thousands_sep` werden im Ausgabefeld generiert. Andernfalls werden Trennzeichen eingefügt, nachdem die Drucken Konvertierung erfolgt.  
  
 Der zweite virtuelle geschützte Member-Funktion:  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    unsigned long val) const;
```  
  
 verhält sich wie die erste, außer dass es eine Konvertierungsspezifikation von ersetzt **%ld** mit **Lu**.  
  
 Die dritte virtuelle geschützter Member-Funktion:  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    double val) const;
```  
  
 verhält sich wie die erste, außer dass es ein Gleitkomma Ausgabefeld aus dem Wert erzeugt **Val**. **FAc**. [Decimal_point](../standard-library/numpunct-class.md#numpunct__decimal_point) bestimmt die Reihenfolge, die die ganzzahligen Ziffern von der Bruchziffern trennt. Die entsprechende drucken Konvertierungsspezifikation wird wie folgt bestimmt:  
  
-   Wenn **Iosbase**. **Flags** & `ios_base::floatfield` == `ios_base::`[festen](../Topic/%3Cios%3E%20functions.md#fixed), ist die Konvertierungsspezifikation **lf**.  
  
-   Wenn **Iosbase**. **Flags** & **ios_base::floatfield** == `ios_base::`[wissenschaftliche](../Topic/%3Cios%3E%20functions.md#scientific), ist die Konvertierungsspezifikation `le`. Wenn **Iosbase**. **Flags** & `ios_base::`[Großbuchstaben](../Topic/%3Cios%3E%20functions.md#uppercase) ungleich NULL ist, **e** durch ersetzt **E**.  
  
-   Andernfalls ist die Konvertierungsspezifikation **Lg**. Wenn **Iosbase**. **Flags** & **ios_base::uppercase** ist ein Wert ungleich NULL **g** mit ersetzt **G**.  
  
 Wenn **Iosbase**. **Flags** & **ios_base::fixed** ungleich NULL ist oder wenn **Iosbase**. [Genauigkeit](../standard-library/ios-base-class.md#ios_base__precision) ist größer als 0 (null), eine Genauigkeit mit dem Wert **Iosbase**. **Genauigkeit** Konvertierungsspezifikation vorangestellt wird. Abstände verhält sich genauso wie bei einem Integer-Ausgabe-Feld. Auffüllzeichen ist **Füllung**. Zum Schluss:  
  
-   Wenn **Iosbase**. **Flags** & `ios_base::`[Showpos](../Topic/%3Cios%3E%20functions.md#showpos) ungleich NULL ist, wird das Flag **+** die Konvertierungsspezifikation vorangestellt wird.  
  
-   Wenn **Iosbase**. **Flags** & `ios_base::`[Showpoint](../Topic/%3Cios%3E%20functions.md#showpoint) ungleich NULL ist, wird das Flag **#** die Konvertierungsspezifikation vorangestellt wird.  
  
 Der vierte virtuelle geschützte Member-Funktion:  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    long double val) const;
```  
  
 verhält sich die dritte, außer dass die Qualifizierer **l** bei der Konvertierung ersetzt mit **L**.  
  
 Die fünfte virtuellen geschützte Member-Funktion:  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    const void* val) const;
```  
  
 verhält sich die erste, außer dass die Konvertierungsspezifikation `p`**,** sowie alle Qualifizierer Abstand anzugeben.  
  
 Der sechste virtuelle geschützter Member-Funktion:  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    bool val) const;
```  
  
 verhält sich wie die erste, generiert er ein boolescher Ausgabefeld aus ` val`.  
  
 Ein boolescher Ausgabefeld akzeptiert einen von zwei Formen. Wenn **Iosbase**. **Flags** & `ios_base::`[Boolalpha](../Topic/%3Cios%3E%20functions.md#boolalpha) ist **false**, gibt die Memberfunktion `do_put`(_ *Weiter*, \_ *Iosbase*, \_ *Füllen*, ( **lange**) ` val`), erzeugt die in der Regel eine generierte Sequenz entweder 0 (für **false**) oder 1 (für **true**). Andernfalls wird von die generierte Sequenz entweder **Fac**. [Falsename](../standard-library/numpunct-class.md#numpunct__falsename)`)` (für **false**), oder **Fac**. [TrueName](../standard-library/numpunct-class.md#numpunct__truename) (für **true**).  
  
 Der siebte virtuellen geschützte Member-Funktion:  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,  
    Elem fill,
    long long val) const;
```  
  
 verhält sich wie die erste, außer dass es eine Konvertierungsspezifikation von ersetzt **%ld** mit **Lld**.  
  
 Die achte virtuellen geschützte Member-Funktion:  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,  
    Elem fill,
    unsigned long long val) const;
```  
  
 verhält sich wie die erste, außer dass es eine Konvertierungsspezifikation von ersetzt `ld` mit `llu`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [put](#num_put__put), welche `do_put`.  
  
##  <a name="a-namenumputitertypea-numputitertype"></a><a name="num_put__iter_type"></a>  num_put:: iter_type  
 Ein Typ, der einen Ausgabeiterator beschreibt.  
  
```  
typedef OutputIterator iter_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter **OutputIterator.**  
  
##  <a name="a-namenumputnumputa-numputnumput"></a><a name="num_put__num_put"></a>  num_put:: num_put  
 Der Konstruktor für Objekte des Typs `num_put`.  
  
```  
explicit num_put(size_t _Refs = 0);
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
  
 Der Konstruktor initialisiert die Basisobjekt mit **Gebietsschema::**[Facet](../standard-library/locale-class.md#facet_class)(_ *Refs*).  
  
##  <a name="a-namenumputputa-numputput"></a><a name="num_put__put"></a>  num_put:: Put  
 Konvertiert eine Zahl in eine Sequenz von **CharType**s die Anzahl für ein bestimmtes Gebietsschema formatiert.  
  
```  
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    bool val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    long val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    unsigned long val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    Long long val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    Unsigned long long val) const;

 
 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    double val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    long double val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    const void* val) const;
```  
  
### <a name="parameters"></a>Parameter  
 ` dest`  
 Ein Iterator, der das erste Element der eingefügten Zeichenfolge adressiert.  
  
 `_Iosbase`  
 Angegebenen Stream, der mit dem Numpunct-Facet verwendet, um die Ausgabe und die Flags für das Formatieren der Ausgabe Satzzeichen voneinander getrennt Gebietsschema enthält.  
  
 `_Fill`  
 Ein Zeichen, die für den Abstand verwendet wird.  
  
 ` val`  
 Die Nummer oder Boolean-Typ, der ausgegeben werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Ausgabeiterator die Adressen die Position hinter dem letzten Element erzeugt.  
  
### <a name="remarks"></a>Hinweise  
 Alle Memberfunktionen geben [Do_put](#num_put__do_put)( ` next`, `_Iosbase`, `_Fill`, ` val`).  
  
### <a name="example"></a>Beispiel  
  
```  
// num_put_put.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
   basic_stringstream<char> psz2;  
   ios_base::iostate st = 0;  
   long double fVal;  
   cout << "The thousands separator is: "   
        << use_facet < numpunct <char> >(loc).thousands_sep( )   
        << endl;  
  
   psz2.imbue( loc );  
   use_facet < num_put < char > >  
      ( loc ).put(basic_ostream<char>::_Iter(psz2.rdbuf( ) ),  
                    psz2, ' ', fVal=1000.67);  
  
   if ( st & ios_base::failbit )  
      cout << "num_put( ) FAILED" << endl;  
   else  
      cout << "num_put( ) = " << psz2.rdbuf( )->str( ) << endl;  
}  
```  
  
```Output  
The thousands separator is: .  
num_put( ) = 1.000,67  
```  
  
## <a name="see-also"></a>Siehe auch  
 [\< Gebietsschema>](../standard-library/locale.md)   
 [Facet-Klasse](../standard-library/locale-class.md#facet_class)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)

