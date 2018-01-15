---
title: basic_ostringstream-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- sstream/std::basic_ostringstream
- sstream/std::basic_ostringstream::allocator_type
- sstream/std::basic_ostringstream::rdbuf
- sstream/std::basic_ostringstream::str
dev_langs: C++
helpviewer_keywords:
- std::basic_ostringstream [C++]
- std::basic_ostringstream [C++], allocator_type
- std::basic_ostringstream [C++], rdbuf
- std::basic_ostringstream [C++], str
ms.assetid: aea699f7-350f-432a-acca-adbae7b483fb
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6338ed2bbaa7d16dc2723f4bdcaa93ea0a3f3e31
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="basicostringstream-class"></a>basic_ostringstream-Klasse
Beschreibt ein Objekt, das das Einfügen von Elementen und codierten Objekten in einen Streampuffer der Klasse [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> steuert.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>  
class basic_ostringstream : public basic_ostream<Elem, Tr>  
```  
  
#### <a name="parameters"></a>Parameter  
 `Alloc`  
 Die Zuweisungsklasse.  
  
 `Elem`  
 Der Typ des grundlegenden Elements der Zeichenfolge.  
  
 *Tr*  
 Die für das grundlegende Element der Zeichenfolge spezialisierten Zeichenmerkmale.  
  
## <a name="remarks"></a>Hinweise  
 Die Klasse beschreibt ein Objekt, das das Einfügen von Elementen und codierten Objekten in einen Streampuffer steuert, der Elemente des Typs **Elem** enthält, dessen Zeichenmerkmale durch die Klasse **Tr** bestimmt sind, und dessen Elemente durch eine Zuweisung der Klasse `Alloc` zugeordnet werden. Das Objekt speichert ein Objekt der Klasse basic_stringbuf< **Elem**, **Tr**, `Alloc`>.  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[basic_ostringstream](#basic_ostringstream)|Konstruiert ein Objekt vom Typ `basic_ostringstream`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[allocator_type](#allocator_type)|Der Type stellt ein Synonym für den Vorlagenparameter `Alloc` dar.|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[rdbuf](#rdbuf)|Gibt die Adresse des gespeicherten Streampuffers des Typs `pointer` an [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`> zurück.|  
|[str](#str)|Legt den Text in einem Zeichenfolgenpuffer fest, ohne die Schreibposition zu ändern, oder ruft ihn ab.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<sstream>  
  
 **Namespace:** std  
  
##  <a name="allocator_type"></a> basic_ostringstream::allocator_type  
 Der Type stellt ein Synonym für den Vorlagenparameter `Alloc` dar.  
  
```  
typedef Alloc allocator_type;  
```  
  
##  <a name="basic_ostringstream"></a> basic_ostringstream::basic_ostringstream  
 Konstruiert ein Objekt vom Typ „basic_ostringstream“.  
  
```  
explicit basic_ostringstream(ios_base::openmode _Mode = ios_base::out);

explicit basic_ostringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::out);
```  
  
### <a name="parameters"></a>Parameter  
 `_Mode`  
 Eine der Enumerationen in [ios_base::openmode](../standard-library/ios-base-class.md#openmode).  
  
 `str`  
 Ein Objekt vom Typ `basic_string`.  
  
### <a name="remarks"></a>Hinweise  
 Der erste Konstruktor initialisiert die Basisklasse durch Aufruf von [basic_ostream](../standard-library/basic-ostream-class.md)( **sb**), bei der **sb** das gespeicherte Objekt der Klasse [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> ist. Er initialisiert außerdem **sb** durch Aufruf von basic_stringbuf< **Elem**, **Tr**, `Alloc`>( `_Mode` &#124; `ios_base::out`).  
  
 Der zweite Konstruktor initialisiert die Basisklasse durch Aufrufen von basic_ostream( **sb**). Er initialisiert außerdem **sb** durch Aufrufen von basic_stringbuf< **Elem**, **Tr**, `Alloc`>(_ *Str*, `_Mode` &#124; `ios_base::out`).  
  
##  <a name="rdbuf"></a> basic_ostringstream::rdbuf  
 Gibt die Adresse des gespeicherten Streampuffers des Typs **pointer** zurück, die ein Zeiger auf [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`> ist.  
  
```  
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Adresse des gespeicherten Streampuffers des Typs **pointer**, die ein Zeiger auf basic_stringbuf< **Elem**, **Tr**, `Alloc`> ist.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion gibt die Adresse des gespeicherten Streampuffers des Typs **pointer** an basic_stringbuf< **Elem**, **Tr**, `Alloc`> zurück.  
  
### <a name="example"></a>Beispiel  
  Sie finden ein Beispiel, in dem `rdbuf` verwendet wird, unter [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).  
  
##  <a name="str"></a> basic_ostringstream::str  
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
 Gibt ein Objekt der Klasse [basic_string](../standard-library/basic-string-class.md)< **Elem**, **Tr**, `Alloc`> zurück, dessen gesteuerte Sequenz eine Kopie der von **\*this** gesteuerten Sequenz ist.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Memberfunktion gibt [rdbuf](#rdbuf) -> [str](../standard-library/basic-stringbuf-class.md#str) zurück. Die zweite Memberfunktion ruft `rdbuf` -> **str**( `_Newstr`) auf.  
  
### <a name="example"></a>Beispiel  
  Unter [basic_stringbuf::str](../standard-library/basic-stringbuf-class.md#str) finden Sie ein Beispiel, in dem **str** verwendet wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams-Konventionen](../standard-library/iostreams-conventions.md)

