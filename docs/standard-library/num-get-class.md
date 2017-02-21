---
title: "num_get-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "num_get"
  - "std::num_get"
  - "std.num_get"
  - "xlocnum/std::num_get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "num_get-Klasse"
ms.assetid: 9933735d-3918-4b17-abad-5fca2adc62d7
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# num_get-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet dienen kann, um Konvertierungen von Sequenzen des Typs `CharType` in numerische Werte zu steuern.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>  
class num_get : public locale::facet;
```  
  
#### <a name="parameters"></a>Parameter  
 `CharType`  
 Der Typ, der innerhalb eines Programms zum Codieren von Zeichen in einem Gebietsschema verwendet wird.  
  
 `InputIterator`  
 Der Typ des Iterators, von dem die numerische get-Funktionen ihre Eingabe lesen.  
  
## <a name="remarks"></a>Hinweise  
 Wie bei jedem Gebietsschemafacet hat die statische Objekt-ID einen anfänglichen gespeicherten Wert von NULL. Beim erste Versuch, den gespeicherten Wert zuzugreifen speichert einen eindeutigen positiven Wert in **Id.**  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[num_get](#num_get__num_get)|Der Konstruktor für Objekte vom Typ `num_get`, die verwendet werden, um numerische Werte aus Sequenzen zu extrahieren.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#num_get__char_type)|Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.|  
|[iter_type](#num_get__iter_type)|Ein Typ, der einen Eingabeiterator beschreibt.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[do_get](#num_get__do_get)|Eine virtuelle Funktion, die aufgerufen wird, um einen numerischen oder booleschen Wert aus einer Zeichenfolge aufzurufen.|  
|[Erhalten](#num_get__get)|Extrahiert einen numerischen oder booleschen Wert aus einer Zeichenfolge.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \< Gebietsschema>  
  
 **Namespace:** std  
  
##  <a name="a-namenumgetchartypea-numgetchartype"></a><a name="num_get__char_type"></a>  num_get:: char_type  
 Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter **CharType**.  
  
##  <a name="a-namenumgetdogeta-numgetdoget"></a><a name="num_get__do_get"></a>  num_get:: do_get  
 Eine virtuelle Funktion, die aufgerufen wird, um einen numerischen oder booleschen Wert aus einer Zeichenfolge aufzurufen.  
  
```
virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long& val) const;virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned short& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned int& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long long& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    float& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;

