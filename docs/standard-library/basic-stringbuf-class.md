---
title: basic_stringbuf-Klasse| Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sstream/std::basic_stringbuf
- sstream/std::basic_stringbuf::allocator_type
- sstream/std::basic_stringbuf::char_type
- sstream/std::basic_stringbuf::int_type
- sstream/std::basic_stringbuf::off_type
- sstream/std::basic_stringbuf::pos_type
- sstream/std::basic_stringbuf::traits_type
- sstream/std::basic_stringbuf::overflow
- sstream/std::basic_stringbuf::pbackfail
- sstream/std::basic_stringbuf::seekoff
- sstream/std::basic_stringbuf::seekpos
- sstream/std::basic_stringbuf::str
- sstream/std::basic_stringbuf::underflow
dev_langs: C++
helpviewer_keywords:
- std::basic_stringbuf [C++]
- std::basic_stringbuf [C++], allocator_type
- std::basic_stringbuf [C++], char_type
- std::basic_stringbuf [C++], int_type
- std::basic_stringbuf [C++], off_type
- std::basic_stringbuf [C++], pos_type
- std::basic_stringbuf [C++], traits_type
- std::basic_stringbuf [C++], overflow
- std::basic_stringbuf [C++], pbackfail
- std::basic_stringbuf [C++], seekoff
- std::basic_stringbuf [C++], seekpos
- std::basic_stringbuf [C++], str
- std::basic_stringbuf [C++], underflow
ms.assetid: 40c85f9e-42a5-4a65-af5c-23c8e3bf8113
caps.latest.revision: "28"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7b1b41f1a12f6b9e97db6ad3014b047bbc0f4b72
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="basicstringbuf-class"></a>basic_stringbuf-Klasse
Beschreibt einen die Übertragung zu und aus einer Sequenz von in einem Arrayobjekt gespeicherten Elementen von Elementen des Typs `Elem` steuernden Streampuffer, dessen Zeichenmerkmale durch die Klasse `Tr` ermittelt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Elem, class Tr = char_traits<Elem>,   
    class Alloc = allocator<Elem>>  
class basic_stringbuf : public basic_streambuf<Elem, Tr>  
```  
  
#### <a name="parameters"></a>Parameter  
 `Alloc`  
 Die Zuweisungsklasse.  
  
 `Elem`  
 Der Typ des grundlegenden Elements der Zeichenfolge.  
  
 `Tr`  
 Die für das grundlegende Element der Zeichenfolge spezialisierten Zeichenmerkmale.  
  
## <a name="remarks"></a>Hinweise  
 Das Objekt wird reserviert, erweitert und freigegeben, sofern erforderlich, um Änderungen in der Sequenz zu berücksichtigen.  
  
 Ein Objekt der Klasse basic_stringbuf< `Elem`, `Tr`, `Alloc`> speichert eine Kopie des Arguments `ios_base::`[openmode](../standard-library/ios-base-class.md#openmode) aus seinem Konstruktor als seinen `stringbuf`-Modus **mode**:  
  
-   Wenn `mode & ios_base::in` ungleich 0 ist, kann auf den Eingabepuffer zugegriffen werden. Weitere Informationen finden Sie unter [basic_streambuf-Klasse](../standard-library/basic-streambuf-class.md).  
  
-   Wenn `mode & ios_base::out` ungleich 0 ist, kann auf den Ausgabepuffer zugegriffen werden.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[basic_stringbuf](#basic_stringbuf)|Konstruiert ein Objekt vom Typ `basic_stringbuf`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[allocator_type](#allocator_type)|Der Type stellt ein Synonym für den Vorlagenparameter `Alloc` dar.|  
|[char_type](#char_type)|Verknüpft einen Typnamen mit dem `Elem`-Vorlagenparameter.|  
|[int_type](#int_type)|Stellt den Typ im Bereich von `basic_filebuf` dem Typ desselben Namens im Bereich `Tr` gleich.|  
|[off_type](#off_type)|Stellt den Typ im Bereich von `basic_filebuf` dem Typ desselben Namens im Bereich `Tr` gleich.|  
|[pos_type](#pos_type)|Stellt den Typ im Bereich von `basic_filebuf` dem Typ desselben Namens im Bereich `Tr` gleich.|  
|[traits_type](#traits_type)|Verknüpft einen Typnamen mit dem `Tr`-Vorlagenparameter.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[overflow](#overflow)|Eine geschützte virtuelle Funktion, die aufgerufen werden kann, wenn ein neues Zeichen in einen vollen Puffer eingefügt wird.|  
|[pbackfail](#pbackfail)|Die geschützte virtuelle Memberfunktion versucht, ein Element zurück in den Eingabepuffer zu versetzen und es dann zum aktuellen Element zu ernennen (wird mit dem nächsten Zeiger darauf gezeigt).|  
|[seekoff](#seekoff)|Die geschützte virtuelle Memberfunktion versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.|  
|[seekpos](#seekpos)|Die geschützte virtuelle Memberfunktion versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.|  
|[str](#str)|Legt den Text in einem Zeichenfolgenpuffer fest, ohne die Schreibposition zu ändern, oder ruft ihn ab.|  
|swap||  
|[underflow](#underflow)|Die geschützte virtuelle Memberfunktion versucht, das aktuelle Element aus dem Eingabestream zu extrahieren.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<sstream>  
  
 **Namespace:** std  
  
##  <a name="allocator_type"></a> basic_stringbuf::allocator_type  
 Der Type stellt ein Synonym für den Vorlagenparameter `Alloc` dar.  
  
```  
typedef Alloc allocator_type;  
```  
  
##  <a name="basic_stringbuf"></a> basic_stringbuf::basic_stringbuf  
 Konstruiert ein Objekt vom Typ `basic_stringbuf`.  
  
```  
basic_stringbuf(
    ios_base::openmode _Mode = ios_base::in | ios_base::out);

