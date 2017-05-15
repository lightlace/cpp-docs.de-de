---
title: ostrstream-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ostrstream
- strstream/std::ostrstream::freeze
- strstream/std::ostrstream::pcount
- strstream/std::ostrstream::rdbuf
- strstream/std::ostrstream::str
dev_langs:
- C++
helpviewer_keywords:
- ostrstream class
ms.assetid: e2e34679-b266-4728-a8e1-8eda5d400e46
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 2ed85552778f3bbf7346001e4dd4c858177ce49b
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="ostrstream-class"></a>ostrstream-Klasse
Beschreibt ein Objekt, das das Einfügen von Elementen und programmierten Objekten in einen Streampuffer der Klasse [strstreambuf](../standard-library/strstreambuf-class.md) steuert.  
  
## <a name="syntax"></a>Syntax  
  
```
class ostrstream : public ostream
```  
  
## <a name="remarks"></a>Hinweise  
 Das Objekt speichert ein Objekt der Klasse `strstreambuf`.  
  
> [!NOTE]
>  Diese Klasse ist veraltet. Verwenden Sie stattdessen [ostringstream](../standard-library/sstream-typedefs.md#ostringstream) oder [wostringstream](../standard-library/sstream-typedefs.md#wostringstream).  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[ostrstream](#ostrstream)|Konstruiert ein Objekt vom Typ `ostrstream`.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[freeze](#freeze)|Bewirkt, dass ein Streampuffer durch Streampuffervorgänge nicht verfügbar ist.|  
|[pcount](#pcount)|Gibt die Anzahl der Elemente zurück, die in die kontrollierte Sequenz geschrieben wurde.|  
|[rdbuf](#rdbuf)|Gibt einen Zeiger auf das dem Stream zugeordnete `strstreambuf`-Objekt zurück.|  
|[str](#str)|Ruft [freeze](../standard-library/strstreambuf-class.md#freeze) auf gibt dann einen Zeiger am Anfang der kontrollierten Sequenz zurück.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<strstream>  
  
 **Namespace:** std  
  
##  <a name="freeze"></a> ostrstream::freeze  
 Bewirkt, dass ein Streampuffer durch Streampuffervorgänge nicht verfügbar ist.  
  
```
void freeze(bool _Freezeit = true);
```  
  
### <a name="parameters"></a>Parameter  
 `_Freezeit`  
 Ein `bool`, der angibt, ob der Stream fixiert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion ruft [rdbuf](#rdbuf) -> [freeze](../standard-library/strstreambuf-class.md#freeze)(_ *Freezeit*) auf.  
  
### <a name="example"></a>Beispiel  
  Ein Beispiel, das **freeze** verwendet, finden Sie unter [strstream::freeze](../standard-library/strstreambuf-class.md#freeze).  
  
##  <a name="ostrstream"></a> ostrstream::ostrstream  
 Konstruiert ein Objekt vom Typ `ostrstream`.  
  
```
ostrstream();

ostrstream(char* ptr,
    streamsize count,
    ios_base::openmode _Mode = ios_base::out);
```  
  
### <a name="parameters"></a>Parameter  
 `ptr`  
 Der Puffer.  
  
 `count`  
 Die Größe des Puffers in Byte.  
  
 `_Mode`  
 Der Eingabe- und Ausgabemodus des Puffers. Weitere Informationen finden Sie unter [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
### <a name="remarks"></a>Hinweise  
 Beide Konstruktoren initialisieren die Basisklasse durch Aufrufen von [ostream](../standard-library/ostream-typedefs.md#ostream)( **sb**), wobei **sb** das gespeicherte Objekt der Klasse [strstreambuf](../standard-library/strstreambuf-class.md) ist. Der erste Konstruktor initialisiert zudem **sb** durch Aufrufen von `strstreambuf`. Der zweite Konstruktor initialisiert die Basisklasse auf einer von zwei Arten:  
  
-   Wenn `_Mode` & **ios_base::app**== 0, dann muss `ptr` das erste Element eines Arrays von `count`-Elementen festlegen, und der Konstruktor ruft `strstreambuf`( `ptr`, `count`, `ptr`) auf.  
  
-   Andernfalls muss `ptr` das erste Element eines Arrays an count-Elementen bezeichnen, die eine C-Zeichenfolge enthält, deren erstes Element von `ptr` bezeichnet wird und der Konstruktor ruft `strstreambuf`( `ptr`, `count`, `ptr`  +  `strlen`( `ptr`)) auf.  
  
##  <a name="pcount"></a> ostrstream::pcount  
 Gibt die Anzahl der Elemente zurück, die in die kontrollierte Sequenz geschrieben wurde.  
  
```
streamsize pcount() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente, die in die kontrollierte Sequenz geschrieben wurden.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [rdbuf](#rdbuf) -> [pcount](../standard-library/strstreambuf-class.md#pcount) zurück.  
  
### <a name="example"></a>Beispiel  
  Siehe [strstream::pcount](../standard-library/strstreambuf-class.md#pcount) für ein Beispiel, das `pcount` verwendet.  
  
##  <a name="rdbuf"></a> ostrstream::rdbuf  
 Gibt einen Zeiger auf das dem Stream zugeordnete strstreambuf-Objekt zurück.  
  
```
strstreambuf *rdbuf() const
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das dem Stream zugeordnete strstreambuf-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt die Adresse des gespeicherten Streampuffers des Typs **pointer** auf [strstreambuf](../standard-library/strstreambuf-class.md) zurück.  
  
### <a name="example"></a>Beispiel  
  Ein Beispiel, das `rdbuf` verwendet, finden Sie unter [strstreambuf::pcount](../standard-library/strstreambuf-class.md#pcount).  
  
##  <a name="str"></a> ostrstream::str  
 Ruft [freeze](../standard-library/strstreambuf-class.md#freeze) auf und gibt anschließend einen Zeiger zum Anfang der kontrollierten Sequenz zurück.  
  
```
char *str();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf den Anfang der kontrollierten Sequenz.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt [rdbuf](#rdbuf) -> [str](../standard-library/strstreambuf-class.md#str) zurück.  
  
### <a name="example"></a>Beispiel  
  Unter [strstream::str](../standard-library/strstreambuf-class.md#str) finden Sie ein Beispiel, das **str** verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [ostream](../standard-library/ostream-typedefs.md#ostream)   
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams-Konventionen](../standard-library/iostreams-conventions.md)




