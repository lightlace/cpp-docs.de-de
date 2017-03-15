---
title: ostreambuf_iterator-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.ostreambuf_iterator
- streambuf/std::ostreambuf_iterator
- ostreambuf_iterator
- std::ostreambuf_iterator
dev_langs:
- C++
helpviewer_keywords:
- ostreambuf_iterator class
ms.assetid: dad1e624-2f45-4e94-8887-a885e95f9071
caps.latest.revision: 16
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
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: 30e8f1c86ebff67c520f4ff303ade831306cede6
ms.lasthandoff: 02/24/2017

---
# <a name="ostreambufiterator-class"></a>ostreambuf_iterator Class
Die Vorlagenklasse ostreambuf_iterator beschreibt ein Ausgabeiteratorobjekt, das aufeinander folgende Zeichenelemente in den Ausgabestream mit der Extraktion **operator>>** schreibt. Die `ostreambuf_iterator` unterscheiden sich von denen der [ostream_iterator-Klasse](../standard-library/ostream-iterator-class.md) insofern, als dass sie über Zeichen anstelle eines generischen Typs im Hinblick auf den Objekttyp verfügen, der in den Ausgabestream eingefügt wird.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class CharType = char class Traits = char_traits <CharType>>
```  
  
#### <a name="parameters"></a>Parameter  
 `CharType`  
 Der Typ, der den Zeichentyp für das ostreambuf_iterator-Objekt darstellt. Dieses Argument ist optional, und der Standardwert ist `char`*.*  
  
 `Traits`  
 Der Typ, der den Zeichentyp für das ostreambuf_iterator-Objekt darstellt. Dieses Argument ist optional, und der Standardwert ist `char_traits`\< *CharType>.*  
  
## <a name="remarks"></a>Hinweise  
 Die ostreambuf_iterator-Klasse muss den Anforderungen für einen Ausgabeiterator entsprechen. Algorithmen können mit `ostreambuf_iterator` direkt in Ausgabestreams geschrieben werden. Die Klasse bietet einen Streamiterator auf niedriger Ebene, der Zugriff auf den unformatierten E/A-Stream in Form von Zeichen und die Fähigkeit erlaubt, die Pufferung und die Zeichenumsetzungen zu umgehen, die mit den Streamiteratoren auf hoher Ebene verbunden sind.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator)|Erstellt einen `ostreambuf_iterator`, der zum Schreiben von Zeichen in den Ausgabestream initialisiert wird.|  
  
### <a name="typedefs"></a>TypeDefs  
  
|||  
|-|-|  
|[char_type](#ostreambuf_iterator__char_type)|Ein Typ, der für den Zeichentyp von `ostreambuf_iterator` bereitgestellt wird.|  
|[ostream_type](#ostreambuf_iterator_ostream_type)|Ein Typ, der für den Streamtyp von `ostream_iterator` bereitgestellt wird.|  
|[streambuf_type](#ostreambuf_iterator__streambuf_type)|Ein Typ, der für den Streamtyp von `ostreambuf_iterator` bereitgestellt wird.|  
|[traits_type](#ostreambuf_iterator__traits_type)|Ein Typ, der für den Merkmaltyp von `ostream_iterator` bereitgestellt wird.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[failed](#ostreambuf_iterator__failed)|Testet eine Einfügung in den Ausgabestreampuffer auf Fehler.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[operator*](#ostreambuf_iterator__operator_star)|Der Dereferenzierungsoperator, der zum Implementieren des Ausgabeiteratorausdrucks *`i` = `x` verwendet wird.|  
|[operator++](#ostreambuf_iterator__operator_add_add)|Ein nicht funktionaler Inkrementoperator, der einen `ostreambuf_iterator` zum gleichen Objekt zurückgibt, das er adressiert hat, bevor der Vorgang aufgerufen wurde.|  
|[operator=](#ostreambuf_iterator__operator_eq)|Der Operator fügt ein Zeichen in den zugeordneten Streampuffer ein.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<iterator>  
  
 **Namespace:** std  
  
##  <a name="a-nameostreambufiteratorchartypea--ostreambufiteratorchartype"></a><a name="ostreambuf_iterator__char_type"></a> ostreambuf_iterator::char_type  
 Ein Typ, der für den Zeichentyp von `ostreambuf_iterator` bereitgestellt wird.  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ stellt ein Synonym für den Vorlagenparameter **CharType** dar.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// ostreambuf_iterator_char_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef ostreambuf_iterator<char>::char_type CHT1;  
   typedef ostreambuf_iterator<char>::traits_type CHTR1;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter:  
    ostreambuf_iterator< CHT1, CHTR1> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output streambuf:  
   cout << "The characters written to the output stream\n"  
        << " by charOutBuf are: ";  
 *charOutBuf = 'O';  
   charOutBuf++;  
 *charOutBuf = 'U';  
   charOutBuf++;  
 *charOutBuf = 'T';  
   charOutBuf++;  
   cout << "." << endl;  
}  
\* Output:   
The characters written to the output stream  
 by charOutBuf are: OUT.  
*\  
```  
  
