---
title: basic_iostream-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- istream/std::basic_iostream
- basic_iostream
- istream/std::basic_iostream::swap
dev_langs:
- C++
helpviewer_keywords:
- basic_iostream class
ms.assetid: 294b680b-eb49-4066-8db2-6d52dac9d6e3
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
ms.openlocfilehash: 3a71df6cc23c0c8f4e6faeb39474c363ed1bd412
ms.contentlocale: de-de
ms.lasthandoff: 04/29/2017

---
# <a name="basiciostream-class"></a>basic_iostream-Klasse
Eine Streamklasse für Ein- und Ausgabe.  
  
## <a name="syntax"></a>Syntax  
  
```  
template <class Elem, class Tr = char_traits<Elem>>  
class basic_iostream : public basic_istream<Elem, Tr>,  
    public basic_ostream<Elem, Tr>  
{  
public:  
    explicit basic_iostream(basic_streambuf<Elem, Tr>* strbuf);

    virtual ~basic_iostream();

};  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Vorlagenklasse beschreibt ein Objekt, das Einfügevorgänge über seine Basisklasse [basic_ostream](../standard-library/basic-ostream-class.md)< `Elem`, `Tr`>, und Extraktionen über seine Basisklasse [basic_istream](../standard-library/basic-istream-class.md)< `Elem`, `Tr`> steuert. Die beiden Objekte nutzen gemeinsam die virtuelle Basisklasse [basic_ios](../standard-library/basic-ios-class.md)< `Elem``Tr`>. Außerdem verwalten sie einen gemeinsamen Streampuffer mit Elementen des Typs `Elem`, deren Zeichenmerkmale durch die `Tr`-Klasse bestimmt sind. Der Konstruktor initialisiert seine Basisklassen über `basic_istream`( **strbuf**) und `basic_ostream`( **strbuf**).  
  
### <a name="constructors"></a>Konstruktoren  
  
|||  
|-|-|  
|[basic_iostream](#basic_iostream)|Erstellen eines `basic_iostream`-Objekts|  
  
### <a name="member-functions"></a>Memberfunktionen  
  
|||  
|-|-|  
|[swap](#swap)|Tauscht den Inhalt des bereitgestellten `basic_iostream`-Objekts mit dem Inhalt dieses Objekts aus.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[operator=](#op_eq)|Weist diesem Objekt den Wert eines angegebenen `basic_iostream`-Objekts zu . Dies ist eine Verschiebezuweisung über einen `rvalue`, die keine Kopie hinterlässt.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** \<istream>  
  
 **Namespace:** std  
  
##  <a name="basic_iostream"></a> basic_iostream::basic_iostream  
 Erstellen eines `basic_iostream`-Objekts  
  
```  
explicit basic_iostream(basic_streambuf<Elem, Tr>* strbuf);

basic_iostream(basic_iostream&& right);

basic_iostream();
```  
  
### <a name="parameters"></a>Parameter  
 `strbuf`  
 Ein vorhandenes `basic_streambuf`-Objekt.  
  
 `right`  
 Ein vorhandenes `basic_iostream`-Objekt, das verwendet wird, um ein neues `basic_iostream`-Objekt zu erstellen.  
  
### <a name="remarks"></a>Hinweise  
 Der erste Konstruktor initialisiert die Basisobjekte über `basic_istream(strbuf)` und `basic_ostream(strbuf)`.  
  
 Der zweite Konstruktor initialisiert die Basisobjekte durch Aufrufen von `move(right)`.  
  
##  <a name="op_eq"></a> basic_iostream::operator=  
 Weisen Sie diesem Objekt den Wert eines angegebenen `basic_iostream`-Objekts zu . Dies ist eine Verschiebezuweisung über einen rvalue, die keine Kopie hinterlässt.  
  
```  
basic_iostream& operator=(basic_iostream&& right);
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 Ein `rvalue`-Verweis auf ein `basic_iostream`-Objekt, aus dem zugewiesen werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Der Memberoperator ruft `swap(right)`.  
  
##  <a name="swap"></a> basic_iostream::swap  
 Tauscht den Inhalt des bereitgestellten `basic_iostream`-Objekts mit dem Inhalt dieses Objekts aus.  
  
```  
void swap(basic_iostream& right);
```  
  
### <a name="parameters"></a>Parameter  
 `right`  
 Das auszutauschende `basic_iostream`-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Die Memberfunktion ruft `swap(right)`.  
  
## <a name="see-also"></a>Siehe auch  
 [Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams-Konventionen](../standard-library/iostreams-conventions.md)