virtual iter_type do_get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;
```  
  
### <a name="parameters"></a>Parameter  
 `first`  
 Der Anfang des Bereichs von Zeichen aus dem die Anzahl gelesen.  
  
 `last`  
 Das Ende des Bereichs von Zeichen aus dem die Anzahl gelesen.  
  
 `_Iosbase`  
 Die [Ios_base](../standard-library/ios-base-class.md) deren Flags werden durch die Konvertierung verwendet.  
  
 `_State`  
 Der Zustand, der die Failbit (finden Sie unter [ios_base:: iostate](../standard-library/ios-base-class.md#ios_base__iostate)), die bei einem Fehler hinzugefügt wird.  
  
 `val`  
 Der gelesene Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Iterator, nachdem der Wert gelesen wurde.  
  
### <a name="remarks"></a>Hinweise  
 Die erste virtuelle geschützter Member-Funktion  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `long& val`  
  
 `) const;`  
  
 gleicht sequenzielle Elemente, beginnend bei `first` in der Sequenz `[``first``,` `last``)` bis er eine vollständige erkannt, Eingabe Integer nicht leeren Feld. Wenn erfolgreich, wird dieses Feld in den entsprechenden-Wert als Typ umgewandelt `long``,` und speichert das Ergebnis in `val`. Es gibt einen Iterator, der das erste Element nach dem numerischen Eingabefeld festlegen. Andernfalls speichert die Funktion "nothing" in `val` und `ios_base::failbit` in `state`. Es gibt einen Iterator, der das erste Element nach einem Präfix von einem Eingabefeld gültige ganze Zahl festlegen. In beiden Fällen, wenn der Rückgabewert gleich `last`, die Funktion legt `ios_base::eofbit` in `state`.  
  
 Feld für die ganze Zahl konvertiert, indem die gleichen Regeln, die von der Scan-Funktionen für den Abgleich und konvertieren eine Reihe von `char` Elemente aus einer Datei. (Alle diese `char` Element steht für eine entsprechende Element vom Typ zuordnen `Elem` durch eine einfache, 1: 1, zuordnen.) Die entsprechende Überprüfung Konvertierungsspezifikation wird wie folgt bestimmt:  
  
 Wenn `iosbase.`[ios_base:: Flags](../standard-library/ios-base-class.md#ios_base__flags)`() & ios_base::basefield == ios_base::`[Okt](../Topic/%3Cios%3E%20functions.md#oct), ist die Konvertierungsspezifikation `lo`.  
  
 Wenn `iosbase.flags() & ios_base::basefield == ios_base::`[hex](../Topic/%3Cios%3E%20functions.md#hex), ist die Konvertierungsspezifikation `lx`.  
  
 Wenn `iosbase.flags() & ios_base::basefield == 0`, ist die Konvertierungsspezifikation `li`.  
  
 Andernfalls ist die Konvertierungsspezifikation `ld`.  
  
 Das Format eines Eingabefelds ganze Zahl hängt darüber hinaus von der [gebietsschemafacet](../standard-library/locale-class.md#facet_class)`fac` vom Aufruf zurückgegebene [Use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) `<`[Numpunct](../standard-library/numpunct-class.md)`<Elem>(iosbase.` [ios_base:: getloc](../standard-library/ios-base-class.md#ios_base__getloc)`())`. Dies gilt insbesondere in folgenden Fällen:  
  
 `fac.` [numpunct:: GROUPING](../standard-library/numpunct-class.md#numpunct__grouping) `()` Bestimmt, wie Ziffern auf der linken Seite des Dezimaltrennzeichens gruppiert werden  
  
 `fac.` [numpunct:: thousands_sep](../standard-library/numpunct-class.md#numpunct__thousands_sep) `()` Bestimmt die Reihenfolge, die Zifferngruppen links vom Dezimaltrennzeichen.  
  
 Wenn keine Instanzen von `fac.thousands_sep()` auftreten in der numerischen Eingabefeld ist keine Gruppierung Einschränkung auferlegt werden. Andernfalls Gruppierung Einschränkungen aufgrund der `fac.grouping()` werden erzwungen und Trennzeichen werden entfernt, bevor die Konvertierung Scan auftritt.  
  
 Der vierte virtuelle geschützte Member-Funktion:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `unsigned long& val`  
  
 `) const;`  
  
 verhält sich wie die erste, außer dass es eine Konvertierungsspezifikation von ersetzt `ld` mit `lu`. Wenn erfolgreiche numerische Eingabefeld in einen Wert vom Typ konvertiert `unsigned long` und speichert diesen Wert in `val`.  
  
 Die fünfte virtuellen geschützte Member-Funktion:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `long long& val`  
  
 `) const;`  
  
 verhält sich wie die erste, außer dass es eine Konvertierungsspezifikation von ersetzt `ld` mit `lld`. Wenn erfolgreiche numerische Eingabefeld in einen Wert vom Typ konvertiert `long long` und speichert diesen Wert in `val`.  
  
 Der sechste virtuelle geschützter Member-Funktion:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `unsigned long long& val`  
  
 `) const;`  
  
 verhält sich wie die erste, außer dass es eine Konvertierungsspezifikation von ersetzt `ld` mit `llu`. Wenn erfolgreiche numerische Eingabefeld in einen Wert vom Typ konvertiert `unsigned long long` und speichert diesen Wert in `val`.  
  
 Der siebte virtuellen geschützte Member-Funktion:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `float& val`  
  
 `) const;`  
  
 verhält sich wie die erste, außer dass er versucht, eine vollständige, nicht leeren Gleitkomma Eingabefeld übereinstimmen. `fac.`[numpunct:: decimal_point](../standard-library/numpunct-class.md#numpunct__decimal_point)`()` bestimmt die Reihenfolge, die die ganzzahligen Ziffern von der Bruchziffern trennt. Ist die entsprechende Überprüfung Konvertierungsspezifizierer `lf`.  
  
 Die achte virtuellen geschützte Member-Funktion:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `double& val`  
  
 `) const;`  
  
 verhält sich wie die erste, außer dass er versucht, eine vollständige, nicht leeren Gleitkomma Eingabefeld übereinstimmen. `fac.`[numpunct:: decimal_point](../standard-library/numpunct-class.md#numpunct__decimal_point)`()` bestimmt die Reihenfolge, die die ganzzahligen Ziffern von der Bruchziffern trennt. Ist die entsprechende Überprüfung Konvertierungsspezifizierer `lf`.  
  
 Der neunte virtuellen geschützte Member-Funktion:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `long double& val`  
  
 `) const;`  
  
 verhält sich wie das achte, außer dass die entsprechende Überprüfung Konvertierungsspezifizierer ist `Lf`.  
  
 Der neunte virtuellen geschützte Member-Funktion:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `void *& val`  
  
 `) const;`  
  
 verhält sich das erste, allerdings wird der entsprechende Scan Konvertierungsspezifizierer `p`.  
  
 Die letzte (elfte) virtuellen geschützte Member-Funktion:  
  
 `virtual iter_type do_get(`  
  
 `iter_type first,`  
  
 `iter_type last,`  
  
 `ios_base& _Iosbase,`  
  
 `ios_base::iostate& _State,`  
  
 `bool& val`  
  
 `) const;`  
  
 verhält sich wie die erste, außer dass er versucht, eine vollständige, nicht leeren booleschen Eingabefeld übereinstimmen. Wenn erfolgreiche booleschen Eingabefeld in einen Wert vom Typ konvertiert `bool` und speichert diesen Wert in `val`.  
  
 Ein boolescher Eingabefeld akzeptiert einen von zwei Formen. Wenn `iosbase.flags() & ios_base::`[Boolalpha](../Topic/%3Cios%3E%20functions.md#boolalpha) false ist, es ist identisch mit einem Eingabefeld ganze Zahl, mit der Ausnahme, dass der konvertierte Wert entweder 0 (False) oder 1 (True) sein muss. Andernfalls die Sequenz übereinstimmen entweder `fac.`[numpunct:: falsename](../standard-library/numpunct-class.md#numpunct__falsename)`()` (für False), oder `fac.`[numpunct:: TrueName](../standard-library/numpunct-class.md#numpunct__truename)`()` (für True).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [abrufen](#num_get__get), bei dem die virtuelle Memberfunktion, indem aufgerufen wird `do_get`.  
  
##  <a name="a-namenumgetgeta-numgetget"></a><a name="num_get__get"></a>  num_get:: Get  
 Extrahiert einen numerischen oder booleschen Wert aus einer Zeichenfolge.  
  
```
iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned short& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned int& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long long& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    float& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;

