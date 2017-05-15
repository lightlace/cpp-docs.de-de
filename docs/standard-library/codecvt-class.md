---
title: codecvt-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- codecvt
- xlocale/std::codecvt
- locale/std::codecvt::extern_type
- locale/std::codecvt::intern_type
- locale/std::codecvt::state_type
- locale/std::codecvt::always_noconv
- locale/std::codecvt::do_always_noconv
- locale/std::codecvt::do_encoding
- locale/std::codecvt::do_in
- locale/std::codecvt::do_length
- locale/std::codecvt::do_max_length
- locale/std::codecvt::do_out
- locale/std::codecvt::do_unshift
- locale/std::codecvt::encoding
- locale/std::codecvt::in
- locale/std::codecvt::length
- locale/std::codecvt::max_length
- locale/std::codecvt::out
- locale/std::codecvt::unshift
dev_langs:
- C++
helpviewer_keywords:
- codecvt class
ms.assetid: 37d3efa1-2b7f-42b6-b04f-7a972c8c2c86
caps.latest.revision: 23
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
ms.openlocfilehash: 2f96bb4a2eb577eb490b492ec425220ea5ce9eb3
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="codecvt-class"></a>codecvt-Klasse
Eine Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet dienen kann. Sie ist in der Lage, Konvertierungen zwischen einer Sequenz von Werten zu steuern, mit denen Zeichen innerhalb des Programms codiert werden, und einer Sequenz von Werten, mit denen Zeichen außerhalb des Programms codiert werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class CharType, class Byte, class StateType>  
class codecvt : public locale::facet, codecvt_base;  
```  
  
#### <a name="parameters"></a>Parameter  
 `CharType`  
 Der Typ, der innerhalb eines Programms verwendet wird, um Zeichen zu codieren.  
  
 `Byte`  
 Ein Typ, mit dem Zeichen außerhalb eines Programms codiert werden.  
  
 `StateType`  
 Ein Typ, der verwendet werden kann, um Zwischenzustände einer Konvertierung zwischen internen und externen Zeichendarstellungen darzustellen.  
  
## <a name="remarks"></a>Hinweise  
 Die Vorlagenklasse beschreibt ein Objekt, das als [Gebietsschemafacet](../standard-library/locale-class.md#facet_class) dienen kann, um Konvertierungen zwischen einer Sequenz von Werten des Typs `CharType` und einer Sequenz von Werten des Typs `Byte` zu steuern. Die `StateType`-Klasse kennzeichnet die Transformation, und ein Objekt der `StateType`-Klasse speichert alle erforderlichen Zustandsinformationen während einer Konvertierung.  
  
 Die interne Codierung verwendet eine Darstellung mit einer festen Anzahl von Byte pro Zeichen, normalerweise entweder vom Typ `char` oder vom Typ `wchar_t`.  
  
 Wie bei jedem Gebietsschemafacet hat das statische Objekt `id` einen anfänglichen gespeicherten Wert von NULL. Beim ersten Versuch, auf den gespeicherten Wert zuzugreifen, wird ein eindeutiger positiver Wert in `id` gespeichert.  
  
 Die Vorlagenversionen [do_in](#do_in) und [do_out](#do_out) geben immer `codecvt_base::noconv` zurück.  
  
 Die C++- Standardbibliothek definiert einige explizite Spezialisierungen:  
  
 `template<>`  
  
 `codecvt<wchar_t, char, mbstate_t>`  
  
 konvertiert `wchar_t`- und `char`-Sequenzen.  
  
 `template<>`  
  
 `codecvt<char16_t, char, mbstate_t>`  
  
 konvertiert `char16_t`-Sequenzen, die als UTF-16 codiert sind, und `char`-Sequenzen, die als UTF-8 codiert sind.  
  
 `template<>`  
  
 `codecvt<char32_t, char, mbstate_t>`  
  
 konvertiert `char32_t`-Sequenzen, die als UTF-32 (UCS-4) codiert sind, und `char`-Sequenzen, die als UTF-8 codiert sind.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[codecvt](#codecvt)|Der Konstruktor für Objekte der `codecvt`-Klasse, die als Gebietsschemafacet zur Behandlung von Konvertierungen dient.|  
  
### <a name="typedefs"></a>TypeDefs  
  
|||  
|-|-|  
|[extern_type](#extern_type)|Ein Zeichentyp, der für externe Darstellungen verwendet wird.|  
|[intern_type](#intern_type)|Ein Zeichentyp, der für interne Darstellungen verwendet wird.|  
|[state_type](#state_type)|Ein Zeichentyp, der verwendet wird, um Zwischenzustände bei Konvertierungen zwischen externen und internen Darstellungen darzustellen.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[always_noconv](#always_noconv)|Testet, ob keine Konvertierungen ausgeführt werden müssen.|  
|[do_always_noconv](#do_always_noconv)|Eine virtuelle Funktion, die aufgerufen wird, um zu testen, ob keine Konvertierungen ausgeführt werden müssen.|  
|[do_encoding](#do_encoding)|Eine virtuelle Funktion, die testet, ob die Codierung des `Byte`-Streams zustandsabhängig ist, ob das zwischen den verwendeten `Byte`s und den `CharType`-Objekten erstellte Verhältnis konstant ist, und die im positiven Fall den Wert dieses Verhältnisses bestimmt.|  
|[do_in](#do_in)|Eine virtuelle Funktion, die aufgerufen wird, um eine Sequenz interner `Byte`s in eine Sequenz externer `CharType`s zu konvertieren.|  
|[do_length](#do_length)|Eine virtuelle Funktion, die bestimmt, wie viele `Byte`s aus einer angegebenen Sequenz externer `Byte`s nicht mehr als eine angegebene Anzahl von `CharType`-Objekten ergibt, und die die Anzahl von `Byte`s zurückgibt.|  
|[do_max_length](#do_max_length)|Eine virtuelle Funktion, die die maximale Anzahl externer Bytes zurückgibt, die erforderlich sind, um ein internes `CharType`-Objekt zu erzeugen.|  
|[do_out](#do_out)|Eine virtuelle Funktion, die aufgerufen wird, um eine Sequenz interner `CharType`-Objekte in eine Sequenz externer Bytes zu konvertieren.|  
|[do_unshift](#do_unshift)|Eine virtuelle Funktion, die aufgerufen wird, um die `Byte`s bereitzustellen, die in einer zustandsabhängigen Konvertierung erforderlich sind, um das letzte Zeichen in einer Sequenz von `Byte`s abzuschließen.|  
|[encoding](#encoding)|Testet, ob die Codierung des `Byte`-Streams zustandsabhängig ist, ob das zwischen den verwendeten `Byte`s und den `CharType`-Objekten erstellte Verhältnis konstant ist, und bestimmt im positiven Fall den Wert dieses Verhältnisses.|  
|[in](#in)|Konvertiert eine externe Darstellung einer Sequenz von `Byte`s in eine Darstellung einer Sequenz von `CharType`-Objekten.|  
|[length](#length)|Bestimmt, wie viele `Byte`s aus einer angegebenen Sequenz externer `Byte`s nicht mehr als eine angegebene Anzahl von `CharType`-Objekten ergibt, und gibt die Anzahl von `Byte`s zurück.|  
|[max_length](#max_length)|Gibt die maximale Anzahl von externen `Byte`s zurück, die erforderlich ist, um einen internen `CharType` zu erstellen.|  
|[out](#out)|Konvertiert eine Sequenz interner `CharType`-Objekte in eine Sequenz externer `Byte`s.|  
|[unshift](#unshift)|Stellt die externen `Byte`s bereit, die in einer zustandsabhängigen Konvertierung erforderlich sind, um das letzte Zeichen der Sequenz von `Byte`s abzuschließen.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<locale>  
  
 **Namespace:** std  
  
##  <a name="always_noconv"></a> codecvt::always_noconv  
 Testet, ob keine Konvertierungen ausgeführt werden müssen.  
  
```  
bool always_noconv() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein boolescher Wert, der **TRUE** ist, wenn keine Konvertierungen ausgeführt werden müssen; bei **FALSE** muss mindestens eine Konvertierung ausgeführt werden.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [do_always_noconv](#do_always_noconv) zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// codecvt_always_noconv.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
   bool result1 = use_facet<codecvt<char, char, mbstate_t> >   
      ( loc ).always_noconv( );  
  
   if ( result1 )  
      cout << "No conversion is needed." << endl;  
   else  
      cout << "At least one conversion is required." << endl;  
  
   bool result2 = use_facet<codecvt<wchar_t, char, mbstate_t> >   
      ( loc ).always_noconv( );  
  
   if ( result2 )  
      cout << "No conversion is needed." << endl;  
   else  
      cout << "At least one conversion is required." << endl;  
}  
```  
  
```Output  
No conversion is needed.  
At least one conversion is required.  
```  
  
##  <a name="codecvt"></a> codecvt::codecvt  
 Der Konstruktor für Objekte der Klasse „codecvt“, die als Gebietsschemafacet zur Handhabung von Konvertierungen dient.  
  
```  
explicit codecvt(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `_Refs`  
 Integerwert, der zum Angeben des Speicherverwaltungstyps für das Objekt verwendet wird.  
  
### <a name="remarks"></a>Hinweise  
 Mögliche Werte für den `_Refs`-Parameter und ihre Bedeutung:  
  
-   0: Die Lebensdauer des Objekts wird von den Gebietsschemas verwaltet, in denen es enthalten ist.  
  
-   1: Die Lebensdauer des Objekts muss manuell verwaltet werden.  
  
-   \>1: Diese Werte sind nicht definiert.  
  
 Der Konstruktor initialisiert seine `locale::facet` Basisobjekt mit **Gebietsschema::**[Facet](../standard-library/locale-class.md#facet_class)(`_Refs`).  
  
##  <a name="do_always_noconv"></a> codecvt::do_always_noconv  
 Eine virtuelle Funktion, die aufgerufen wird, um zu testen, ob keine Konvertierungen ausgeführt werden müssen.  
  
```  
virtual bool do_always_noconv() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die geschützte virtuelle Memberfunktion gibt **TRUE** nur zurück, wenn bei jedem Aufruf von [do_in](#do_in) oder [do_out](#do_out) **noconv** zurückgegeben wird.  
  
 Die Vorlagenversion gibt immer **TRUE** zurück.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [always_noconv](#always_noconv), das `do_always_noconv` aufruft.  
  
##  <a name="do_encoding"></a> codecvt::do_encoding  
 Eine virtuelle Funktion, die testet, ob die Codierung des **Byte**-Streams zustandsabhängig ist und ob das Verhältnis zwischen den verwendeten **Byte**s und den erstellten **CharType**-Objekten konstant ist, und die im positiven Fall den Wert dieses Verhältnisses bestimmt.  
  
```  
virtual int do_encoding() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die geschützte virtuelle Memberfunktion gibt Folgendes zurück:  
  
-   1, wenn die Codierung von Sequenzen des Typs `extern_type` Status abhängig ist.  
  
-   0, wenn die Codierung Sequenzen von variabler Länge umfasst.  
  
- *N*, wenn die Codierung nur Sequenzen der Länge *N* umfasst.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [encoding](#encoding), mit dem `do_encoding` aufgerufen wird.  
  
##  <a name="do_in"></a> codecvt::do_in  
 Eine virtuelle Funktion, die aufgerufen wird, um eine Sequenz externer **Byte**s in eine Sequenz interner **CharType**-Objekte zu konvertieren.  
  
```  
virtual result do_in(
    StateType& _State,  
    const Byte* first1,   
    const Byte* last1,   
    const Byte*& next1,  
    CharType* first2,  
    CharType* last2,  
    CharType*& next2,) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_State`  
 Der Konvertierungszustand, der zwischen den Aufrufen der Memberfunktion beibehalten wird.  
  
 `first1`  
 Zeiger auf den Anfang der zu konvertierenden Sequenz.  
  
 `last1`  
 Zeiger auf das Ende der zu konvertierenden Sequenz.  
  
 `next1`  
 Zeiger hinter das Ende der konvertierten Sequenz auf das erste nicht konvertierte Zeichen.  
  
 `first2`  
 Zeiger auf den Anfang der konvertierten Sequenz.  
  
 `last2`  
 Zeiger auf das Ende der konvertierten Sequenz.  
  
 `next2`  
 Zeiger auf den **CharType**, der nach dem letzten konvertierten **CharType** kommt, und auf das erste unveränderte Zeichen in der Zielsequenz.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Rückgabewert, der den Erfolg, den teilweisen Erfolg oder das Fehlschlagen des Vorgangs angibt. Die Funktion gibt Folgendes zurück:  
  
- **codecvt_base::error**, wenn die Quellsequenz fehlerhaft formuliert ist.  
  
- `codecvt_base::noconv`, wenn die Funktion keine Konvertierung ausführt.  
  
- **codecvt_base::ok**, wenn die Konvertierung erfolgreich ausgeführt wird.  
  
- **codecvt_base::partial**, wenn die Quelle unzureichend ist oder das Ziel nicht groß genug ist, damit die Konvertierung erfolgreich ausgeführt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 `_State` muss den ursprünglichen Konvertierungszustand am Anfang einer neuen Quellsequenz darstellen. Die Funktion ändert bei Bedarf ihren gespeicherten Wert, um den aktuellen Zustand einer erfolgreichen Konvertierung widerzuspiegeln. Andernfalls ist der gespeicherte Wert unspezifiziert.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [in](#in), mit dem `do_in` aufgerufen wird.  
  
##  <a name="do_length"></a> codecvt::do_length  
 Eine virtuelle Funktion, die ermittelt, wie viele **Byte**s einer bestimmten Sequenz externer **Byte**s nicht mehr als eine bestimmte Anzahl interner **CharType**-Objekte ergeben, und die diese Anzahl von **Byte**s zurückgibt.  
  
```  
virtual int do_length(
    const StateType& _State,  
    const Byte* first1,   
    const Byte* last1,  
    size_t _Len2) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_State`  
 Der Konvertierungszustand, der zwischen den Aufrufen der Memberfunktion beibehalten wird.  
  
 `first1`  
 Zeiger auf den Anfang der externen Sequenz.  
  
 `last1`  
 Zeiger auf das Ende der externen Sequenz.  
  
 `_Len2`  
 Die maximale Anzahl von **Byte**s, die von der Memberfunktion zurückgegeben werden kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl, die einen Zähler der maximalen Zahl von Konvertierungen darstellt. Sie ist nicht größer als `_Len2` und wird durch die Sequenz der externen Quelle an [ `first1`, `last1`) definiert.  
  
### <a name="remarks"></a>Hinweise  
 Die geschützte virtuelle Memberfunktion ruft effektiv `do_in`( `_State`, `first1`, `last1`, `next1`, `_Buf`, `_Buf` + `_Len2`, `next2`) für `_State` (eine Zustandskopie), einen Puffer `_Buf` und die Zeiger `next1` und `next2` auf.  
  
 Anschließend gibt `next2`  -  **Buf**. Somit zählt sie die maximale Zahl von Konvertierungen, die nicht größer als `_Len2` sind und durch die Quellsequenz an [ `first1`, `last1`) definiert sind.  
  
 Die Vorlagenversion immer gibt die kleinere von `last1`  -  `first1` und `_Len2`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [length](#length), das **do_length** aufruft.  
  
##  <a name="do_max_length"></a> codecvt::do_max_length  
 Eine virtuelle Funktion, die die maximale Anzahl externer **Byte**s zurückgibt, die erforderlich sind, um ein internes **CharType**-Objekt zu erstellen.  
  
```  
virtual int do_max_length() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Anzahl von **Byte**s, die für das Erstellen eines **CharType**-Objekts erforderlich sind.  
  
### <a name="remarks"></a>Hinweise  
 Die geschützte virtuelle Memberfunktion gibt den größten zulässigen Wert zurück, der von [do_length](#do_length)( `first1`, `last1`, 1) für beliebige gültige Werte von `first1` und `last1` zurückgegeben werden kann.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [max_length](#max_length), das `do_max_length` aufruft.  
  
##  <a name="do_out"></a> codecvt::do_out  
 Eine virtuelle Funktion, die aufgerufen wird, um eine Sequenz interner **CharType**-Objekte in eine Sequenz externer **Byte**s zu konvertieren.  
  
```  
virtual result do_out(
    StateType& _State,  
    const CharType* first1,   
    const CharType* last1,  
    const CharType*& next1,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_State`  
 Der Konvertierungszustand, der zwischen den Aufrufen der Memberfunktion beibehalten wird.  
  
 `first1`  
 Zeiger auf den Anfang der zu konvertierenden Sequenz.  
  
 `last1`  
 Zeiger auf das Ende der zu konvertierenden Sequenz.  
  
 `next1`  
 Verweis auf einen Zeiger auf den ersten nicht konvertierten **CharType** nach dem letzten konvertierten **CharType**.  
  
 `first2`  
 Zeiger auf den Anfang der konvertierten Sequenz.  
  
 `last2`  
 Zeiger auf das Ende der konvertierten Sequenz.  
  
 `next2`  
 Verweis auf einen Zeiger auf das erste nicht konvertierte **Byte** nach dem letzten konvertierten **Byte**.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Funktion gibt Folgendes zurück:  
  
- **codecvt_base::error**, wenn die Quellsequenz fehlerhaft formuliert ist.  
  
- `codecvt_base::noconv`, wenn die Funktion keine Konvertierung ausführt.  
  
- **codecvt_base::ok**, wenn die Konvertierung erfolgreich ausgeführt wird.  
  
- **codecvt_base::partial**, wenn die Quelle unzureichend oder das Ziel nicht groß genug ist, damit die Konvertierung erfolgreich ausgeführt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 `_State` muss den ursprünglichen Konvertierungszustand am Anfang einer neuen Quellsequenz darstellen. Die Funktion ändert bei Bedarf ihren gespeicherten Wert, um den aktuellen Zustand einer erfolgreichen Konvertierung widerzuspiegeln. Andernfalls ist der gespeicherte Wert unspezifiziert.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [out](#out), mit dem `do_out` aufgerufen wird.  
  
##  <a name="do_unshift"></a> codecvt::do_unshift  
 Eine virtuelle Funktion, die aufgerufen wird, um die **Byte**s bereitzustellen, die in einer zustandsabhängigen Konvertierung erforderlich sind, um das letzte Zeichen in einer Sequenz von **Byte**s abzuschließen.  
  
```  
virtual result do_unshift(
    StateType& _State,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_State`  
 Der Konvertierungszustand, der zwischen den Aufrufen der Memberfunktion beibehalten wird.  
  
 `first2`  
 Zeiger auf die erste Position im Zielbereich.  
  
 `last2`  
 Zeiger auf die letzte Position im Zielbereich.  
  
 `next2`  
 Zeiger auf das erste unveränderte Element in der Zielsequenz.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Funktion gibt Folgendes zurück:  
  
- **codecvt_base::error**, wenn _ *State* einen ungültigen Zustand darstellt  
  
- `codecvt_base::noconv`, wenn die Funktion keine Konvertierung ausführt  
  
- **codecvt_base::ok**, wenn die Konvertierung erfolgreich ausgeführt wird  
  
- **codecvt_base::partial**, wenn das Ziel nicht groß genug ist, damit die Konvertierung erfolgreich ausgeführt werden kann  
  
### <a name="remarks"></a>Hinweise  
 Die geschützte virtuelle Memberfunktion versucht, das Quellelement **CharType**(0) in eine Zielsequenz zu konvertieren, die sie in [ `first2`, `last2`) speichert, ausgenommen das abschließende Element **Byte**(0). Sie speichert in `next2` stets einen Zeiger auf das erste unveränderte Element in der Zielsequenz.  
  
 _ *State* muss den ursprünglichen Konvertierungszustand am Anfang einer neuen Quellsequenz darstellen. Die Funktion ändert bei Bedarf ihren gespeicherten Wert, um den aktuellen Zustand einer erfolgreichen Konvertierung widerzuspiegeln. In der Regel bleibt beim Konvertieren des Quellelements **CharType**(0) als aktueller Zustand der ursprüngliche Konvertierungszustand erhalten.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [unshift](#unshift), mit dem `do_unshift` aufgerufen wird.  
  
##  <a name="encoding"></a> codecvt::encoding  
 Testet, ob die Codierung des **Byte**-Streams zustandsabhängig ist und ob das Verhältnis zwischen den verwendeten **Byte**s und den generierten **CharType**-Objekten konstant ist, und ermittelt im positiven Fall den Wert dieses Verhältnisses.  
  
```  
int encoding() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der Rückgabewert positiv ist, entspricht dieser Wert der konstanten Zahl von **Byte**-Zeichen, die zum Generieren des **CharType**-Zeichens erforderlich sind.  
  
 Die geschützte virtuelle Memberfunktion gibt Folgendes zurück:  
  
-   1, wenn die Codierung von Sequenzen des Typs `extern_type` Status abhängig ist.  
  
-   0, wenn die Codierung Sequenzen von variabler Länge umfasst.  
  
- *N*, wenn die Codierung nur Sequenzen der Länge *N* umfasst.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [do_encoding](#do_encoding) zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// codecvt_encoding.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
   int result1 = use_facet<codecvt<char, char, mbstate_t> > ( loc ).encoding ( );  
   cout << result1 << endl;  
   result1 = use_facet<codecvt<wchar_t, char, mbstate_t> > ( loc ).encoding( );  
   cout << result1 << endl;  
   result1 = use_facet<codecvt<char, wchar_t, mbstate_t> > ( loc ).encoding( );  
   cout << result1 << endl;  
}  
```  
  
```Output  
1  
1  
1  
```  
  
##  <a name="extern_type"></a> codecvt::extern_type  
 Ein Zeichentyp, der für externe Darstellungen verwendet wird.  
  
```  
typedef Byte extern_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter **Byte**.  
  
##  <a name="in"></a> codecvt::in  
 Konvertiert eine externe Darstellung einer Sequenz von **Byte**s in eine interne Darstellung einer Sequenz von **CharType**-Objekten.  
  
```  
result in(
    StateType& _State,  
    const Byte* first1,   
    const Byte* last1,   
    const Byte*& next1,  
    CharType* first2,  
    CharType* last2,  
    CharType*& next2,) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_State`  
 Der Konvertierungszustand, der zwischen den Aufrufen der Memberfunktion beibehalten wird.  
  
 `first1`  
 Zeiger auf den Anfang der zu konvertierenden Sequenz.  
  
 `last1`  
 Zeiger auf das Ende der zu konvertierenden Sequenz.  
  
 `next1`  
 Zeiger hinter das Ende der konvertierten Sequenz auf das erste nicht konvertierte Zeichen.  
  
 `first2`  
 Zeiger auf den Anfang der konvertierten Sequenz.  
  
 `last2`  
 Zeiger auf das Ende der konvertierten Sequenz.  
  
 `next2`  
 Zeiger auf den **CharType**, der nach dem letzten konvertierten **CharType** kommt, und auf das erste unveränderte Zeichen in der Zielsequenz.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Rückgabewert, der den Erfolg, den teilweisen Erfolg oder das Fehlschlagen des Vorgangs angibt. Die Funktion gibt Folgendes zurück:  
  
- **codecvt_base::error**, wenn die Quellsequenz fehlerhaft formuliert ist.  
  
- `codecvt_base::noconv`, wenn die Funktion keine Konvertierung ausführt.  
  
- **codecvt_base::ok**, wenn die Konvertierung erfolgreich ausgeführt wird.  
  
- **codecvt_base::partial**, wenn die Quelle unzureichend oder das Ziel nicht groß genug ist, damit die Konvertierung erfolgreich ausgeführt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 `_State` muss den ursprünglichen Konvertierungszustand am Anfang einer neuen Quellsequenz darstellen. Die Funktion ändert bei Bedarf ihren gespeicherten Wert, um den aktuellen Zustand einer erfolgreichen Konvertierung widerzuspiegeln. Nach einer teilweisen Konvertierung muss `_State` so festgelegt werden, dass die Konvertierung beim Eintreffen neuer Zeichen fortgesetzt werden kann.  
  
 Die Memberfunktion gibt [do_in](#do_in)( `_State`, _ *First1,  last1,  next1, First2, _Llast2,  next2*) zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// codecvt_in.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
using namespace std;  
#define LEN 90  
int main( )     
{  
   char* pszExt = "This is the string to be converted!";  
   wchar_t pwszInt [LEN+1];  
   memset(&pwszInt[0], 0, (sizeof(wchar_t))*(LEN+1));  
   const char* pszNext;  
   wchar_t* pwszNext;  
   mbstate_t state = {0};  
   locale loc("C");//English_Britain");//German_Germany  
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >  
     ( loc ).in( state,  
          pszExt, &pszExt[strlen(pszExt)], pszNext,  
          pwszInt, &pwszInt[strlen(pszExt)], pwszNext );  
   pwszInt[strlen(pszExt)] = 0;  
   wcout << ( (res!=codecvt_base::error)  L"It worked! " : L"It didn't work! " )  
   << L"The converted string is:\n ["  
   << &pwszInt[0]  
   << L"]" << endl;  
   exit(-1);  
}  
```  
  
```Output  
It worked! The converted string is:  
 [This is the string to be converted!]  
```  
  
##  <a name="intern_type"></a> codecvt::intern_type  
 Ein Zeichentyp, der für interne Darstellungen verwendet wird.  
  
```  
typedef CharType intern_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter **CharType**.  
  
##  <a name="length"></a> codecvt::length  
 Bestimmt, wie viele **Byte**s einer bestimmten Sequenz externer **Byte**s nicht mehr als eine bestimmte Anzahl von **CharType**-Objekten ergeben, und gibt die Anzahl dieser **Byte**s zurück.  
  
```  
int length(
    const StateType& _State,  
    const Byte* first1,   
    const Byte* last1,  
    size_t _Len2) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_State`  
 Der Konvertierungszustand, der zwischen den Aufrufen der Memberfunktion beibehalten wird.  
  
 `first1`  
 Zeiger auf den Anfang der externen Sequenz.  
  
 `last1`  
 Zeiger auf das Ende der externen Sequenz.  
  
 `_Len2`  
 Die maximale Anzahl von Bytes, die von der Memberfunktion zurückgegeben werden kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl, die einen Zähler der maximalen Zahl von Konvertierungen darstellt. Sie ist nicht größer als `_Len2` und wird durch die Sequenz der externen Quelle an [ `first1`, `last1`) definiert.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [do_length](#do_length)( *_State,  first1*, `last1`, `_Len2`) zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// codecvt_length.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
using namespace std;  
#define LEN 90  
int main( )     
{  
   char* pszExt = "This is the string whose length is to be measured!";  
   mbstate_t state = {0};  
   locale loc("C");//English_Britain");//German_Germany  
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >  
     ( loc ).length( state,  
          pszExt, &pszExt[strlen(pszExt)], LEN );  
   cout << "The length of the string is: ";  
   wcout << res;  
   cout << "." << endl;  
   exit(-1);  
}  
```  
  
```Output  
The length of the string is: 50.  
```  
  
##  <a name="max_length"></a> codecvt::max_length  
 Gibt die maximale Anzahl von externen **Byte**s zurück, die erforderlich sind, um ein internes **CharType**-Objekt zu erstellen.  
  
```  
int max_length() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Anzahl von **Byte**s, die für das Erstellen eines **CharType**-Objekts erforderlich sind.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [do_max_length](#do_max_length) zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// codecvt_max_length.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc( "C");//English_Britain" );//German_Germany  
   int res = use_facet<codecvt<char, char, mbstate_t> >  
     ( loc ).max_length( );  
   wcout << res << endl;  
}  
```  
  
```Output  
1  
```  
  
##  <a name="out"></a> codecvt::out  
 Konvertiert eine Sequenz interner **CharType**-Objekte in eine Sequenz externer **Byte**s.  
  
```  
result out(
    StateType& _State,  
    const CharType* first1,   
    const CharType* last1,  
    const CharType*& next1,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_State`  
 Der Konvertierungszustand, der zwischen den Aufrufen der Memberfunktion beibehalten wird.  
  
 `first1`  
 Zeiger auf den Anfang der zu konvertierenden Sequenz.  
  
 `last1`  
 Zeiger auf das Ende der zu konvertierenden Sequenz.  
  
 `next1`  
 Verweis auf einen Zeiger auf den ersten nicht konvertierten **CharType** nach dem letzten konvertierten **CharType**.  
  
 `first2`  
 Zeiger auf den Anfang der konvertierten Sequenz.  
  
 `last2`  
 Zeiger auf das Ende der konvertierten Sequenz.  
  
 `next2`  
 Verweis auf einen Zeiger auf das erste nicht konvertierte **Byte** nach dem letzten konvertierten **Byte**.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Memberfunktion gibt [do_out](#do_out)( `_State`, `first1`, `last1`, `next1`, `first2`, `last2`, `next2`) zurück.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [codecvt::do_out](#do_out).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// codecvt_out.cpp  
// compile with: /EHsc  
#define _INTL  
#include <locale>  
#include <iostream>  
#include <wchar.h>  
using namespace std;  
#define LEN 90  
int main( )     
{  
   char pszExt[LEN+1];  
   wchar_t *pwszInt = L"This is the wchar_t string to be converted.";  
   memset( &pszExt[0], 0, ( sizeof( char ) )*( LEN+1 ) );  
   char* pszNext;  
   const wchar_t* pwszNext;  
   mbstate_t state;  
   locale loc("C");//English_Britain");//German_Germany  
   int res = use_facet<codecvt<wchar_t, char, mbstate_t> >  
      ( loc ).out( state,  
      pwszInt, &pwszInt[wcslen( pwszInt )], pwszNext ,  
      pszExt, &pszExt[wcslen( pwszInt )], pszNext );  
   pszExt[wcslen( pwszInt )] = 0;  
   cout << ( ( res!=codecvt_base::error )  "It worked: " : "It didn't work: " )  
   << "The converted string is:\n ["  
   << &pszExt[0]  
   << "]" << endl;  
}  
```  
  
```Output  
It worked: The converted string is:  
 [This is the wchar_t string to be converted.]  
```  
  
##  <a name="state_type"></a> codecvt::state_type  
 Ein Zeichentyp, der verwendet wird, um Zwischenzustände bei Konvertierungen zwischen externen und internen Darstellungen darzustellen.  
  
```  
typedef StateType state_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter **StateType**.  
  
##  <a name="unshift"></a> codecvt::unshift  
 Stellt die **Byte**s bereit, die in einer zustandsabhängigen Konvertierung erforderlich sind, um das letzte Zeichen in einer Sequenz von **Byte**s abzuschließen.  
  
```  
result unshift(
    StateType& _State,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_State`  
 Der Konvertierungszustand, der zwischen den Aufrufen der Memberfunktion beibehalten wird.  
  
 `first2`  
 Zeiger auf die erste Position im Zielbereich.  
  
 `last2`  
 Zeiger auf die letzte Position im Zielbereich.  
  
 `next2`  
 Zeiger auf das erste unveränderte Element in der Zielsequenz.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Funktion gibt Folgendes zurück:  
  
- **codecvt_base::error**, wenn der Zustand ein ungültiger Zustand ist.  
  
- `codecvt_base::noconv`, wenn die Funktion keine Konvertierung ausführt.  
  
- **codecvt_base::ok**, wenn die Konvertierung erfolgreich ausgeführt wird.  
  
- **codecvt_base::partial** wenn das Ziel nicht groß genug ist, damit die Konvertierung erfolgreich ausgeführt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Die geschützte virtuelle Memberfunktion versucht, das Quellelement **CharType**(0) in eine Zielsequenz zu konvertieren, die sie in [ `first2`, `last2`) speichert, ausgenommen das abschließende Element **Byte**(0). Sie speichert in `next2` stets einen Zeiger auf das erste unveränderte Element in der Zielsequenz.  
  
 `_State` muss den ursprünglichen Konvertierungszustand am Anfang einer neuen Quellsequenz darstellen. Die Funktion ändert bei Bedarf ihren gespeicherten Wert, um den aktuellen Zustand einer erfolgreichen Konvertierung widerzuspiegeln. In der Regel bleibt beim Konvertieren des Quellelements **CharType**(0) als aktueller Zustand der ursprüngliche Konvertierungszustand erhalten.  
  
 Die Memberfunktion gibt [do_unshift](#do_unshift)( `_State`, `first2`, `last2`, `next2` ) zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [\<locale>](../standard-library/locale.md)   
 [Codepages](../c-runtime-library/code-pages.md)   
 [Gebietsschema-Namen, Sprachen und Zeichenfolgen für Länder und Regionen](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)


