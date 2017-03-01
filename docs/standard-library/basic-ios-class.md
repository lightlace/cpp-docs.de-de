---
title: basic_ios-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.basic_ios
- ios/std::basic_ios
- basic_ios
- std::basic_ios
dev_langs:
- C++
helpviewer_keywords:
- basic_ios class
ms.assetid: 4fdcd8e1-62d2-4611-8a70-1e4f58434007
caps.latest.revision: 24
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 6987d9c75785ebb716324395e0ce295d4155e55f
ms.lasthandoff: 02/24/2017

---
# <a name="basicios-class"></a>basic_ios-Klasse
Die Vorlagenklasse beschreibt die Speicher- und Memberfunktionen, die sowohl Eingabestreams (der Vorlagenklasse [basic_istream](../standard-library/basic-istream-class.md)) als auch Ausgabestreams (der Vorlagenklasse [basic_ostream](../standard-library/basic-ostream-class.md)) gemeinsam sind, die von den Vorlagenparametern abhängen. (Die Klasse [ios_base](../standard-library/ios-base-class.md) beschreibt, welche Funktionen gemeinsam und nicht von Vorlagenparametern abhängig sind.) Ein Objekt der Klasse **basic_ios\<class Elem, class Traits>** steuert einen Stream mit Elementen des Typs **Elem**, dessen Zeichenmerkmale durch die **Traits**-Klasse bestimmt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
 
