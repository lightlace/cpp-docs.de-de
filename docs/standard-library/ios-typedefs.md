---
title: '&lt;ios&gt;-Typedefs | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b962632-3439-44de-bf26-20c67a7f0ff3
caps.latest.revision: 13
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: d9f9dd5f13f0f4559455ff8d8cf09bab5350b1f0
ms.lasthandoff: 02/24/2017

---
# <a name="ltiosgt-typedefs"></a>&lt;ios&gt;-Typedefs
||||  
|-|-|-|  
|[ios](#ios)|[streamoff](#streamoff)|[streampos](#streampos)|  
|[streamsize](#streamsize)|[wios](#wios)|[wstreampos](#wstreampos)|  
  
##  <a name="a-nameiosa--ios"></a><a name="ios"></a> ios  
 Unterstützt die ios-Klasse aus der alten iostream-Bibliothek.  
  
```  
typedef basic_ios<char, char_traits<char>> ios;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für die Vorlagenklasse [basic_ios](../standard-library/basic-ios-class.md), die auf Elemente des Typs `char` mit Standardzeichenmerkmalen spezialisiert ist.  
  
##  <a name="a-namestreamoffa--streamoff"></a><a name="streamoff"></a> streamoff  
 Unterstützt interne Vorgänge.  
  
```  
#ifdef _WIN64  
    typedef __int64 streamoff;  
#else  
    typedef long streamoff;  
#endif  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist eine Ganzzahl mit Vorzeichen, die ein Objekt beschreibt, das einen Byte-Offset speichern kann, der an verschiedenen Streampositionierungsvorgängen beteiligt ist. Seine Repräsentation hat mindestens 32 Wertbits. Er ist nicht unbedingt groß genug, um eine willkürliche Byte-Position innerhalb eines Streams repräsentieren zu können. Der Wert **streamoff(–1)** markiert grundsätzlich einen fehlerhaften Offset.  
  
##  <a name="a-namestreamposa--streampos"></a><a name="streampos"></a> streampos  
 Enthält die aktuelle Position des Pufferzeigers oder Dateizeigers.  
  
```  
typedef fpos<mbstate_t> streampos;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für [fpo](../standard-library/fpos-class.md)< `mbstate_t`s>.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// ios_streampos.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main( )   
{  
   using namespace std;  
  
   ofstream x( "iostream.txt" );  
   x << "testing";  
   streampos y = x.tellp( );  
   cout << y << endl;  
}  
```  
  
```Output  
7  
```  
  
##  <a name="a-namestreamsizea--streamsize"></a><a name="streamsize"></a> streamsize  
 Bezeichnet die Größe des Streams.  
  
```  
#ifdef _WIN64  
    typedef __int64 streamsize;  
#else  
    typedef int streamsize;  
#endif  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist eine Ganzzahl mit Vorzeichen, die ein Objekt beschreibt, das die Anzahl von Objekten speichern kann, die an verschiedenen Streamvorgängen beteiligt sind. Seine Repräsentation verfügt über mindestens 16 Bits. Er ist nicht unbedingt groß genug, um eine willkürliche Byte-Position innerhalb eines Streams repräsentieren zu können.  
  
### <a name="example"></a>Beispiel  
  Nachdem Sie folgendes Programm kompiliert und ausgeführt haben, öffnen Sie die Datei test.txt,, um den Effekt der Einstellung `streamsize` zu überprüfen.  
  
```  
// ios_streamsize.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main( )   
{  
   using namespace std;  
   char a[16] = "any such text";  
   ofstream x( "test.txt" );  
   streamsize y = 6;  
   x.write( a, y );  
}  
```  
  
##  <a name="a-namewiosa--wios"></a><a name="wios"></a> wios  
 Unterstützt die wios-Klasse aus der alten iostream-Bibliothek.  
  
```  
typedef basic_ios<wchar_t, char_traits<wchar_t>> wios;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für die Vorlagenklasse [basic_ios](../standard-library/basic-ios-class.md), die auf Elemente des Typs `wchar_t` mit Standardzeichenmerkmalen spezialisiert ist.  
  
##  <a name="a-namewstreamposa--wstreampos"></a><a name="wstreampos"></a> wstreampos  
 Enthält die aktuelle Position des Pufferzeigers oder Dateizeigers.  
  
```  
typedef fpos<mbstate_t> wstreampos;  
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für [fpo](../standard-library/fpos-class.md)< `mbstate_t`s>.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// ios_wstreampos.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main( )   
{  
   using namespace std;  
   wofstream xw( "wiostream.txt" );  
   xw << L"testing";  
   wstreampos y = xw.tellp( );  
   cout << y << endl;  
}  
```  
  
```Output  
7  
```  
  
## <a name="see-also"></a>Siehe auch  
 [\<ios>](../standard-library/ios.md)