##  <a name="a-nameostreambufiteratorfaileda--ostreambufiteratorfailed"></a><a name="ostreambuf_iterator__failed"></a> ostreambuf_iterator::failed  
 Testet eine Einfügung in den Ausgabestreampuffer auf Fehler.  
  
```
bool failed() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 **TRUE**, wenn vorher kein Einfügen in den Ausgabestreampuffer fehlgeschlagen ist; andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt **TRUE** zurück, sofern es sich um jede vorherige Verwendung des Members `operator=` handelt, der Aufruf von **subf**_-> `sputc` gibt **eof** zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// ostreambuf_iterator_failed.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   ostreambuf_iterator<char> charOut ( cout );  
  
 *charOut = 'a';  
   charOut ++;  
 *charOut  = 'b';  
   charOut ++;     
 *charOut = 'c';  
   cout << " are characters output individually." << endl;  
  
   bool b1 = charOut.failed ( );  
   if (b1)   
       cout << "At least one insertion failed." << endl;  
   else  
       cout << "No insertions failed." << endl;  
}  
\* Output:   
abc are characters output individually.  
No insertions failed.  
*\  
```  
  
##  <a name="a-nameostreambufiteratoroperatorstara--ostreambufiteratoroperator"></a><a name="ostreambuf_iterator__operator_star"></a> ostreambuf_iterator::operator*  
 Ein nicht funktionaler Dereferenzierungsoperator, der zum Implementieren des Ausgabeiteratorausdrucks \* *i* = *x* verwendet wird.  
  
```
ostreambuf_iterator<CharType, Traits>& operator*();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das ostreambuf-Iteratorobjekt.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Operator funktioniert nur im Ausgabeiteratorausdruck \* *i* = *x* für die Zeichenausgabe zum Streampuffer. Angewendet auf einen ostreambuf-Iterator, wird der Iterator zurückgegeben. **\*iter** gibt **iter**, zurück.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// ostreambuf_iterator_op_deref.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter  
   ostreambuf_iterator<char> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *charOutBuf = 'O';  
   charOutBuf++;   // no effect on iterator position  
 *charOutBuf = 'U';  
 *charOutBuf = 'T';  
}  
\* Output:   
Elements written to output stream:  
OUT  
*\  
```  
  
##  <a name="a-nameostreambufiteratoroperatoraddadda--ostreambufiteratoroperator"></a><a name="ostreambuf_iterator__operator_add_add"></a> ostreambuf_iterator::operator++  
 Ein nicht funktionaler Inkrementoperator, der einen ostream-Iterator zum gleichen Zeichen zurückgibt, das er adressiert hat, bevor der Vorgang aufgerufen wurde.  
  
```
ostreambuf_iterator<CharType, Traits>& operator++();
ostreambuf_iterator<CharType, Traits>& operator++(int);
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das Zeichen, das ursprünglich behandelt wurde oder auf ein durch die Implementierung definiertes Objekt, das zu `ostreambuf_iterator`\<**CharType**, **Traits**> konvertiert werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Der Operator wird zum Implementieren des Ausgabeiteratorausdrucks \* *i* = *x* verwendet.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// ostreambuf_iterator_op_incr.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter  
   ostreambuf_iterator<char> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *charOutBuf = 'O';  
   charOutBuf++;      // No effect on iterator position  
 *charOutBuf = 'U';  
 *charOutBuf = 'T';     
}  
\* Output:   
Elements written to output stream:  
OUT  
*\  
```  
  
##  <a name="a-nameostreambufiteratoroperatoreqa--ostreambufiteratoroperator"></a><a name="ostreambuf_iterator__operator_eq"></a> ostreambuf_iterator::operator=  
 Der Operator fügt ein Zeichen in den zugeordneten Streampuffer ein.  
  
```
ostreambuf_iterator<CharType, Traits>& operator=(CharType _Char);
```  
  
### <a name="parameters"></a>Parameter  
 `_Char`  
 Das in den Streampuffer einzufügende Zeichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das in den Streampuffer eingefügte Zeichen.  
  