template <class Elem, class Traits>  
class basic_ios : public ios_base  
```  
  
#### <a name="parameters"></a>Parameter  
 `Elem`  
 Ein Typ.  
  
 `Traits`  
 Eine Variable des Typs `char_traits`.  
  
## <a name="remarks"></a>Hinweise  
 Ein Objekt der Klasse **basic_ios\<class Elem, class Traits>** speichert Folgendes:  
  
-   Einen tie-Zeiger auf ein Objekt des Typs [basic_istream](../standard-library/basic-istream-class.md)**\<Elem, Traits>**.  
  
-   Einen Streampufferzeiger auf ein Objekt des Typs [basic_streambuf](../standard-library/basic-streambuf-class.md)**\<Elem, Traits >**.  
  
- [Formatierungsinformationen](../standard-library/ios-base-class.md).  
  
- [Streamzustandsinformationen](../standard-library/ios-base-class.md) in einem Basisobjekt des Typs [ios_base](../standard-library/ios-base-class.md).  
  
-   Ein Füllzeichen in einem Objekt des Typs `char_type`.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[basic_ios](#basic_ios__basic_ios)|Erstellt die `basic_ios`-Klasse.|  
  
### <a name="typedefs"></a>TypeDefs  
  
|||  
|-|-|  
|[char_type](#basic_ios__char_type)|Ein Synonym für den Vorlagenparameter `Elem`.|  
|[int_type](#basic_ios__int_type)|Ein Synonym für `Traits::int_type`.|  
|[off_type](#basic_ios__off_type)|Ein Synonym für `Traits::off_type`.|  
|[pos_type](#basic_ios__pos_type)|Ein Synonym für `Traits::pos_type`.|  
|[traits_type](#basic_ios__traits_type)|Ein Synonym für den Vorlagenparameter `Traits`.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[bad](#basic_ios__bad)|Kennzeichnet einen Verlust der Integrität des Streampuffers.|  
|[clear](#basic_ios__clear)|Löscht alle Fehlerflags.|  
|[copyfmt](#basic_ios__copyfmt)|Kopiert Flags aus einem Stream in einen anderen.|  
|[eof](#basic_ios__eof)|Gibt an, dass das Ende eines Streams erreicht wurde.|  
|[exceptions](#basic_ios__exceptions)|Gibt an, welche Ausnahmen vom Datenstrom ausgelöst werden.|  
|[fail](#basic_ios__fail)|Kennzeichnet einen Fehler beim Extrahieren eines gültigen Felds aus einem Stream.|  
|[fill](#basic_ios__fill)|Gibt das Zeichen an oder zurück, das verwendet wird, wenn der Text nicht so breit ist wie der Stream.|  
|[good](#basic_ios__good)|Gibt an, dass der Stream in einem guten Zustand ist.|  
|[imbue](#basic_ios__imbue)|Ändert das Gebietsschema.|  
|[init](#basic_ios__init)|Wird von `basic_ios`-Konstruktoren aufgerufen.|  
|[move](#basic_ios__move)|Verschiebt alle Werte, mit Ausnahme des Zeigers auf den Streampuffer, aus dem Parameter in das aktuelle Objekt.|  
|[narrow](#basic_ios__narrow)|Sucht das entsprechende Zeichen zu einem angegebenen `char_type`.|  
|[rdbuf](#basic_ios__rdbuf)|Leitet einen Stream in den angegebenen Puffer weiter.|  
|[rdstate](#basic_ios__rdstate)|Liest den Status der Bits für Flags.|  
|[set_rdbuf](#basic_ios__set_rdbuf)|Weist einen Streampuffer zu, der der Lesepuffer für dieses Streamobjekt sein soll.|  
|[setstate](#basic_ios__setstate)|Legt zusätzliche Flags fest.|  
|[swap](#basic_ios__swap)|Tauscht die Werte in diesem `basic_ios`-Objekt gegen die Werte eines anderen `basic_ios`-Objekts aus. Die Zeiger auf die Streampuffer werden nicht ausgetauscht.|  
|[tie](#basic_ios__tie)|Stellt sicher, dass ein Stream vor einem anderen Stream verarbeitet wird.|  
|[widen](#basic_ios__widen)|Sucht den entsprechenden `char_type` zu einem angegebenen Zeichen.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[explicit operator bool](#basic_ios__operator_bool)|Ermöglicht es, ein `basic_ios`-Objekt als ein `bool`-Objekt zu verwenden. Die automatische Typkonvertierung wird deaktiviert, um häufig vorkommende unbeabsichtigte Nebeneffekte zu verhindern.|  
|[operator void *](#basic_ios__operator_void_star)|Gibt an, ob der Stream weiterhin brauchbar ist.|  
|[operator!](#basic_ios__operator_not)|Gibt an, ob der Stream nicht unbrauchbar ist.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<ios>  
  
 **Namespace:** std  
  
##  <a name="a-namebasiciosbada--basiciosbad"></a><a name="basic_ios__bad"></a> basic_ios::bad  
 Kennzeichnet einen Verlust der Integrität des Streampuffers.  
  
```  
bool bad() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn `rdstate & badbit` ungleich null ist, andernfalls `false`.  
  
 Weitere Informationen zu `badbit` finden Sie unter [ios_base::iostate](../standard-library/ios-base-class.md#ios_base__iostate).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// basic_ios_bad.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( void )  
{  
  using namespace std;  
  bool b = cout.bad( );  
  cout << boolalpha;  
  cout << b << endl;  
    
  b = cout.good( );  
  cout << b << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosbasiciosa--basiciosbasicios"></a><a name="basic_ios__basic_ios"></a> basic_ios::basic_ios  
 Erstellt die basic_ios-Klasse.  
  
```   
explicit basic_ios(basic_streambuf<Elem,  Traits>* sb);
basic_ios();
```  
  
### <a name="parameters"></a>Parameter  
 `sb`  
 Standardpuffer zum Speichern von Eingabe- oder Ausgabeelementen.  
  
### <a name="remarks"></a>Hinweise  
 Der erste Konstruktor initialisiert die Memberobjekte durch Aufrufen von [init](#basic_ios__init)(_ *Sb*). Der zweite (geschützte) Konstruktor initialisiert seine Memberobjekte nicht. Ein späterer Aufruf von **init** muss das Objekt initialisieren, bevor es sicher zerstört werden kann.  
  
##  <a name="a-namebasicioschartypea--basicioschartype"></a><a name="basic_ios__char_type"></a> basic_ios::char_type  
 Ein Synonym für den Vorlagenparameter **Elem**.  
  
```   
typedef Elem char_type;  
```  
  
##  <a name="a-namebasicioscleara--basiciosclear"></a><a name="basic_ios__clear"></a> basic_ios::clear  
 Löscht alle Fehlerflags.  
  
```   
void clear(iostate state = goodbit, bool reraise = false); 
void clear(io_state state);
```  
  
### <a name="parameters"></a>Parameter  
 `state` (optional)  
 Die Flags, die Sie nach dem Löschen aller Flags festlegen möchten. Wird standardmäßig auf `goodbit` festgelegt.  
  
 `reraise` (optional)  
 Gibt an, ob die Ausnahme erneut ausgelöst werden soll. Wird standardmäßig auf `false` festgelegt (die Ausnahme wird nicht erneut ausgelöst).  
  
### <a name="remarks"></a>Hinweise  
 Die Flags sind **goodbit**, **failbit**, **eofbit** und **badbit**. Testen Sie auf diese Flags mit [good](#basic_ios__good), [bad](#basic_ios__bad), [eof](#basic_ios__eof) und [fail](#basic_ios__fail).  
  
 Die Memberfunktion ersetzt die gespeicherten Informationen zum Streamstatus durch:  
  
 `state` &#124; `(`[rdbuf](#basic_ios__rdbuf) != 0 **goodbit** : **badbit**)  
  
 Wenn `state`**&**[exceptions](#basic_ios__exceptions) ungleich null ist, wird ein Objekt der Klasse [failure](../standard-library/ios-base-class.md#ios_base__failure) ausgelöst.  
  
### <a name="example"></a>Beispiel  
  Unter [rdstate](#basic_ios__rdstate) und [getline](../standard-library/string-functions.md#getline) finden Sie Beispiele zur Verwendung von **clear**.  
  
##  <a name="a-namebasicioscopyfmta--basicioscopyfmt"></a><a name="basic_ios__copyfmt"></a> basic_ios::copyfmt  
 Kopiert Flags aus einem Stream in einen anderen.  
  
```   
basic_ios<Elem, Traits>& copyfmt(
const basic_ios<Elem, Traits>& right);
```  
  
### <a name="parameters"></a>Parameter  
 ` right`  
 Der Stream, dessen Flags Sie kopieren möchten.  
  
### <a name="return-value"></a>Rückgabewert  
 Das **this**-Objekt für den Stream, in den Sie die Flags kopieren möchten.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion meldet das RückrufereignisÂ „erase_event“. Anschließend kopiert sie das Füllzeichen, den tie-Zeiger und die Formatierungsinformationen aus ` right` in **\*this**. Vor dem Ändern der Ausnahmemaske wird das Rückrufereignis „copyfmt_event“ gemeldet. Wenn **state &**[exceptions](#basic_ios__exceptions) nach Abschluss der Kopie ungleich null ist, ruft die Funktion effektiv [clear](#basic_ios__clear) mit dem Argument [rdstate](#basic_ios__rdstate) auf. Sie gibt **\*this** zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp    
// basic_ios_copyfmt.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main( )  
{  
  using namespace std;  
  ofstream x( "test.txt" );  
  int i = 10;  
    
  x << showpos;  
  cout << i << endl;  
  cout.copyfmt( x );  
  cout << i << endl;  
}  
  
```  
  
##  <a name="a-namebasicioseofa--basicioseof"></a><a name="basic_ios__eof"></a> basic_ios::eof  
 Gibt an, dass das Ende eines Streams erreicht wurde.  
  
```  
bool eof() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn das Ende eines Streams erreicht wurde; andernfalls `false`.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt `true` zurück, wenn [rdstate](#basic_ios__rdstate) `& eofbit` ungleich null ist. Weitere Informationen zu `eofbit` finden Sie unter [ios_base::iostate](../standard-library/ios-base-class.md#ios_base__iostate).  
  
### <a name="example"></a>Beispiel  
  
```cpp    
// basic_ios_eof.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
using namespace std;  
  
int main( int argc, char* argv[] )  
{  
  fstream   fs;  
  int n = 1;  
  fs.open( "basic_ios_eof.txt" );   // an empty file  
  cout << boolalpha  
  cout << fs.eof() << endl;  
  fs >> n;   // Read the char in the file  
  cout << fs.eof() << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosexceptionsa--basiciosexceptions"></a><a name="basic_ios__exceptions"></a> basic_ios::exceptions  
 Gibt an, welche Ausnahmen vom Datenstrom ausgelöst werden.  
  
```   
iostate exceptions() const; 
void exceptions(iostate Newexcept);
void exceptions(io_state Newexcept);
```  
  
### <a name="parameters"></a>Parameter  
 *Newexcept*  
 Die Flags, die eine Ausnahme auslösen sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Flags, die aktuell angegeben sind, um eine Ausnahme für den Stream auszulösen.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion gibt die gespeicherte Ausnahmemaske zurück. Die zweite Memberfunktion speichert *_Except* in der Ausgabemaske und gibt den zuletzt gespeicherten Wert zurück. Beachten Sie, dass das Speichern einer neuen Ausgabemaske ebenso wie der Aufruf von [clear](#basic_ios__clear)( [rdstate](#basic_ios__rdstate) ) eine Ausnahme auslösen kann.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// basic_ios_exceptions.cpp  
// compile with: /EHsc /GR  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
    
  cout << cout.exceptions( ) << endl;  
  cout.exceptions( ios::eofbit );  
  cout << cout.exceptions( ) << endl;  
  try  
  {  
    cout.clear( ios::eofbit );   // Force eofbit on  
  }  
  catch ( exception &e )  
  {  
    cout.clear( );  
    cout << "Caught the exception." << endl;  
    cout << "Exception class: " << typeid(e).name()  << endl;  
    cout << "Exception description: " << e.what() << endl;  
  }  
}  
  
```  
  
```Output  
  
0  
1  
Caught the exception.  
Exception class: class std::ios_base::failure  
Exception description: ios_base::eofbit set   
```  
  
##  <a name="a-namebasiciosfaila--basiciosfail"></a><a name="basic_ios__fail"></a> basic_ios::fail  
 Kennzeichnet einen Fehler beim Extrahieren eines gültigen Felds aus einem Stream.  
  
```  
bool fail() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true`, wenn [rdstate](#basic_ios__rdstate) `& (badbit|failbit)` ungleich null ist; andernfalls `false`.  
  
 Weitere Informationen zu `failbit` finden Sie unter [ios_base::iostate](../standard-library/ios-base-class.md#ios_base__iostate).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// basic_ios_fail.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( void )  
{  
  using namespace std;  
  bool b = cout.fail( );  
  cout << boolalpha;  
  cout << b << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosfilla--basiciosfill"></a><a name="basic_ios__fill"></a> basic_ios::fill  
 Gibt das Zeichen an oder zurück, das verwendet wird, wenn der Text nicht so breit ist wie der Stream.  
  
```   
char_type fill() const; 
char_type fill(char_type Char);
```  
  
### <a name="parameters"></a>Parameter  
 `Char`  
 Das Zeichen, das als das Füllzeichen dienen soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Das aktuelle Füllzeichen.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion gibt die gespeicherten Füllzeichen zurück. Die zweite Memberfunktion speichert `Char` in den Füllzeichen und gibt den zuletzt gespeicherten Wert zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// basic_ios_fill.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <iomanip>  
  
int main( )  
{  
  using namespace std;  
    
  cout << setw( 5 ) << 'a' << endl;     
  cout.fill( 'x' );  
  cout << setw( 5 ) << 'a' << endl;      
  cout << cout.fill( ) << endl;  
}  
  
```  
  
```Output  
  
a  
xxxxa  
x   
```  
  
##  <a name="a-namebasiciosgooda--basiciosgood"></a><a name="basic_ios__good"></a> basic_ios::good  
 Gibt an, dass der Stream in einem guten Zustand ist.  
  
```  
bool good() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 `true` bei [rdstate](#basic_ios__rdstate) `== goodbit` (keine Statusflags festgelegt); andernfalls `false`.  
  
 Weitere Informationen zu `goodbit` finden Sie unter [ios_base::iostate](../standard-library/ios-base-class.md#ios_base__iostate).  
  
### <a name="example"></a>Beispiel  
  Unter [basic_ios::bad](#basic_ios__bad) finden Sie ein Beispiel für die Verwendung von `good`.  
  
##  <a name="a-namebasiciosimbuea--basiciosimbue"></a><a name="basic_ios__imbue"></a> basic_ios::imbue  
 Ändert das Gebietsschema.  
  
```   
locale imbue(const locale& Loc);
```  
  
### <a name="parameters"></a>Parameter  
 `Loc`  
 Eine lokale Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Das vorherige Gebietsschema.  
  
### <a name="remarks"></a>Hinweise  
 Wenn [rdbuf](#basic_ios__rdbuf) kein NULL-Zeiger ist, ruft die Memberfunktion Folgendes auf:  
  
 `rdbuf`-> [pubimbue](../standard-library/basic-streambuf-class.md#basic_streambuf__pubimbue)(_ *Loc*)  
  
 In jedem Fall gibt sie [ios_base::imbue](../standard-library/ios-base-class.md#ios_base__imbue)(_ *Loc*) zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// basic_ios_imbue.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <locale>  
  
int main( )  
{  
  using namespace std;  
    
  cout.imbue( locale( "french_france" ) );  
  double x = 1234567.123456;  
  cout << x << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosinita--basiciosinit"></a><a name="basic_ios__init"></a> basic_ios::init  
 Wird von basic_ios-Konstruktoren aufgerufen.  
  
```  
 
void init(basic_streambuf<Elem,Traits>* _Sb, bool _Isstd = false);
```  
  
### <a name="parameters"></a>Parameter  
 `_Sb`  
 Standardpuffer zum Speichern von Eingabe- oder Ausgabeelementen.  
  
 `_Isstd`  
 Gibt an, ob es sich um einen Standardstream handelt.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion speichert Werte in allen Memberobjekten, sodass:  
  
- [rdbuf](#basic_ios__rdbuf) *_Sb.* zurückgibt.  
  
- [tie](#basic_ios__tie) einen NULL-Zeiger zurückgibt.  
  
- [rdstate](#basic_ios__rdstate) [goodbit](../standard-library/ios-base-class.md#ios_base__iostate) zurückgibt, wenn `_Sb` ungleich null ist; andernfalls wird [badbit](../standard-library/ios-base-class.md#ios_base__iostate) zurückgegeben.  
  
- [exceptions](#basic_ios__exceptions) **goodbit** zurückgibt.  
  
- [flags](../standard-library/ios-base-class.md#ios_base__flags) [skipws](../standard-library/ios-base-class.md#ios_base__fmtflags) &#124; [dec](../standard-library/ios-base-class.md#ios_base__fmtflags) zurückgibt.  
  
- [width](../standard-library/ios-base-class.md#ios_base__width) 0 zurückgibt.  
  
- [precision](../standard-library/ios-base-class.md#ios_base__precision) 6 zurückgibt.  
  
- [fill](#basic_ios__fill) das Leerzeichen zurückgibt.  
  
- [getloc](../standard-library/ios-base-class.md#ios_base__getloc) `locale::classic` zurückgibt.  
  
- [iword](../standard-library/ios-base-class.md#ios_base__iword) null zurückgibt, und [pword](../standard-library/ios-base-class.md#ios_base__pword) einen NULL-Zeiger für alle Argumentwerte zurückgibt.  
  
##  <a name="a-namebasiciosinttypea--basiciosinttype"></a><a name="basic_ios__int_type"></a> basic_ios::int_type  
 Ein Synonym für **traits_type::int_type**.  
  
```  
typedef typename traits_type::int_type int_type;  
```  
  
##  <a name="a-namebasiciosmovea--basiciosmove"></a><a name="basic_ios__move"></a> basic_ios::move  
 Verschiebt alle Werte, mit Ausnahme des Zeigers auf den Streampuffer, aus dem Parameter in das aktuelle Objekt.  
  
```   
void move(basic_ios&& right);
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 Das `ios_base`-Objekt, aus dem Werte verschoben werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Die geschützte Memberfunktion verschiebt alle in ` right` gespeicherten Werte nach `*this`, mit Ausnahme des gespeicherten Zeigers `stream buffer pointer`, der unverändert in ` right` bleibt und in `*this` als NULL-Zeiger festgelegt wird. Der gespeicherte Zeiger `tie pointer` wird in ` right` als NULL-Zeiger festgelegt.  
  
##  <a name="a-namebasiciosnarrowa--basiciosnarrow"></a><a name="basic_ios__narrow"></a> basic_ios::narrow  
 Sucht das entsprechende Zeichen zu einem angegebenen `char_type`.  
  
```  
 
char narrow(char_type Char, char Default = '\0') const;
```  
  
### <a name="parameters"></a>Parameter  
 `Char`  
 Die zu konvertierende `char`.  
  
 `Default`  
 Das `char`, das zurückgegeben werden soll, wenn keine Entsprechung gefunden wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Der entsprechende `char` zu einem angegebenen `char_type`.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [use_facet](../standard-library/basic-filebuf-class.md#basic_filebuf__open)**<**Â **ctype**\< **E**> >( [getloc](../standard-library/ios-base-class.md#ios_base__getloc)( ) ) zurück. `narrow`( `Char`, `Default`).  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// basic_ios_narrow.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <wchar.h>  
  
int main( )  
{  
  using namespace std;  
  wchar_t *x = L"test";  
  char y[10];  
  cout << x[0] << endl;  
  wcout << x << endl;  
  y[0] = wcout.narrow( x[0] );  
  cout << y[0] << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosofftypea--basiciosofftype"></a><a name="basic_ios__off_type"></a> basic_ios::off_type  
 Ein Synonym für **traits_type::off_type**.  
  
```  
typedef typename traits_type::off_type off_type;  
```  
  
##  <a name="a-namebasiciosoperatorvoidstara--basiciosoperator-void-"></a><a name="basic_ios__operator_void_star"></a> basic_ios::operator void *  
 Gibt an, ob der Stream weiterhin brauchbar ist.  
  
```  
 operator void *() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Operator gibt nur bei [fail](#basic_ios__fail) einen NULL-Zeiger zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// basic_ios_opgood.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
  cout << (bool)(&cout != 0) << endl;   // Stream is still good  
}  
  
```  
  
```Output  
1  
```  
  
##  <a name="a-namebasiciosoperatornota--basiciosoperator"></a><a name="basic_ios__operator_not"></a> basic_ios::operator!  
 Gibt an, ob der Stream nicht unbrauchbar ist.  
  
```   
bool operator!() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt [fail](#basic_ios__fail) zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// basic_ios_opbad.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
  cout << !cout << endl;   // Stream is not bad  
}  
  
```  
  
```Output  
0  
```  
  
##  <a name="a-namebasiciosoperatorboola--basiciosoperator-bool"></a><a name="basic_ios__operator_bool"></a> basic_ios::operator bool  
 Ermöglicht es, ein `basic_ios`-Objekt als ein `bool`-Objekt zu verwenden. Die automatische Typkonvertierung wird deaktiviert, um häufig vorkommende unbeabsichtigte Nebeneffekte zu verhindern.  
  
```  
explicit operator bool() const;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Operator gibt einen Wert zurück, der nur bei `fail``()` in `false` konvertiert werden kann. Der Rückgabetyp kann nur zu `bool` konvertiert werden, nicht zu `void *` oder zu anderen bekannten skalaren Typen.  
  
##  <a name="a-namebasiciospostypea--basiciospostype"></a><a name="basic_ios__pos_type"></a> basic_ios::pos_type  
 Ein Synonym für **traits_type::pos_type**.  
  
```  
typedef typename traits_type::pos_type pos_type;  
```  
  
##  <a name="a-namebasiciosrdbufa--basiciosrdbuf"></a><a name="basic_ios__rdbuf"></a> basic_ios::rdbuf  
 Leitet einen Stream in den angegebenen Puffer weiter.  
  
```   
basic_streambuf<Elem, Traits> *rdbuf() const; 
basic_streambuf<Elem, Traits> *rdbuf(
basic_streambuf<Elem, Traits>* _Sb);
```  
  
### <a name="parameters"></a>Parameter  
 `_Sb`  
 Ein Stream.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion gibt den gespeicherten Streampufferzeiger zurück.  
  
 Die zweite Memberfunktion speichert `_Sb` im gespeicherten Streampufferzeiger und gibt den vorher gespeicherten Wert zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// basic_ios_rdbuf.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <fstream>  
  
int main( )  
{  
  using namespace std;  
  ofstream file( "rdbuf.txt" );  
  streambuf *x = cout.rdbuf( file.rdbuf( ) );  
  cout << "test" << endl;   // Goes to file  
  cout.rdbuf(x);  
  cout << "test2" << endl;  
}  
  
```  
  
```Output  
test2  
```  
  
##  <a name="a-namebasiciosrdstatea--basiciosrdstate"></a><a name="basic_ios__rdstate"></a> basic_ios::rdstate  
 Liest den Status der Bits für Flags.  
  
```  
 
iostate rdstate() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die gespeicherten Informationen zum Status des Streams.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// basic_ios_rdstate.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
using namespace std;  
  
void TestFlags( ios& x )  
{  
  cout << ( x.rdstate( ) & ios::badbit ) << endl;  
  cout << ( x.rdstate( ) & ios::failbit ) << endl;  
  cout << ( x.rdstate( ) & ios::eofbit ) << endl;  
  cout << endl;  
}  
  
int main( )  
{  
  fstream x( "c:\test.txt", ios::out );  
  x.clear( );  
  TestFlags( x );  
  x.clear( ios::badbit | ios::failbit | ios::eofbit );  
  TestFlags( x );  
}  
  
```  
  
```Output  
  
0  
0  
0  
  
4  
2  
1   
```  
  
##  <a name="a-namebasiciossetstatea--basiciossetstate"></a><a name="basic_ios__setstate"></a> basic_ios::setstate  
 Legt zusätzliche Flags fest.  
  
```   
void setstate(iostate _State);
```  
  
### <a name="parameters"></a>Parameter  
 `_State`  
 Zusätzlich festzulegende Flags.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion ruft effektiv [clear](#basic_ios__clear)(_ *State* &#124; [rdstate](#basic_ios__rdstate)) auf.  
  
### <a name="example"></a>Beispiel  
  
```cpp    
// basic_ios_setstate.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
  bool b = cout.bad( );  
  cout << b << endl;   // Good  
  cout.clear( ios::badbit );  
  b = cout.bad( );  
  // cout.clear( );  
  cout << b << endl;   // Is bad, good  
  b = cout.fail( );  
  cout << b << endl;   // Not failed  
  cout.setstate( ios::failbit );  
  b = cout.fail( );  
  cout.clear( );  
  cout << b << endl;   // Is failed, good  
  return 0;  
}  
  
```  
  
```Output  
  
0  
1   
```  
  
##  <a name="a-namebasiciossetrdbufa--basiciossetrdbuf"></a><a name="basic_ios__set_rdbuf"></a> basic_ios::set_rdbuf  
 Weist einen Streampuffer zu, der der Lesepuffer für dieses Streamobjekt sein soll.  
  
```   
void set_rdbuf(
basic_streambuf<Elem, Tr>* strbuf)  
```  
  
### <a name="parameters"></a>Parameter  
 ` strbuf`  
 Der Streampuffer, der zum Lesepuffer werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die geschützte Memberfunktion speichert ` strbuf` in `stream buffer pointer`. Sie ruft nicht `clear` auf.  
  
##  <a name="a-namebasiciostiea--basiciostie"></a><a name="basic_ios__tie"></a> basic_ios::tie  
 Stellt sicher, dass ein Stream vor einem anderen Stream verarbeitet wird.  
  
```  
 
basic_ostream<Elem, Traits> *tie() const; 
basic_ostream<Elem, Traits> *tie(
basic_ostream<Elem, Traits>* str);
```  
  
### <a name="parameters"></a>Parameter  
 ` str`  
 Ein Stream.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste Memberfunktion gibt den gespeicherten tie-Zeiger zurück. Die zweite Memberfunktion speichert ` str` im tie-Zeiger und gibt den zuletzt gespeicherten Wert zurück.  
  
### <a name="remarks"></a>Hinweise  
 `tie` bewirkt, dass zwei Streams so synchronisiert werden, dass Vorgänge für einen Stream erst stattfinden, wenn sie für den anderen Stream abgeschlossen sind.  
  
### <a name="example"></a>Beispiel  
  In diesem Beispiel wird durch Verbinden von „cin“ mit „cout“ sichergestellt, dass die Zeichenfolge „Enter a number:“ (Geben Sie eine Zahl ein) die Konsole erreicht, bevor die Zahl selbst aus „cin“ extrahiert wird. Dadurch wird ausgeschlossen, dass die Zeichenfolge „Enter a number:“ sich noch im Puffer befindet, wenn die Zahl gelesen wird, sodass wir sichergehen können, dass der Benutzer eine Eingabeaufforderung erhält, auf die er reagieren kann. Standardmäßig sind „cin“ und „cout“ verbunden.  
  
```  
  
#include <ios>  
#include <iostream>  
  
int main( )  
{  
  using namespace std;  
  int i;  
  cin.tie( &cout );  
  cout << "Enter a number:";  
  cin >> i;  
}  
  
```  
  
##  <a name="a-namebasiciostraitstypea--basiciostraitstype"></a><a name="basic_ios__traits_type"></a> basic_ios::traits_type  
 Dient als ein Synonym für den Vorlagenparameter **Traits**.  
  
```   
typedef Traits traits_type;  
```  
  
##  <a name="a-namebasicioswidena--basicioswiden"></a><a name="basic_ios__widen"></a> basic_ios::widen  
 Sucht den entsprechenden `char_type` zu einem angegebenen `char`.  
  
```   
char_type widen(char Char) const;
```  
  
### <a name="parameters"></a>Parameter  
 `Char`  
 Das zu konvertierende Zeichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Sucht den entsprechenden `char_type` zu einem angegebenen `char`.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [use_facet](../standard-library/basic-filebuf-class.md#basic_filebuf__open)< **ctype**\< **E**> >( [getloc](../standard-library/ios-base-class.md#ios_base__getloc)) zurück. `widen`( `Char`).  
  
### <a name="example"></a>Beispiel  
  
```cpp    
// basic_ios_widen.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <wchar.h>  
  
int main( )  
{  
  using namespace std;  
  char *z = "Hello";  
  wchar_t y[2] = {0,0};  
  cout << z[0] << endl;  
  y[0] = wcout.widen( z[0] );  
  wcout << &y[0] << endl;  
}  
  
```  
  
##  <a name="a-namebasiciosswapa--basiciosswap"></a><a name="basic_ios__swap"></a> basic_ios::swap  
 Tauscht die Werte in diesem `basic_ios`-Objekt gegen die Werte eines anderen `basic_ios`-Objekts aus. Die Zeiger auf die Streampuffer werden jedoch nicht ausgetauscht.  
  
```   
void swap(basic_ios&& right);
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 Das `basic_ios`-Objekt, das zum Austauschen von Werten verwendet wird.  
  
### <a name="remarks"></a>Hinweise  
 Die geschützte Memberfunktion tauscht alle Werte aus, die mit `*this` in ` right` gespeichert sind, bis auf den gespeicherten Zeiger `stream buffer pointer`.  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams-Konventionen](../standard-library/iostreams-conventions.md)