iter_type get(
    iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;
```  
  
### <a name="parameters"></a>Parameter  
 `first`  
 Der Anfang des Bereichs von Zeichen aus dem die Anzahl gelesen.  
  
 `last`  
 Das Ende des Bereichs von Zeichen aus dem die Anzahl gelesen.  
  
 `_Iosbase`  
 Die [Ios_base](../standard-library/ios-base-class.md) deren Flags werden durch die Konvertierung verwendet.  
  
 `_State`  
 Der Zustand, der die Failbit (finden Sie unter [ios_base:: iostate](../standard-library/ios-base-class.md#ios_base__iostate)), die bei einem Fehler hinzugefügt wird.  
  
 `val`  
 Der gelesene Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Iterator, nachdem der Wert gelesen wurde.  
  
### <a name="remarks"></a>Hinweise  
 Alle Memberfunktionen geben [Do_get](#num_get__do_get)( `first`, `last`, `_Iosbase`, `_State`, `val`).  
  
 Die erste als geschützte virtuelle Memberfunktion sequenzielle Elemente ab, die auf den ersten in der Sequenz entsprechen versucht [ `first`, `last`), bis er eine vollständige erkannt, Eingabe Integer nicht leeren Feld. Wenn erfolgreich, wird dieses Feld in den entsprechenden-Wert als Typ umgewandelt **lange** und speichert das Ergebnis in `val`. Es gibt einen Iterator, der das erste Element nach dem numerischen Eingabefeld festlegen. Andernfalls speichert die Funktion "nothing" in `val` und `ios_base::failbit` in _ *Zustand*. Es gibt einen Iterator, der das erste Element nach einem Präfix von einem Eingabefeld gültige ganze Zahl festlegen. In beiden Fällen, wenn der Rückgabewert gleich **letzten**, die Funktion legt `ios_base::eofbit` in `_State`.  
  
 Feld für die ganze Zahl konvertiert, indem die gleichen Regeln, die von der Scan-Funktionen für den Abgleich und konvertieren eine Reihe von `char` Elemente aus einer Datei. Alle diese `char` Element steht für eine entsprechende Element vom Typ zugeordnet **CharType** durch eine einfache 1: 1-Zuordnung. Die entsprechende Überprüfung Konvertierungsspezifikation wird wie folgt bestimmt:  
  
-   Wenn **Iosbase**. [Flags](../standard-library/ios-base-class.md#ios_base__flags) & `ios_base::basefield` == `ios_base::`[Okt](../Topic/%3Cios%3E%20functions.md#oct), ist die Konvertierungsspezifikation **lo**.  
  
-   Wenn **iosbase.flags** & **ios_base** == `ios_base::`[hex](../Topic/%3Cios%3E%20functions.md#hex), ist die Konvertierungsspezifikation **lx**.  
  
-   Wenn **iosbase.flags** & **ios_base** == 0 ist, wird die Konvertierungsspezifikation `li`.  
  
-   Andernfalls ist die Konvertierungsspezifikation **%ld**.  
  
 Das Format eines Eingabefelds ganze Zahl hängt darüber hinaus von der [gebietsschemafacet](../standard-library/locale-class.md#facet_class)**Fac** vom Aufruf zurückgegebene [Use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) < [Numpunct](../standard-library/numpunct-class.md)\< **Elem**> ( **Iosbase**. [Getloc](../standard-library/ios-base-class.md#ios_base__getloc)). Dies gilt insbesondere in folgenden Fällen:  
  
- **FAc**. [Gruppieren von](../standard-library/numpunct-class.md#numpunct__grouping) bestimmt, wie Ziffern auf der linken Seite des Dezimaltrennzeichens gruppiert werden.  
  
- **FAc**. [Thousands_sep](../standard-library/numpunct-class.md#numpunct__thousands_sep) bestimmt die Reihenfolge, die Zifferngruppen links vom Dezimaltrennzeichen.  
  
 Wenn keine Instanzen von **Fac**. `thousands_sep` im numerischen Eingabefeld auftreten, ist keine Gruppierung Einschränkung auferlegt werden. Andernfalls Gruppierung Einschränkungen aufgrund von **Fac**. **Gruppieren von** wird erzwungen und Trennzeichen werden entfernt, bevor die Konvertierung Scan auftritt.  
  
 Der zweite virtuelle geschützte Member-Funktion:  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    unsigned long& val) const;
```  
  
 verhält sich wie die erste, außer dass es eine Konvertierungsspezifikation von ersetzt **%ld** mit **Lu**. Wenn erfolgreich, das numerische Feld für die Eingabe in ein Wert vom Typ konvertiert `unsigned long` und speichert diesen Wert in `val`.  
  
 Die dritte virtuelle geschützter Member-Funktion:  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    double& val) const;
