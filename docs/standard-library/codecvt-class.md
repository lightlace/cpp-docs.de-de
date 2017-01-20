---
title: "codecvt-Klasse"
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
  - "codecvt"
  - "std::codecvt"
  - "std.codecvt"
  - "xlocale/std::codecvt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt-Klasse"
ms.assetid: 37d3efa1-2b7f-42b6-b04f-7a972c8c2c86
caps.latest.revision: 23
caps.handback.revision: "23"
ms.author: "corob"
manager: "ghogen"
---
# codecvt-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

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
 Die Vorlagenklasse beschreibt ein Objekt, das als dienen kann eine [gebietsschemafacet](../standard-library/locale-class.md#facet_class), Konvertierungen zwischen einer Sequenz von Werten des Typs steuern `CharType` und eine Sequenz von Werten des Typs `Byte`. Die `StateType`-Klasse kennzeichnet die Transformation, und ein Objekt der `StateType`-Klasse speichert alle erforderlichen Zustandsinformationen während einer Konvertierung.  
  
 Die interne Codierung verwendet eine Darstellung mit einer festen Anzahl von Byte pro Zeichen, normalerweise entweder vom Typ `char` oder vom Typ `wchar_t`.  
  
 Wie bei jedem Gebietsschemafacet hat das statische Objekt `id` einen anfänglichen gespeicherten Wert von NULL. Beim erste Versuch, den gespeicherten Wert zuzugreifen speichert einen eindeutigen positiven Wert in `id`.  
  
 Die Vorlagenversionen von [Do_in](#codecvt__do_in) und [Do_out](#codecvt__do_out) jederzeit `codecvt_base::noconv`.  
  
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
|[codecvt](#codecvt__codecvt)|Der Konstruktor für Objekte der `codecvt`-Klasse, die als Gebietsschemafacet zur Behandlung von Konvertierungen dient.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[extern_type](#codecvt__extern_type)|Ein Zeichentyp, der für externe Darstellungen verwendet wird.|  
|[intern_type](#codecvt__intern_type)|Ein Zeichentyp, der für interne Darstellungen verwendet wird.|  
|[state_type](#codecvt__state_type)|Ein Zeichentyp, der verwendet wird, um Zwischenzustände bei Konvertierungen zwischen externen und internen Darstellungen darzustellen.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[always_noconv](#codecvt__always_noconv)|Testet, ob keine Konvertierungen ausgeführt werden müssen.|  
|[do_always_noconv](#codecvt__do_always_noconv)|Eine virtuelle Funktion, die aufgerufen wird, um zu testen, ob keine Konvertierungen ausgeführt werden müssen.|  
|[do_encoding](#codecvt__do_encoding)|Eine virtuelle Funktion, die testet, ob die Codierung des `Byte`-Streams zustandsabhängig ist, ob das zwischen den verwendeten `Byte`s und den `CharType`-Objekten erstellte Verhältnis konstant ist, und die im positiven Fall den Wert dieses Verhältnisses bestimmt.|  
|[do_in](#codecvt__do_in)|Eine virtuelle Funktion, die aufgerufen wird, um eine Sequenz interner `Byte`s in eine Sequenz externer `CharType`s zu konvertieren.|  
|[do_length](#codecvt__do_length)|Eine virtuelle Funktion, die bestimmt, wie viele `Byte`s aus einer angegebenen Sequenz externer `Byte`s nicht mehr als eine angegebene Anzahl von `CharType`-Objekten ergibt, und die die Anzahl von `Byte`s zurückgibt.|  
|[do_max_length](#codecvt__do_max_length)|Eine virtuelle Funktion, die die maximale Anzahl externer Bytes zurückgibt, die erforderlich sind, um ein internes `CharType`-Objekt zu erzeugen.|  
|[do_out](#codecvt__do_out)|Eine virtuelle Funktion, die aufgerufen wird, um eine Sequenz interner `CharType`-Objekte in eine Sequenz externer Bytes zu konvertieren.|  
|[do_unshift](#codecvt__do_unshift)|Eine virtuelle Funktion, die aufgerufen wird, um die `Byte`s bereitzustellen, die in einer zustandsabhängigen Konvertierung erforderlich sind, um das letzte Zeichen in einer Sequenz von `Byte`s abzuschließen.|  
|[Codierung](#codecvt__encoding)|Testet, ob die Codierung des `Byte`-Streams zustandsabhängig ist, ob das zwischen den verwendeten `Byte`s und den `CharType`-Objekten erstellte Verhältnis konstant ist, und bestimmt im positiven Fall den Wert dieses Verhältnisses.|  
|[in](#codecvt__in)|Konvertiert eine externe Darstellung einer Sequenz von `Byte`s in eine Darstellung einer Sequenz von `CharType`-Objekten.|  
|[Länge](#codecvt__length)|Bestimmt, wie viele `Byte`s aus einer angegebenen Sequenz externer `Byte`s nicht mehr als eine angegebene Anzahl von `CharType`-Objekten ergibt, und gibt die Anzahl von `Byte`s zurück.|  
|[max_length](#codecvt__max_length)|Gibt die maximale Anzahl von externen `Byte`s zurück, die erforderlich ist, um einen internen `CharType` zu erstellen.|  
|[Out](#codecvt__out)|Konvertiert eine Sequenz interner `CharType`-Objekte in eine Sequenz externer `Byte`s.|  
|[unshift](#codecvt__unshift)|Stellt die externen `Byte`s bereit, die in einer zustandsabhängigen Konvertierung erforderlich sind, um das letzte Zeichen der Sequenz von `Byte`s abzuschließen.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \< Gebietsschema>  
  
 **Namespace:** std  
  
##  <a name="a-namecodecvtalwaysnoconva-codecvtalwaysnoconv"></a><a name="codecvt__always_noconv"></a>  codecvt:: always_noconv  
 Testet, ob keine Konvertierungen ausgeführt werden müssen.  
  
```  
bool always_noconv() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein boolescher Wert, der **true** wenn keine Konvertierung ausgeführt werden müssen; **false** ist mindestens eine ausgeführt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [Do_always_noconv](#codecvt__do_always_noconv).  
  
### <a name="example"></a>Beispiel  
  
```  
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
  
##  <a name="a-namecodecvtcodecvta-codecvtcodecvt"></a><a name="codecvt__codecvt"></a>  codecvt:: codecvt  
 Der Konstruktor für Objekte der Klasse Codecvt, das als gebietsschemafacet zur Behandlung von Konvertierungen dient.  
  
```  
explicit codecvt(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `_Refs`  
 Integer-Wert verwendet, um den Typ der Verwaltung des Arbeitsspeichers für das Objekt angeben.  
  
### <a name="remarks"></a>Hinweise  
 Die möglichen Werte für die `_Refs` Parameter und ihre Bedeutung sind:  
  
-   0: die Lebensdauer des Objekts wird von der Gebietsschemas, die es enthalten verwaltet.  
  
-   1: die Lebensdauer des Objekts manuell verwaltet werden muss.  
  
-   \> 0: Diese Werte sind nicht definiert.  
  
 Der Konstruktor initialisiert die `locale::facet` Basisobjekt mit **Gebietsschema::**[Facet](../standard-library/locale-class.md#facet_class)( `_Refs`) *.*  
  
##  <a name="a-namecodecvtdoalwaysnoconva-codecvtdoalwaysnoconv"></a><a name="codecvt__do_always_noconv"></a>  codecvt:: do_always_noconv  
 Eine virtuelle Funktion, die aufgerufen wird, um zu testen, ob keine Konvertierungen ausgeführt werden müssen.  
  
```  
virtual bool do_always_noconv() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Geschützte virtuelle Memberfunktion gibt **true** nur bei jedem Aufruf von [Do_in](#codecvt__do_in) oder [Do_out](#codecvt__do_out) gibt **Noconv**.  
  
 Die Vorlagenversion immer zurück **true**.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Always_noconv](#codecvt__always_noconv), welche `do_always_noconv`.  
  
##  <a name="a-namecodecvtdoencodinga-codecvtdoencoding"></a><a name="codecvt__do_encoding"></a>  codecvt:: do_encoding  
 Eine virtuelle Funktion, die überprüft, wenn die Codierung des der **Byte** Stream ist, ob das Verhältnis zwischen der **Byte**s verwendet und die **CharType**s erzeugten konstant ist, und wenn dies der Fall ist, bestimmt der Wert dieses Verhältnisses.  
  
```  
virtual int do_encoding() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die geschützte virtuelle Memberfunktion gibt zurück:  
  
-   -1, wenn die Codierung von Sequenzen des Typs `extern_type` Status abhängig ist.  
  
-   0, wenn bei der Codierung Sequenzen von variabler Länge.  
  
- *N*, wenn die Codierung nur Sequenzen Länge umfasst *N*  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Codierung](#codecvt__encoding), welche `do_encoding`.  
  
##  <a name="a-namecodecvtdoina-codecvtdoin"></a><a name="codecvt__do_in"></a>  codecvt:: do_in  
 Eine virtuelle Funktion aufgerufen wird, um eine Sequenz externer konvertieren **Byte**s, um eine Sequenz interner **CharType**s.  
  
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
 Der Status der Konvertierung, der zwischen den Aufrufen der Memberfunktion verwaltet wird.  
  
 ` first1`  
 Zeiger auf den Anfang der Sequenz konvertiert werden.  
  
 ` last1`  
 Ein Zeiger auf das Ende der Sequenz konvertiert werden.  
  
 ` next1`  
 Zeiger hinter dem Ende der Sequenz konvertierte zum ersten Zeichens.  
  
 ` first2`  
 Zeiger auf den Anfang der Sequenz konvertiert.  
  
 ` last2`  
 Ein Zeiger auf das Ende der konvertierten Sequenz.  
  
 ` next2`  
 Zeiger auf die **CharType** die nach der letzten konvertiert stammt **CharType**, zum ersten Zeichen unverändert in der Ziel-Sequenz.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Rückgabewert, der den Erfolg, teilweise erfolgreich oder Fehler des Vorgangs angibt. Die Funktion gibt zurück:  
  
- **codecvt_base::Error** gebildet, wenn die Quellsequenz krank ist.  
  
- `codecvt_base::noconv` Wenn die Funktion keine Konvertierung durchführt.  
  
- **codecvt_base::OK** wenn die Konvertierung erfolgreich ist.  
  
- **codecvt_base::partial** wenn die Quelle nicht ausreicht oder das Ziel nicht groß genug ist, damit die Konvertierung erfolgreich ist.  
  
### <a name="remarks"></a>Hinweise  
 `_State` muss der ursprüngliche konvertierungszustand am Anfang einer neuen Quelle Sequenz darstellen. Die Funktion ändert den gespeicherten Wert, um den aktuellen Zustand für eine erfolgreiche Konvertierung. Der gespeicherte Wert ist andernfalls nicht angegeben.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [in](#codecvt__in), welche `do_in`.  
  
##  <a name="a-namecodecvtdolengtha-codecvtdolength"></a><a name="codecvt__do_length"></a>  codecvt:: do_length  
 Eine virtuelle Funktion, die bestimmt, wie viele **Byte**s aus einer angegebenen Sequenz externer **Byte**s erzeugen, die nicht mehr als eine angegebene Anzahl von internen **CharType**s und gibt die Anzahl von **Byte**s.  
  
```  
virtual int do_length(
    const StateType& _State,  
    const Byte* first1,   
    const Byte* last1,  
    size_t _Len2) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_State`  
 Der Status der Konvertierung, der zwischen den Aufrufen der Memberfunktion verwaltet wird.  
  
 ` first1`  
 Zeiger auf den Anfang der externen Sequenz.  
  
 ` last1`  
 Ein Zeiger auf das Ende der externen Sequenz.  
  
 `_Len2`  
 Die maximale Anzahl von **Byte**s, die von der Memberfunktion zurückgegeben werden kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl, die für die maximale Anzahl von Konvertierungen, die nicht größer als `_Len2`, definiert durch die Reihenfolge der externen Quelle an [ ` first1`, ` last1`).  
  
### <a name="remarks"></a>Hinweise  
 Ruft die geschützte virtuelle Memberfunktion `do_in`( `_State`, ` first1`, ` last1`, ` next1`, `_Buf`, `_Buf` + `_Len2`, ` next2`) für `_State` (eine Kopie des Zustands), einem Puffer `_Buf`, und Zeiger ` next1`und ` next2`.  
  
 Es gibt dann zurück ` next2` – **Buf**. Daher zählt es die maximale Anzahl von Konvertierungen, die nicht größer als `_Len2`, definiert durch die Quellsequenz am [ ` first1`, ` last1`).  
  
 Die Vorlagenversion immer gibt die kleinere von ` last1` – ` first1` und `_Len2`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Länge](#codecvt__length), welche **Do_length**.  
  
##  <a name="a-namecodecvtdomaxlengtha-codecvtdomaxlength"></a><a name="codecvt__do_max_length"></a>  codecvt:: do_max_length  
 Eine virtuelle Funktion, die die maximale Anzahl von externen zurückgibt **Byte**s einen internen Herstellung **CharType**.  
  
```  
virtual int do_max_length() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Anzahl von **Byte**s eine Herstellung **CharType**.  
  
### <a name="remarks"></a>Hinweise  
 Die geschützte virtuelle Memberfunktion größten zulässigen Wert zurück, der von zurückgegeben werden kann [Do_length](#codecvt__do_length)( ` first1`, ` last1`, 1) für beliebige gültige Werte von ` first1` und ` last1`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [Max_length](#codecvt__max_length), welche `do_max_length`.  
  
##  <a name="a-namecodecvtdoouta-codecvtdoout"></a><a name="codecvt__do_out"></a>  codecvt:: do_out  
 Eine virtuelle Funktion aufgerufen wird, um eine Sequenz interner konvertieren **CharType**s, um eine Sequenz externer **Byte**s.  
  
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
 Der Status der Konvertierung, der zwischen den Aufrufen der Memberfunktion verwaltet wird.  
  
 ` first1`  
 Zeiger auf den Anfang der Sequenz konvertiert werden.  
  
 ` last1`  
 Ein Zeiger auf das Ende der Sequenz konvertiert werden.  
  
 ` next1`  
 Verweis auf einen Zeiger auf das erste nicht konvertiert **CharType**, nachdem die letzte **CharType** konvertiert.  
  
 ` first2`  
 Zeiger auf den Anfang der Sequenz konvertiert.  
  
 ` last2`  
 Ein Zeiger auf das Ende der konvertierten Sequenz.  
  
 ` next2`  
 Verweis auf einen Zeiger auf das erste nicht konvertiert **Byte**, nach dem letzten **Byte** konvertiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Funktion gibt zurück:  
  
- **codecvt_base::Error** gebildet, wenn die Quellsequenz krank ist.  
  
- `codecvt_base::noconv` Wenn die Funktion keine Konvertierung durchführt.  
  
- **codecvt_base::OK** wenn die Konvertierung erfolgreich ist.  
  
- **codecvt_base::partial** wenn die Quelle nicht ausreicht oder das Ziel nicht groß genug ist, damit die Konvertierung erfolgreich ist.  
  
### <a name="remarks"></a>Hinweise  
 `_State` muss der ursprüngliche konvertierungszustand am Anfang einer neuen Quelle Sequenz darstellen. Die Funktion ändert den gespeicherten Wert, um den aktuellen Zustand für eine erfolgreiche Konvertierung. Der gespeicherte Wert ist andernfalls nicht angegeben.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [](#codecvt__out), welche `do_out`.  
  
##  <a name="a-namecodecvtdounshifta-codecvtdounshift"></a><a name="codecvt__do_unshift"></a>  codecvt:: do_unshift  
 Eine virtuelle Funktion aufgerufen wird, zu der **Byte**s in einer zustandsabhängigen Konvertierung benötigt werden, um das letzte Zeichen in einer Sequenz von abzuschließen **Byte**s.  
  
```  
virtual result do_unshift(
    StateType& _State,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_State`  
 Der Status der Konvertierung, der zwischen den Aufrufen der Memberfunktion verwaltet wird.  
  
 ` first2`  
 Ein Zeiger auf die erste Position im Zielbereich.  
  
 ` last2`  
 Ein Zeiger auf die letzte Position im Zielbereich.  
  
 ` next2`  
 Ein Zeiger auf das erste unverändert Element in der Ziel-Sequenz.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Funktion gibt zurück:  
  
- **codecvt_base::Error** Wenn _ *Zustand* stellt einen ungültigen Status  
  
- `codecvt_base::noconv` Wenn die Funktion keine Konvertierung ausführt.  
  
- **codecvt_base::OK** ist die Konvertierung erfolgreich  
  
- **codecvt_base::partial** wenn das Ziel nicht groß genug ist, damit die Konvertierung erfolgreich ist.  
  
### <a name="remarks"></a>Hinweise  
 Die geschützte virtuelle Memberfunktion wird versucht, das Quellelement konvertieren **CharType**(0) in eine Ziel-Sequenz, die sie in speichert [ ` first2`, ` last2`), außer das abschließende Element **Byte**(0). Er speichert immer in ` next2` einen Zeiger auf das erste unverändert Element in der Ziel-Sequenz.  
  
 _ *Zustand* muss der ursprüngliche konvertierungszustand am Anfang einer neuen Quelle Sequenz darstellen. Die Funktion ändert den gespeicherten Wert, um den aktuellen Zustand für eine erfolgreiche Konvertierung. In der Regel konvertieren das Quellelement **CharType**(0) bewirkt, dass den aktuellen Zustand der ersten Konvertierung.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [unshift](#codecvt__unshift), welche `do_unshift`.  
  
##  <a name="a-namecodecvtencodinga-codecvtencoding"></a><a name="codecvt__encoding"></a>  codecvt:: Encoding  
 Testet, ob die Codierung des der **Byte** Stream ist, ob das Verhältnis zwischen der **Byte**s verwendet und die **CharType**s erzeugten konstant, und wenn dies der Fall ist, bestimmt der Wert dieses Verhältnisses.  
  
```  
int encoding() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn der zurückgegebene Wert positiv ist, und klicken Sie dann der Wert gleich bleibenden Anzahl von ist **Byte** Zeichen, die zur Erstellung der **CharType** Zeichen.  
  
 Die geschützte virtuelle Memberfunktion gibt zurück:  
  
-   -1, wenn die Codierung von Sequenzen des Typs `extern_type` Status abhängig ist.  
  
-   0, wenn bei der Codierung Sequenzen von variabler Länge.  
  
- *N*, wenn die Codierung nur Sequenzen Länge umfasst *N.*  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [Do_encoding](#codecvt__do_encoding).  
  
### <a name="example"></a>Beispiel  
  
```  
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
  
##  <a name="a-namecodecvtexterntypea-codecvtexterntype"></a><a name="codecvt__extern_type"></a>  codecvt:: extern_type  
 Ein Zeichentyp, der für externe Darstellungen verwendet wird.  
  
```  
typedef Byte extern_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter **Byte**.  
  
##  <a name="a-namecodecvtina-codecvtin"></a><a name="codecvt__in"></a>  codecvt:: in  
 Konvertiert eine externe Darstellung einer Sequenz von **Byte**s, um eine interne Darstellung einer Sequenz von **CharType**s.  
  
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
 Der Status der Konvertierung, der zwischen den Aufrufen der Memberfunktion verwaltet wird.  
  
 ` first1`  
 Zeiger auf den Anfang der Sequenz konvertiert werden.  
  
 ` last1`  
 Ein Zeiger auf das Ende der Sequenz konvertiert werden.  
  
 ` next1`  
 Der Zeiger nach dem Ende des ersten Zeichens der konvertierten Sequenz.  
  
 ` first2`  
 Zeiger auf den Anfang der Sequenz konvertiert.  
  
 ` last2`  
 Ein Zeiger auf das Ende der konvertierten Sequenz.  
  
 ` next2`  
 Zeiger auf die **CharType** die nach der letzten konvertiert stammt **Chartype** zum ersten Zeichen unverändert in der Ziel-Sequenz.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Rückgabewert, der Erfolg, teilweise erfolgreich oder Fehler des Vorgangs angibt. Die Funktion gibt zurück:  
  
- **codecvt_base::Error** gebildet, wenn die Quellsequenz krank ist.  
  
- `codecvt_base::noconv` Wenn die Funktion keine Konvertierung durchführt.  
  
- **codecvt_base::OK** wenn die Konvertierung erfolgreich ist.  
  
- **codecvt_base::partial** wenn die Quelle nicht ausreicht oder das Ziel nicht groß genug ist, damit die Konvertierung erfolgreich ist.  
  
### <a name="remarks"></a>Hinweise  
 `_State` muss der ursprüngliche konvertierungszustand am Anfang einer neuen Quelle Sequenz darstellen. Die Funktion ändert den gespeicherten Wert, bei Bedarf auf dem aktuellen Zustand für eine erfolgreiche Konvertierung. Nach einer teilweisen Konvertierung `_State` muss festgelegt werden, um die Konvertierung fortsetzen beim Eintreffen neuer Zeichen zu ermöglichen.  
  
 Die Memberfunktion gibt [Do_in](#codecvt__do_in)( `_State`, _ *First1, last1, next1, First2, _Llast2, next2*).  
  
### <a name="example"></a>Beispiel  
  
```  
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
  
##  <a name="a-namecodecvtinterntypea-codecvtinterntype"></a><a name="codecvt__intern_type"></a>  codecvt:: intern_type  
 Ein Zeichentyp, der für interne Darstellungen verwendet wird.  
  
```  
typedef CharType intern_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter **CharType**.  
  
##  <a name="a-namecodecvtlengtha-codecvtlength"></a><a name="codecvt__length"></a>  codecvt:: Length  
 Bestimmt, wie viele **Byte**s aus einer angegebenen Sequenz externer **Byte**s erzeugen, die nicht mehr als eine angegebene Anzahl von internen **CharType**s und gibt die Anzahl von **Byte**s.  
  
```  
int length(
    const StateType& _State,  
    const Byte* first1,   
    const Byte* last1,  
    size_t _Len2) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_State`  
 Der Status der Konvertierung, der zwischen den Aufrufen der Memberfunktion verwaltet wird.  
  
 ` first1`  
 Zeiger auf den Anfang der externen Sequenz.  
  
 ` last1`  
 Ein Zeiger auf das Ende der externen Sequenz.  
  
 `_Len2`  
 Die maximale Anzahl von Bytes, die von der Memberfunktion zurückgegeben werden können.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl, die für die maximale Anzahl von Konvertierungen, die nicht größer als `_Len2`, definiert durch die Reihenfolge der externen Quelle an [ ` first1`, ` last1`).  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [Do_length](#codecvt__do_length)( *_State, first1*, ` last1`, `_Len2`).  
  
### <a name="example"></a>Beispiel  
  
```  
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
  
##  <a name="a-namecodecvtmaxlengtha-codecvtmaxlength"></a><a name="codecvt__max_length"></a>  codecvt:: max_length  
 Gibt die maximale Anzahl von externen **Byte**s einen internen Herstellung **CharType**.  
  
```  
int max_length() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die maximale Anzahl von **Byte**s eine Herstellung **CharType**.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [Do_max_length](#codecvt__do_max_length).  
  
### <a name="example"></a>Beispiel  
  
```  
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
  
##  <a name="a-namecodecvtouta-codecvtout"></a><a name="codecvt__out"></a>  codecvt:: out  
 Konvertiert eine Sequenz interner **CharType**s, um eine Sequenz externer **Byte**s.  
  
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
 Der Status der Konvertierung, der zwischen den Aufrufen der Memberfunktion verwaltet wird.  
  
 ` first1`  
 Zeiger auf den Anfang der Sequenz konvertiert werden.  
  
 ` last1`  
 Ein Zeiger auf das Ende der Sequenz konvertiert werden.  
  
 ` next1`  
 Verweis auf einen Zeiger auf das erste nicht konvertiert **CharType** nach dem letzten **CharType** konvertiert.  
  
 ` first2`  
 Zeiger auf den Anfang der Sequenz konvertiert.  
  
 ` last2`  
 Ein Zeiger auf das Ende der konvertierten Sequenz.  
  
 ` next2`  
 Verweis auf einen Zeiger auf das erste nicht konvertiert **Byte** nach der letzten konvertiert **Byte**.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Memberfunktion gibt [Do_out](#codecvt__do_out)( `_State`, ` first1`, ` last1`, ` next1`, ` first2`, ` last2`, ` next2`).  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [codecvt:: do_out](#codecvt__do_out).  
  
### <a name="example"></a>Beispiel  
  
```  
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
  
##  <a name="a-namecodecvtstatetypea-codecvtstatetype"></a><a name="codecvt__state_type"></a>  codecvt:: state_type  
 Ein Zeichentyp, der verwendet wird, um Zwischenzustände bei Konvertierungen zwischen externen und internen Darstellungen darzustellen.  
  
```  
typedef StateType state_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter **StateType**.  
  
##  <a name="a-namecodecvtunshifta-codecvtunshift"></a><a name="codecvt__unshift"></a>  codecvt:: unshift  
 Stellt die **Byte**s in einer zustandsabhängigen Konvertierung benötigt werden, um das letzte Zeichen in einer Sequenz von abzuschließen **Byte**s.  
  
```  
result unshift(
    StateType& _State,  
    Byte* first2,   
    Byte* last2,   
    Byte*& next2) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_State`  
 Der Status der Konvertierung, der zwischen den Aufrufen der Memberfunktion verwaltet wird.  
  
 ` first2`  
 Ein Zeiger auf die erste Position im Zielbereich.  
  
 ` last2`  
 Ein Zeiger auf die letzte Position im Zielbereich.  
  
 ` next2`  
 Ein Zeiger auf das erste unverändert Element in der Ziel-Sequenz.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Funktion gibt zurück:  
  
- **codecvt_base::Error** Wenn Status einen ungültigen Status darstellt.  
  
- `codecvt_base::noconv` Wenn die Funktion keine Konvertierung durchführt.  
  
- **codecvt_base::OK** wenn die Konvertierung erfolgreich ist.  
  
- **codecvt_base::partial** ist das Ziel nicht groß genug für die Konvertierung erfolgreich ausgeführt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Die geschützte virtuelle Memberfunktion wird versucht, das Quellelement konvertieren **CharType**(0) in eine Ziel-Sequenz, die sie in speichert [ ` first2`, ` last2`), außer das abschließende Element **Byte**(0). Er speichert immer in ` next2` einen Zeiger auf das erste unverändert Element in der Ziel-Sequenz.  
  
 `_State` muss der ursprüngliche konvertierungszustand am Anfang einer neuen Quelle Sequenz darstellen. Die Funktion ändert den gespeicherten Wert, bei Bedarf auf dem aktuellen Zustand für eine erfolgreiche Konvertierung. In der Regel konvertieren das Quellelement **CharType**(0) bewirkt, dass den aktuellen Zustand der ersten Konvertierung.  
  
 Die Memberfunktion gibt [Do_unshift](#codecvt__do_unshift)( `_State`, ` first2`, ` last2`, ` next2` ).  
  
## <a name="see-also"></a>Siehe auch  
 [\< Gebietsschema>](../standard-library/locale.md)   
 [Codepages](../c-runtime-library/code-pages.md)   
 [Gebietsschemanamen, Sprachen und Zeichenfolgen für Länder/Regionen](../c-runtime-library/locale-names-languages-and-country-region-strings.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)

