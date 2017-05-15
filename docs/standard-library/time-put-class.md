---
title: time_put-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- time_put
- xloctime/std::time_put
- locale/std::time_put::char_type
- locale/std::time_put::iter_type
- locale/std::time_put::do_put
- locale/std::time_put::put
dev_langs:
- C++
helpviewer_keywords:
- time_put class
ms.assetid: df79493e-3331-48d2-97c3-ac3a745f0791
caps.latest.revision: 22
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
ms.openlocfilehash: 0331580941a30b8d6ab9468ce95182950478ddcb
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="timeput-class"></a>time_put-Klasse
Die Vorlagenklasse, die ein Objekt beschreibt, das als Gebietsschemafacet dienen kann, um Konvertierungen von Zeitwerten in Sequenzen vom Typ `CharType` zu steuern.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class CharType,  
    class OutputIterator = ostreambuf_iterator<CharType>>  
class time_put : public locale::facet;  
```  
  
#### <a name="parameters"></a>Parameter  
 `CharType`  
 Der Typ, der innerhalb eines Programms verwendet wird, um Zeichen zu codieren.  
  
 `OutputIterator`  
 Der Typ des Iterators, in den die Time-Put-Funktionen ihre Ausgabe schreiben.  
  
## <a name="remarks"></a>Hinweise  
 Wie bei jedem Gebietsschemafacet hat die statische Objekt-ID einen anfänglichen gespeicherten Wert von NULL. Beim ersten Versuch, auf den gespeicherten Wert zuzugreifen, wird in **id** ein eindeutiger positiver Wert gespeichert.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[time_put](#time_put)|Der Konstruktor für Objekte des Typs `time_put`.|  
  
### <a name="typedefs"></a>TypeDefs  
  
|||  
|-|-|  
|[char_type](#char_type)|Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.|  
|[iter_type](#iter_type)|Ein Typ, der einen Ausgabeiterator beschreibt.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[do_put](#do_put)|Eine virtuelle Funktion, die Zeit- und Datumsinformationen als Sequenz von `CharType`-Objekten ausgibt.|  
|[put](#put)|Gibt Zeit- und Datumsinformationen als Sequenz von `CharType`-Objekten aus.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<locale>  
  
 **Namespace:** std  
  
##  <a name="char_type"></a> time_put::char_type  
 Ein Typ, mit dem ein Zeichen beschrieben wird, das von einem Gebietsschema verwendet wird.  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter **CharType**.  
  
##  <a name="do_put"></a> time_put::do_put  
 Eine virtuelle Funktion, die Zeit- und Datumsinformationen als Sequenz von **CharType**-Objekten ausgibt.  
  
```  
virtual iter_type do_put(
    iter_type next,   
    ios_base& _Iosbase,  
    const tm* _Pt,   
    char _Fmt,   
    char _Mod = 0) const;
```  
  
### <a name="parameters"></a>Parameter  
 `next`  
 Ein Ausgabeiterator, in den die Zeichensequenz für Zeit und Datum eingefügt werden soll.  
  
 `_Iosbase`  
 Nicht verwendet.  
  
 `_Pt`  
 Die Zeit- und Datumsinformationen, die ausgegeben werden.  
  
 `_Fmt`  
 Das Format der Ausgabe. Siehe [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) für gültige Werte.  
  
 `_Mod`  
 Ein Modifizierer für das Format. Siehe [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) für gültige Werte.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator an die erste Position hinter dem letzten eingefügten Element.  
  
### <a name="remarks"></a>Hinweise  
 Die virtuelle geschützte Memberfunktion generiert sequenzielle Elemente vom Typ **tm** ab `next` aus im Objekt \* `_Pt` gespeicherten Zeitwerten. Die Funktion gibt einen Iterator zurück, der die nächste Stelle zum Einfügen eines Elements nach der generierten Ausgabe festlegt.  
  
 Die Ausgabe wird durch die gleichen Regeln wie durch `strftime` generiert, mit einem letzten Argument aus `_Pt`, um eine Serie von `char`-Elementen in eine Reihe zu generieren. Jedes dieser `char`-Elemente soll einem äquivalenten Element vom Typ **CharType** durch eine einfache 1:1-Zuordnung zugeordnet werden. Wenn `_Mod` gleich null ist, ist das effektive Format „%F“, wobei F durch `_Fmt` ersetzt wird. Andernfalls ist das effektive Format „%MF“, wobei M durch `_Mod` ersetzt wird.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [put](#put), mit dem `do_put` aufgerufen wird.  
  
##  <a name="iter_type"></a> time_put::iter_type  
 Ein Typ, der einen Ausgabeiterator beschreibt.  
  
```  
typedef OutputIterator iter_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für den Vorlagenparameter **OutputIterator**.  
  