### <a name="remarks"></a>Hinweise  
 Ein Zuweisungsoperator, der zum Implementieren des Ausgabeiteratorausdrucks \* *i* = *x* zum Schreiben in einen Ausgabestreams verwendet wird.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// ostreambuf_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter  
   ostreambuf_iterator<char> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *charOutBuf = 'O';  
   charOutBuf++;      // No effect on iterator position  
 *charOutBuf = 'U';  
 *charOutBuf = 'T';     
}  
\* Output:   
Elements written to output stream:  
OUT  
*\  
```  
  
##  <a name="a-nameostreambufiteratorostreambufiteratora--ostreambufiteratorostreambufiterator"></a><a name="ostreambuf_iterator_ostreambuf_iterator"></a> ostreambuf_iterator::ostreambuf_iterator  
 Erstellt einen `ostreambuf_iterator`, der zum Schreiben von Zeichen in den Ausgabestream initialisiert wird.  
  
```
ostreambuf_iterator(streambuf_type* strbuf) throw();
ostreambuf_iterator(ostream_type& Ostr) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `strbuf`  
 Das zur Initialiserung des Ausgabestreampufferzeigers verwendete streambuf-Ausgabeobjekt.  
  
 `Ostr`  
 Das zur Initialiserung des Ausgabestreampufferzeigers verwendete Streamausgabeobjekt.  
  
### <a name="remarks"></a>Hinweise  
 Der erste Konstruktor initialisiert den Zeiger auf den Ausgabestreampuffer mit `strbuf`.  
  
 Der zweite Konstruktor initialisiert den Zeiger auf den Ausgabestreampuffer mit `Ostr`. `rdbuf`. Der gespeicherte Zeiger darf kein NULL-Zeiger sein.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// ostreambuf_iteratorOstreambuf_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostreambuf_iterator for stream cout  
   ostreambuf_iterator<char> charOut ( cout );  
  
 *charOut = 'O';  
   charOut ++;  
 *charOut  = 'U';  
   charOut ++;     
 *charOut = 'T';  
   cout << " are characters output individually." << endl;  
  
   ostreambuf_iterator<char> strOut ( cout );  
   string str = "These characters are being written to the output stream.\n ";  
   copy ( str.begin ( ), str. end ( ), strOut );  
}  
\* Output:   
OUT are characters output individually.  
These characters are being written to the output stream.  
*\  
```  
  
##  <a name="a-nameostreambufiteratorostreamtypea--ostreambufiteratorostreamtype"></a><a name="ostreambuf_iterator_ostream_type"></a> ostreambuf_iterator::ostream_type  
 Ein Typ, der für den Streamtyp von `ostream_iterator` bereitgestellt wird.  
  
```
typedef basicOstream<CharType, Traits> ostream_type;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für `basicOstream`\< **CharType**, **Traits**>  
  
### <a name="example"></a>Beispiel  
  Unter [ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator) finden Sie ein Beispiel für das Deklarieren und Verwenden von `ostream_type`.  
  
##  <a name="a-nameostreambufiteratorstreambuftypea--ostreambufiteratorstreambuftype"></a><a name="ostreambuf_iterator__streambuf_type"></a> ostreambuf_iterator::streambuf_type  
 Ein Typ, der für den Streamtyp von `ostreambuf_iterator` bereitgestellt wird.  
  
```
typedef basic_streambuf<CharType, Traits> streambuf_type;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ ist ein Synonym für `basic_streambuf`\< **CharType**, **Merkmale**>, eine Stream-Klasse für die E/A-Puffer, die beim Spezialisieren auf den Zeichentyp `char` zu `streambuf` wird.  
  
### <a name="example"></a>Beispiel  
  Unter [ostreambuf_iterator](#ostreambuf_iterator_ostreambuf_iterator) finden Sie ein Beispiel für das Deklarieren und Verwenden von `streambuf_type`.  
  
##  <a name="a-nameostreambufiteratortraitstypea--ostreambufiteratortraitstype"></a><a name="ostreambuf_iterator__traits_type"></a> ostreambuf_iterator::traits_type  
 Ein Typ, der für den Merkmaltyp von `ostream_iterator` bereitgestellt wird.  
  
```
typedef Traits traits_type;
```  
  
### <a name="remarks"></a>Hinweise  
 Der Typ stellt ein Synonym für den Vorlagenparameter **Merkmale** dar.  
  
### <a name="example"></a>Beispiel  
  
```cpp  
// ostreambuf_iterator_traits_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef ostreambuf_iterator<char>::char_type CHT1;  
   typedef ostreambuf_iterator<char>::traits_type CHTR1;  
  
   // ostreambuf_iterator for stream cout  
   // with new line delimiter:  
    ostreambuf_iterator< CHT1, CHTR1> charOutBuf ( cout );  
  
   // Standard iterator interface for writing  
   // elements to the output streambuf:  
   cout << "The characters written to the output stream\n"  
        << " by charOutBuf are: ";  
 *charOutBuf = 'O';  
   charOutBuf++;  
 *charOutBuf = 'U';  
   charOutBuf++;  
 *charOutBuf = 'T';  
   charOutBuf++;  
   cout << "." << endl;  
}  
\* Output:   
The characters written to the output stream  
 by charOutBuf are: OUT.  
*\  
```  
  
## <a name="see-also"></a>Siehe auch  
 [\<iterator>](../standard-library/iterator.md)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)




