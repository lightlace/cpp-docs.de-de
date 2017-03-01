---
title: fpos-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.fpos
- std::fpos
- iosfwd/std::fpos
- fpos
dev_langs:
- C++
helpviewer_keywords:
- fpos class, about fpos class
- fpos class
ms.assetid: ffd0827c-fa34-47f4-b10e-5cb707fcde47
caps.latest.revision: 20
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
ms.sourcegitcommit: acc0ecd4edaf1e58977dcbdeb483d497a72bc4c8
ms.openlocfilehash: 35d52be41d8d8ac113d15e78196b30a02aacb415
ms.lasthandoff: 02/24/2017

---
# <a name="fpos-class"></a>fpos-Klasse
Die Vorlagenklasse beschreibt ein Objekt, das alle Informationen, die zum Wiederherstellen eines beliebigen Dateipositionsindikators innerhalb eines Streams erforderlich sind, speichern kann. Ein Objekt der Klasse fpos\< **St**> speichert effektiv mindestens zwei Memberobjekte:  
  
-   Ein Byteoffset vom Typ [streamoff](../standard-library/ios-typedefs.md#streamoff)  
  
-   Ein Konvertierungszustand, der für ein Objekt der Klasse basic_filebuf und vom Typ **St** verwendet wird, in der Regel `mbstate_t`  
  
 Es kann auch eine beliebige Dateiposition speichern, die von einem Objekt der Klasse [basic_filebuf](../standard-library/basic-filebuf-class.md) und vom Typ `fpos_t` verwendet werden kann. In einer Umgebung mit begrenzter Dateigröße werden `streamoff` und `fpos_t` jedoch manchmal synonym verwendet. In einer Umgebung ohne Streams, mit zustandsabhängiger Codierung, wird `mbstate_t` möglicherweise nicht verwendet. Daher kann die Anzahl der gespeicherten Memberobjekte variieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Statetype>  
class fpos  
```  
  
#### <a name="parameters"></a>Parameter  
 *Statetype*  
 Zustandsinformationen.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[fpos](#fpos__fpos)|Erstellt ein Objekt, das Informationen zu einer Position (Offset) in einem Stream enthält.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[seekpos](#fpos__seekpos)|Wird nur intern von der C++-Standardbibliothek verwendet. Rufen Sie diese Methode nicht aus Ihrem Code auf.|  
|[state](#fpos__state)|Legt den Konvertierungszustand fest oder gibt ihn zurück.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[operator!=](#fpos__operator_neq)|Testet Dateipositionsindikatoren auf Ungleichheit.|  
|[operator+](#fpos__operator_add)|Erhöht einen Dateipositionsindikator.|  
|[operator+=](#fpos__operator_add_eq)|Erhöht einen Dateipositionsindikator.|  
|[operator-](#fpos__operator-)|Verringert einen Dateipositionsindikator.|  
|[operator-=](#fpos__operator-_eq)|Verringert einen Dateipositionsindikator.|  
|[operator==](#fpos__operator_eq_eq)|Testet Dateipositionsindikatoren auf Gleichheit.|  
|[operator streamoff](#fpos__operator_streamoff)|Wandelt ein Objekt vom Typ `fpos` in ein Objekt vom Typ `streamoff` um.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<ios>  
  
 **Namespace:** std  
  
##  <a name="a-namefposfposa--fposfpos"></a><a name="fpos__fpos"></a> fpos::fpos  
 Erstellt ein Objekt, das Informationen zu einer Position (Offset) in einem Stream enthält.  
  
```  
fpos(streamoff _Off = 0);

fpos(Statetype _State, fpos_t _Filepos);
```  
  
### <a name="parameters"></a>Parameter  
 `_Off`  
 Der Offset in den Stream  
  
 `_State`  
 Der Startzustand des `fpos`-Objekts  
  
 *_Filepos*  
 Der Offset in den Stream  
  
### <a name="remarks"></a>Hinweise  
 Der erste Konstruktor speichert den `_Off`-Offset relativ zum Anfang der Datei und im ursprünglichen Konvertierungszustand (wenn dies gewünscht ist). Wenn `_Off` -1 ist, stellt das resultierende Objekt eine ungültige Streamposition dar.  
  
 Der zweite Konstruktor speichert ein null-Offset und das Objekt `_State`.  
  
##  <a name="a-namefposoperatorneqa--fposoperator"></a><a name="fpos__operator_neq"></a> fpos::operator!=  
 Testet Dateipositionsindikatoren auf Ungleichheit.  
  
```  
bool operator!=(const fpos<Statetype>& right) const;
```  
  
### <a name="parameters"></a>Parameter  
 ` right`  
 Der Dateipositionsindikator, gegen den verglichen werden soll  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn die Dateipositionsindikatoren nicht identisch sind, andernfalls **FALSE**  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt „**!**( **\*this ==** ` right`)“ zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// fpos_op_neq.cpp  
// compile with: /EHsc  
#include <fstream>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   fpos<int> pos1, pos2;  
   ifstream file;  
   char c;  
  
   // Compare two fpos object  
   if ( pos1 != pos2 )  
      cout << "File position pos1 and pos2 are not equal" << endl;  
   else  
      cout << "File position pos1 and pos2 are equal" << endl;  
  
   file.open( "fpos_op_neq.txt" );  
   file.seekg( 0 );   // Goes to a zero-based position in the file  
   pos1 = file.tellg( );  
   file.get( c);  
   cout << c << endl;  
  
   // Increment pos1  
   pos1 += 1;  
   file.get( c );  
   cout << c << endl;  
  
   pos1 = file.tellg( ) - fpos<int>( 2);  
   file.seekg( pos1 );  
   file.get( c );  
   cout << c << endl;  
  
   // Increment pos1  
   pos1 = pos1 + fpos<int>( 1 );  
   file.get(c);  
   cout << c << endl;  
  
   pos1 -= fpos<int>( 2 );  
   file.seekg( pos1 );  
   file.get( c );  
   cout << c << endl;  
  
   file.close( );  
}  
```  
  
##  <a name="a-namefposoperatoradda--fposoperator"></a><a name="fpos__operator_add"></a> fpos::operator+  
 Erhöht einen Dateipositionsindikator.  
  
```  
fpos<Statetype> operator+(streamoff _Off) const;
```  
  
### <a name="parameters"></a>Parameter  
 `_Off`  
 Der Offset, um den der Dateipositionsindikator erhöht werden soll  
  
### <a name="return-value"></a>Rückgabewert  
 Die Position in der Datei  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt „**fpos(\*this) +=** `_Off`“ zurück.  
  
### <a name="example"></a>Beispiel  
  Ein Beispiel für die Verwendung von `operator+` finden Sie unter [operator!=](#fpos__operator_neq).  
  
##  <a name="a-namefposoperatoraddeqa--fposoperator"></a><a name="fpos__operator_add_eq"></a> fpos::operator+=  
 Erhöht einen Dateipositionsindikator.  
  
```  
fpos<Statetype>& operator+=(streamoff _Off);
```  
  
### <a name="parameters"></a>Parameter  
 `_Off`  
 Der Offset, um den der Dateipositionsindikator erhöht werden soll  
  
### <a name="return-value"></a>Rückgabewert  
 Die Position in der Datei  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion fügt `_Off` den gespeicherten Offset-Memberobjekten hinzu und gibt dann **\*this** zurück. Für die Positionierung innerhalb einer Datei ist das Ergebnis in der Regel nur für binäre Datenströme gültig, die über keine zustandsabhängige Codierung verfügen.  
  
### <a name="example"></a>Beispiel  
  Ein Beispiel für die Verwendung von `operator+=` finden Sie unter [operator!=](#fpos__operator_neq).  
  
##  <a name="a-namefposoperator-a--fposoperator-"></a><a name="fpos__operator-"></a> fpos::operator-  
 Verringert einen Dateipositionsindikator.  
  
```  
streamoff operator-(const fpos<Statetype>& right) const;
 
fpos<Statetype> operator-(streamoff _Off) const;
```  
  
### <a name="parameters"></a>Parameter  
 ` right`  
 Dateiposition  
  
 `_Off`  
 Streamoffset  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste Memberfunktion gibt **(streamoff)\*this - (streamoff)**` right` zurück. Die zweite Memberfunktion gibt **fpos(\*this) -=** `_Off` zurück.  
  
### <a name="example"></a>Beispiel  
  Ein Beispiel für die Verwendung von `operator-` finden Sie unter [operator!=](#fpos__operator_neq).  
  
##  <a name="a-namefposoperator-eqa--fposoperator-"></a><a name="fpos__operator-_eq"></a> fpos::operator-=  
 Verringert einen Dateipositionsindikator.  
  
```  
fpos<Statetype>& operator-=(streamoff _Off);
```  
  
### <a name="parameters"></a>Parameter  
 `_Off`  
 Streamoffset  
  
### <a name="return-value"></a>Rückgabewert  
 Die Memberfunktion gibt „**fpos(\*this) -=** `_Off`“ zurück.  
  
### <a name="remarks"></a>Hinweise  
 Für die Positionierung innerhalb einer Datei ist das Ergebnis in der Regel nur für binäre Datenströme gültig, die über keine zustandsabhängige Codierung verfügen.  
  
### <a name="example"></a>Beispiel  
  Ein Beispiel für die Verwendung von `operator-=` finden Sie unter [operator!=](#fpos__operator_neq).  
  
##  <a name="a-namefposoperatoreqeqa--fposoperator"></a><a name="fpos__operator_eq_eq"></a> fpos::operator==  
 Testet Dateipositionsindikatoren auf Gleichheit.  
  
```  
bool operator==(const fpos<Statetype>& right) const;
```  
  
### <a name="parameters"></a>Parameter  
 ` right`  
 Der Dateipositionsindikator, gegen den verglichen werden soll  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn die Dateipositionsindikatoren identisch sind, andernfalls **FALSE**  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt **(streamoff)\*this == (streamoff)**` right` zurück.  
  
### <a name="example"></a>Beispiel  
  Ein Beispiel für die Verwendung von `operator+=` finden Sie unter [operator!=](#fpos__operator_neq).  
  
##  <a name="a-namefposoperatorstreamoffa--fposoperator-streamoff"></a><a name="fpos__operator_streamoff"></a> fpos::operator streamoff  
 Wandelt ein Objekt vom Typ `fpos` in ein Objekt vom Typ `streamoff` um  
  
```  
operator streamoff() const;
```  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt das gespeicherte Offset-Memberobjekt und alle zusätzlichen Offsets zurück, die als Teil des `fpos_t`-Memberobjekts gespeichert sind.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// fpos_op_streampos.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <fstream>  
  
int main( )   
{  
   using namespace std;  
   streamoff s;  
   ofstream file( "rdbuf.txt");  
  
   fpos<mbstate_t> f = file.tellp( );  
   // Is equivalent to ..  
   // streampos f = file.tellp( );  
   s = f;  
   cout << s << endl;  
}  
```  
  
```Output  
0  
```  
  
##  <a name="a-namefposseekposa--fposseekpos"></a><a name="fpos__seekpos"></a> fpos::seekpos  
 Diese Methode wird nur intern von der C++-Standardbibliothek verwendet. Rufen Sie diese Methode nicht aus Ihrem Code auf.  
  
```  
fpos_t seekpos() const;
```  
  
##  <a name="a-namefposstatea--fposstate"></a><a name="fpos__state"></a> fpos::state  
 Legt den Konvertierungszustand fest oder gibt ihn zurück.  
  
```  
Statetype state() const;

void state(Statetype _State);
```  
  
### <a name="parameters"></a>Parameter  
 `_State`  
 Der neue Konvertierungsstatus  
  
### <a name="return-value"></a>Rückgabewert  
 Der Konvertierungsstatus  
  
### <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion gibt den im **St**-Memberobjekt gespeicherten Wert zurück. Die zweite Memberfunktion speichert `_State` im **St**-Memberobjekt.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// fpos_state.cpp  
// compile with: /EHsc  
#include <ios>  
#include <iostream>  
#include <fstream>  
  
int main() {  
   using namespace std;  
   streamoff s;  
   ifstream file( "fpos_state.txt" );  
  
   fpos<mbstate_t> f = file.tellg( );  
   char ch;  
   while ( !file.eof( ) )  
      file.get( ch );  
   s = f;  
   cout << f.state( ) << endl;  
   f.state( 9 );  
   cout << f.state( ) << endl;  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams-Konventionen](../standard-library/iostreams-conventions.md)