##  <a name="put"></a> time_put::put  
 Gibt Zeit- und Datumsinformationen als Sequenz von **CharType**-Objekten aus.  
  
```  
iter_type put(iter_type next,
    ios_base& _Iosbase,
    char_type _Fill,
    const tm* _Pt,
    char _Fmt,
    char _Mod = 0) const;

iter_type put(iter_type next,
    ios_base& _Iosbase,
    char_type _Fill,
    const tm* _Pt,
    const CharType* first,
    const CharType* last) const;
```  
  
### <a name="parameters"></a>Parameter  
 `next`  
 Ein Ausgabeiterator, in den die Zeichensequenz für Zeit und Datum eingefügt werden soll.  
  
 `_Iosbase`  
 Nicht verwendet.  
  
 `_Fill`  
 Das Zeichen vom Typ **CharType**, das für Abstand verwendet wird.  
  
 `_Pt`  
 Die Zeit- und Datumsinformationen, die ausgegeben werden.  
  
 `_Fmt`  
 Das Format der Ausgabe. Siehe [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) für gültige Werte.  
  
 `_Mod`  
 Ein Modifizierer für das Format. Siehe [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) für gültige Werte.  
  
 `first`  
 Der Anfang der Formatierungszeichenfolge für die Ausgabe. Siehe [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) für gültige Werte.  
  
 `last`  
 Das Ende der Formatierungszeichenfolge für die Ausgabe. Siehe [strftime, wcsftime, _strftime_l, _wcsftime_l](../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) für gültige Werte.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Iterator an die erste Position hinter dem letzten eingefügten Element.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion gibt [do_put](#do_put)( `next`, `_Iosbase`, `_Fill`, `_Pt`, `_Fmt`, `_Mod`) zurück. Die zweite Memberfunktion kopiert jedes Element im Intervall [ `first`, `last`) außer Prozentzeichen (%) nach \* `next` ++. Für ein Prozentzeichen gefolgt von einem *C*-Zeichen im Intervall [ `first`, `last`) wertet die Funktion stattdessen `next` = `do_put`( `next`, `_Iosbase`, `_Fill`, `_Pt`, *C*, 0) und überspringt *C*. Wenn *C* jedoch ein Qualifiziererzeichen aus dem Satz EOQ# gefolgt von einem `C2`-Zeichen im Intervall [ `first`, `last`) ist, wertet die Funktion stattdessen `next` = `do_put`( `next`, `_Iosbase`, `_Fill`, `_Pt`, `C2`, *C*) und überspringt `C2`.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// time_put_put.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
#include <time.h>  
using namespace std;  
int main( )  
{  
   locale loc;  
   basic_stringstream<char> pszPutI;  
   ios_base::iostate st = 0;  
   struct tm t;  
   memset( &t, 0, sizeof( struct tm ) );  
  
   t.tm_hour = 5;  
   t.tm_min = 30;  
   t.tm_sec = 40;  
   t.tm_year = 00;  
   t.tm_mday = 4;  
   t.tm_mon = 6;  
  
   pszPutI.imbue( loc );  
   char *pattern = "x: %X %x";  
   use_facet <time_put <char> >  
   (loc).put(basic_ostream<char>::_Iter(pszPutI.rdbuf( )),  
          pszPutI, ' ', &t, pattern, pattern+strlen(pattern));  
  
      cout << "num_put( ) = " << pszPutI.rdbuf( )->str( ) << endl;  
  
      char strftimebuf[255];  
      strftime(&strftimebuf[0], 255, pattern, &t);  
      cout << "strftime( ) = " << &strftimebuf[0] << endl;  
}  
```  
  
```Output  
num_put( ) = x: 05:30:40 07/04/00  
strftime( ) = x: 05:30:40 07/04/00  
```  
  
##  <a name="time_put"></a> time_put::time_put  
 Konstruktor für Objekte des Typs `time_put`.  
  
```  
explicit time_put(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `_Refs`  
 Integerwert, der zum Angeben des Speicherverwaltungstyps für das Objekt verwendet wird.  
  
### <a name="remarks"></a>Hinweise  
 Mögliche Werte für den `_Refs`-Parameter und ihre Bedeutung:  
  
-   0: Die Lebensdauer des Objekts wird von den Gebietsschemas verwaltet, in denen es enthalten ist.  
  
-   1: Die Lebensdauer des Objekts muss manuell verwaltet werden.  
  
-   \>1: Diese Werte sind nicht definiert.  
  
 Der Konstruktor initialisiert seine Basisobjekt mit [locale::facet](../standard-library/locale-class.md#facet_class)(*_Refs*).  
  
## <a name="see-also"></a>Siehe auch  
 [\<locale>](../standard-library/locale.md)   
 [time_base-Klasse](../standard-library/time-base-class.md)   
 [Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)