```  
  
 verhält sich wie die erste, außer dass er versucht, eine vollständige, nicht leeren Gleitkomma Eingabefeld übereinstimmen. **FAc**. [Decimal_point](../standard-library/numpunct-class.md#numpunct__decimal_point) bestimmt die Reihenfolge, die die ganzzahligen Ziffern von der Bruchziffern trennt. Ist die entsprechende Überprüfung Konvertierungsspezifizierer **lf**.  
  
 Der vierte virtuelle geschützte Member-Funktion:  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;
```  
  
 verhält sich die dritte, allerdings wird der entsprechende Scan Konvertierungsspezifizierer **Lf**.  
  
 Die fünfte virtuellen geschützte Member-Funktion:  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    void *& val) const;
```  
  
 verhält sich das erste, allerdings wird der entsprechende Scan Konvertierungsspezifizierer **p**.  
  
 Der sechste virtuelle geschützter Member-Funktion:  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    bool& val) const;
```  
  
 verhält sich wie die erste, außer dass er versucht, eine vollständige, nicht leeren booleschen Eingabefeld übereinstimmen. Wenn erfolgreiche booleschen Eingabefeld in einen Wert vom Typ konvertiert `bool` und speichert diesen Wert in `val`.  
  
 Ein boolescher Eingabefeld akzeptiert einen von zwei Formen. Wenn **Iosbase**. **Flags** & `ios_base::`[Boolalpha](../Topic/%3Cios%3E%20functions.md#boolalpha) ist **false**, es ist identisch mit einem Eingabefeld ganze Zahl, mit der Ausnahme, dass der konvertierte Wert 0 sein muss (für **false**) oder 1 (für **true**). Andernfalls die Sequenz übereinstimmen entweder **Fac**. [Falsename](../standard-library/numpunct-class.md#numpunct__falsename) (für **false**), oder **Fac**. [TrueName](../standard-library/numpunct-class.md#numpunct__truename) (für **true**).  
  
### <a name="example"></a>Beispiel  
  
```  
// num_get_get.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   basic_stringstream<char> psz, psz2;  
   psz << "-1000,56";  
  
   ios_base::iostate st = 0;  
   long double fVal;  
   cout << use_facet <numpunct <char> >(loc).thousands_sep( ) << endl;  
  
   psz.imbue( loc );  
   use_facet <num_get <char> >  
   (loc).get( basic_istream<char>::_Iter( psz.rdbuf( ) ),  
           basic_istream<char>::_Iter(0), psz, st, fVal );  
  
   if ( st & ios_base::failbit )  
      cout << "money_get( ) FAILED" << endl;  
   else  
      cout << "money_get( ) = " << fVal << endl;  
}  
```  
  
##  <a name="a-namenumgetitertypea-numgetitertype"></a><a name="num_get__iter_type"></a>  num_get:: iter_type  
 Ein Typ, der einen Eingabeiterator beschreibt.  
  
```
typedef InputIterator iter_type;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter **InputIterator**.  
  
##  <a name="a-namenumgetnumgeta-numgetnumget"></a><a name="num_get__num_get"></a>  num_get:: num_get  
 Der Konstruktor für Objekte vom Typ `num_get`, die verwendet werden, um numerische Werte aus Sequenzen zu extrahieren.  
  
```
explicit num_get(size_t _Refs = 0);
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
  
## <a name="see-also"></a>Siehe auch  
 [\< Gebietsschema>](../standard-library/locale.md)   
 [Facet-Klasse](../standard-library/locale-class.md#facet_class)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)