basic_stringbuf(
    const basic_string<Elem, Tr, Alloc>& str,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```  
  
### <a name="parameters"></a>Parameter  
 `_Mode`  
 Eine der Enumerationen in [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
 `str`  
 Ein Objekt vom Typ [basic_string](../standard-library/basic-string-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Der erste Konstruktor speichert einen NULL-Zeiger in allen Zeigern, die den Eingabe- und Ausgabepuffer steuern. Weitere Informationen finden Sie im Abschnitt „Hinweise“ unter [basic_streambuf-Klasse](../standard-library/basic-streambuf-class.md). Er speichert auch `_Mode` als stringbuf-Modus. Weitere Informationen finden Sie im Abschnitt „Hinweise“ unter [basic_stringbuf-Klasse](../standard-library/basic-stringbuf-class.md).  
  
 Der zweite Konstruktor weist eine Kopie der vom Zeichenfolgenobjekt `str` kontrollierten Sequenz zu. Wenn `_Mode & ios_base::in` ungleich null ist, wird festgelegt, dass der Eingabepuffer den Lesevorgang am Anfang der Sequenz beginnt. Wenn `_Mode & ios_base::out` ungleich null ist, wird festgelegt, dass der Ausgabepuffer den Schreibvorgang am Anfang der Sequenz beginnt. Er speichert auch `_Mode` als stringbuf-Modus. Weitere Informationen finden Sie im Abschnitt „Hinweise“ unter [basic_stringbuf-Klasse](../standard-library/basic-stringbuf-class.md).  
  
##  <a name="char_type"></a> basic_stringbuf::char_type  
 Verknüpft einen Typnamen mit dem Vorlagenparameter **Elem**.  
  
```  
typedef Elem char_type;  
```  
  
##  <a name="int_type"></a> basic_stringbuf::int_type  
 Stellt den Typ im Bereich von basic_filebuf dem Typ desselben Namens im Bereich **Tr** gleich.  
  
```  
typedef typename traits_type::int_type int_type;  
```  
  
##  <a name="off_type"></a> basic_stringbuf::off_type  
 Stellt den Typ im Bereich von basic_filebuf dem Typ desselben Namens im Bereich **Tr** gleich.  
  
```  
typedef typename traits_type::off_type off_type;  
```  
  
##  <a name="overflow"></a> basic_stringbuf::overflow  
 Eine geschützte virtuelle Funktion, die aufgerufen werden kann, wenn ein neues Zeichen in einen vollen Puffer eingefügt wird.  
  
```  
virtual int_type overflow(int_type _Meta = traits_type::eof());
```  
  
### <a name="parameters"></a>Parameter  
 `_Meta`  
 Das Zeichen, das in den Puffer eingefügt werden soll, oder **traits_type::eof**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion nicht erfolgreich abgeschlossen werden kann, wird **traits_type::eof** zurückgegeben. Andernfalls wird **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*) zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Wenn _ *Meta* nicht **traits_type::**[eof](../standard-library/char-traits-struct.md#eof) entspricht, versucht die geschützte virtuelle Memberfunktion, das Element **traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)(\_ *Meta*) in den Ausgabepuffer einzufügen. Hierfür gibt es verschiedene Möglichkeiten:  
  
-   Wenn eine Schreibposition verfügbar ist, kann das Element in der Schreibposition gespeichert werden, und der nächste Zeiger für den Ausgabepuffer kann inkrementiert werden.  
  
-   Eine Schreibposition kann verfügbar gemacht werden, indem neuer oder zusätzlicher Speicher für den Ausgabepuffer zugewiesen wird. Das Erweitern des Ausgabepuffers erweitert so auch alle zugewiesenen Eingabepuffer.  
  
##  <a name="pbackfail"></a> basic_stringbuf::pbackfail  
 Die geschützte virtuelle Memberfunktion versucht, ein Element zurück in den Eingabepuffer zu versetzen, und es dann zum aktuellen Element zu ernennen (wird mit dem nächsten Zeiger darauf gezeigt).  
  
```  
virtual int_type pbackfail(int_type _Meta = traits_type::eof());
```  
  
### <a name="parameters"></a>Parameter  
 `_Meta`  
 Das Zeichen, das in den Puffer eingefügt werden soll, oder **traits_type::eof**.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion nicht erfolgreich abgeschlossen werden kann, wird **traits_type::eof** zurückgegeben. Andernfalls wird **traits_type::**[not_eof](../standard-library/char-traits-struct.md#not_eof)(_ *Meta*) zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `_Meta` mit **traits_type::**[eof](../standard-library/char-traits-struct.md#eof) übereinstimmt, ist das Element für den Pushback das Element, das sich bereits vor dem aktuellen Element im Stream befindet. Andernfalls wird dieses Element durch **byte** = **traits_type::**[to_char_type](../standard-library/char-traits-struct.md#to_char_type)(_ *Meta*) ersetzt. Ein Element kann auf verschiedene Arten durch die Funktion wiederhergestellt werden:  
  
-   Wenn eine Position zur Wiederherstellung verfügbar ist, und das Element, das dort gespeichert ist, „byte“ entspricht, kann der nächste Zeiger für den Eingabepuffer verringert werden.  
  
-   Wenn eine Position zur Wiederherstellung verfügbar ist, und der stringbuf-Modus zulässt, dass die Sequenz geändert wird ( **mode & ios_base::out** ist ungleich null), kann „byte“ in der Position zur Wiederherstellung gespeichert werden und den nächsten Zeiger für den Eingabepuffer verringern.  
  
##  <a name="pos_type"></a> basic_stringbuf::pos_type  
 Stellt den Typ im Bereich von basic_filebuf dem Typ desselben Namens im Bereich **Tr** gleich.  
  
```  
typedef typename traits_type::pos_type pos_type;  
```  
  
##  <a name="seekoff"></a> basic_stringbuf::seekoff  
 Die geschützte virtuelle Memberfunktion versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.  
  
```  
virtual pos_type seekoff(
    off_type _Off,  
    ios_base::seekdir _Way,  
    ios_base::openmode _Mode = ios_base::in | ios_base::out);
```  
  
### <a name="parameters"></a>Parameter  
 `_Off`  
 Die Position, nach der gesucht werden soll, die relativ zu `_Way` ist. Weitere Informationen finden Sie unter [basic_stringbuf::off_type](#off_type).  
  
 `_Way`  
 Der Startpunkt für Offsetvorgänge. Mögliche Werte sind unter [ios_base::seekdir](../standard-library/ios-base-class.md#seekdir) aufgeführt.  
  
 `_Mode`  
 Gibt den Modus für die Zeigerposition an. Standardmäßig können Lese- und Schreibpositionen geändert werden. Weitere Informationen finden Sie unter [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die neue Position oder eine ungültige Streamposition zurück.  
  
### <a name="remarks"></a>Hinweise  
 Für ein Objekt der Klasse `basic_stringbuf<Elem, Tr, Alloc>` besteht eine Streamposition nur aus einem Streamoffset. Das Offset Null legt das erste Element der kontrollierten Sequenz fest.  
  
 Die neue Position wird wie folgt bestimmt:  
  
-   Bei `_Way` == `ios_base::beg` ist die neue Position der Anfang des Streams plus `_Off`.  
  
-   Bei `_Way` == `ios_base::cur` ist die neue Position die aktuelle Streamposition plus `_Off`.  
  
-   Bei `_Way` == `ios_base::end` ist die neue Position das Ende des Streams plus `_Off`.  
  
 Wenn `_Mode & ios_base::in` ungleich null ist, ändert die Funktion die nächste Position, die im Eingabepuffer gelesen werden soll. Wenn `_Mode & ios_base::out` ungleich null ist, ändert die Funktion die nächste Position, die im Ausgabepuffer gelesen werden soll. Damit ein Stream betroffen wird, muss ein Puffer bestehen. Damit eine Positionierung erfolgreich ist, muss die resultierende Streamposition innerhalb der kontrollierten Sequenz liegen. Wenn die Funktion beide Streampositionen betrifft, muss `_Way` `ios_base::beg` oder `ios_base::end` sein. Außerdem müssen beide Streams am gleichen Element positioniert werden. Andernfalls (oder wenn keine Position betroffen ist) tritt bei der Positionierung ein Fehler ein.  
  
 Wenn die Funktion erfolgreich eine der beiden Streampositionen ändern kann, gibt sie die resultierende Streamposition zurück. Andernfalls schlägt sie fehl und gibt eine ungültige Streamposition zurück.  
  
##  <a name="seekpos"></a> basic_stringbuf::seekpos  
 Die geschützte virtuelle Memberfunktion versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.  
  
```  
virtual pos_type seekpos(pos_type _Sp, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```  
  
### <a name="parameters"></a>Parameter  
 `_Sp`  
 Die Position, nach der gesucht werden soll.  
  
 `_Mode`  
 Gibt den Modus für die Zeigerposition an. Standardmäßig können Lese- und Schreibpositionen geändert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich eine der beiden Streampositionen ändern kann, gibt sie die resultierende Streamposition zurück. Andernfalls schlägt sie fehl und gibt eine ungültige Streamposition zurück. Vergleichen Sie den Rückgabewert mit `pos_type(off_type(-1))`, um festzustellen, ob die Streamposition ungültig ist.  
  
### <a name="remarks"></a>Hinweise  
 Für ein Objekt der Klasse basic_stringbuf< **Elem**, **Tr**, `Alloc`> besteht eine Streamposition bloß aus einem Streamoffset. Das Offset Null legt das erste Element der gesteuerten Sequenz fest. Die neue Position wird von _ *Sp* bestimmt.  
  
 Wenn **mode & ios_base::in** ungleich null ist, ändert die Funktion die nächste Position, die in den Eingabepuffer gelesen werden soll. Wenn **mode & ios_base::out** ungleich null ist, ändert die Funktion die nächste Position, die in den Ausgabepuffer geschrieben werden soll. Damit ein Stream betroffen wird, muss ein Puffer bestehen. Damit eine Positionierung erfolgreich ist, muss die resultierende Streamposition innerhalb der gesteuerten Sequenz liegen. Andernfalls (oder wenn keine Position betroffen ist) tritt bei der Positionierung ein Fehler ein.  
  
##  <a name="str"></a> basic_stringbuf::str  
 Legt den Text in einem Zeichenfolgenpuffer fest, ohne die Schreibposition zu ändern, oder ruft ihn ab.  
  
```  
basic_string<Elem, Tr, Alloc> str() const;
void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```  
  
### <a name="parameters"></a>Parameter  
 `_Newstr`  
 Die neue Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt ein Objekt der Klasse [basic_string](../standard-library/basic-string-class.md)\< **Elem**, **Tr**, Alloc **>,** zurück, dessen gesteuerte Sequenz eine Kopie der von **\*this** gesteuerten Sequenz ist.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion gibt ein Objekt der Klasse basic_string< **Elem**, **Tr**, `Alloc`> zurück, dessen gesteuerte Sequenz eine Kopie der von **\*this** gesteuerten Sequenz ist. Die kopierte Sequenz ist vom Modus „stored stringbuf“ abhängig:  
  
-   Wenn **mode & ios_base::out** ungleich null ist, und ein Ausgabepuffer besteht, ist die Sequenz der gesamte Ausgabepuffer ( [epptr](../standard-library/basic-streambuf-class.md#epptr) - [pbase](../standard-library/basic-streambuf-class.md#pbase)-Elemente, die mit `pbase` beginnen).  
  
-   Wenn **mode & ios_base::in** ungleich null ist, und ein Eingabepuffer besteht, ist die Sequenz der gesamte Eingabepuffer ( [egptr](../standard-library/basic-streambuf-class.md#egptr) - [back](../standard-library/basic-streambuf-class.md#eback)-Elemente, die mit `eback` beginnen).  
  
-   Andernfalls ist die kopierte Sequenz leer.  
  
 Die zweite Memberfunktion gibt alle Sequenzen frei, die von **\*this** kontrolliert werden. Sie weist dann eine Kopie der von `_Newstr` gesteuerten Sequenz zu. Wenn **mode & ios_base::in** ungleich null ist, wird festgelegt, dass der Eingabepuffer den Lesevorgang am Anfang der Sequenz beginnt. Wenn **mode & ios_base::out** ungleich null ist, wird festgelegt, dass der Ausgabepuffer den Schreibvorgang am Anfang der Sequenz beginnt.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// basic_stringbuf_str.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <sstream>  
  
using namespace std;  
  
int main( )   
{  
   basic_string<char> i( "test" );  
   stringstream ss;  
  
   ss.rdbuf( )->str( i );  
   cout << ss.str( ) << endl;  
  
   ss << "z";  
   cout << ss.str( ) << endl;  
  
   ss.rdbuf( )->str( "be" );  
   cout << ss.str( ) << endl;  
}  
```  
  
```Output  
test  
zest  
be  
```  
  
##  <a name="traits_type"></a> basic_stringbuf::traits_type  
 Verknüpft einen Typnamen mit dem **Tr**-Vorlagenparameter.  
  
```  
typedef Tr traits_type;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ stellt ein Synonym für den Vorlagenparameter **Tr** dar.  
  
##  <a name="underflow"></a> basic_stringbuf::underflow  
 Die geschützte virtuelle Funktion versucht, das aktuelle Element aus dem Eingabestream zu extrahieren.  
  
```  
virtual int_type underflow();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion nicht erfolgreich abgeschlossen werden kann, wird **traits_type::**[eof](../standard-library/char-traits-struct.md#eof) zurückgegeben. Andernfalls wird das aktuelle Element, das konvertiert wurde, in den Eingabestream zurückgegeben.  
  
### <a name="remarks"></a>Hinweise  
 Die geschützte virtuelle Memberfunktion versucht, das aktuelle Element **byte** aus dem Eingabepuffer zu extrahieren, die aktuelle Streamposition nach vorne zu verschieben und das Element als **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#to_int_type)( **byte**) zurückzugeben. Hierfür gibt es eine Möglichkeit: Wenn eine Leseposition verfügbar ist, wird **byte** als das in der Leseposition gespeicherte Element verwendet, und der nächste Zeiger für den Eingabepuffer wird nach vorne verschoben.  
  
##  <a name="swap"></a> basic_streambuf::swap  
 Vertauscht den Inhalt dieses Zeichenfolgenpuffers mit einem anderen Zeichenfolgenpuffer.  
  
```  
void basic_stringbuf<T>::swap(basic_stringbuf& other)  
```  
  
### <a name="parameters"></a>Parameter  
 `other`  
 Der „basic_stringbuf“, dessen Inhalt mit diesem „basic_stringbuf“ getauscht wird.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="op_eq"></a> basic_stringbuf::operator=  
 Weist den Inhalt von basic_stringbuf auf der rechten Seite des Operators dem basic_stringbuf auf der linken Seite zu.  
  
```  
basic_stringbuf& basic_stringbuf:: operator=(const basic_stringbuf& other)  
```  
  
### <a name="parameters"></a>Parameter  
 `other`  
 Ein basic_stringbuf, dessen Inhalt, einschließlich Gebietsschema-Merkmalen, dem Stringbuf auf der linken Seite des Operators zugewiesen wird.  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams-Konventionen](../standard-library/iostreams-conventions.md)

