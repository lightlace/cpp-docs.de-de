---
title: "istrstream-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "istrstream"
  - "std::istrstream"
  - "std.istrstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "istrstream-Klasse"
ms.assetid: c2d41c75-bd2c-4437-bd77-5939ce1b97af
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# istrstream-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt ein Objekt, das die Extraktion von Elementen und codierten Objekten aus einem Streampuffer der Klasse [strstreambuf](../standard-library/strstreambuf-class.md) steuert.  
  
## Syntax  
  
```  
  
class istrstream : public istream  
  
```  
  
## Hinweise  
 Das Objekt speichert ein Objekt der Klasse `strstreambuf`.  
  
> [!NOTE]
>  Diese Klasse ist veraltet. In Betracht [istringstream](../Topic/istringstream.md) oder [wistringstream](../Topic/wistringstream.md) stattdessen.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[istrstream](../Topic/istrstream::istrstream.md)|Konstruiert ein Objekt vom Typ `istrstream`.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[rdbuf](../Topic/istrstream::rdbuf.md)|Gibt einen Zeiger auf das dem Stream zugeordnete `strstreambuf`\-Objekt zurück.|  
|[str](../Topic/istrstream::str.md)|Ruft [freeze](../Topic/strstreambuf::freeze.md) auf gibt dann einen Zeiger am Anfang der kontrollierten Sequenz zurück.|  
  
## Anforderungen  
 **Header:** \<strstream\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [istream](../Topic/istream.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)