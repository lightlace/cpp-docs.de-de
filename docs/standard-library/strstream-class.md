---
title: "strstream-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::strstream"
  - "strstream"
  - "std.strstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strstream-Klasse"
ms.assetid: 63f3be31-9e36-42b1-9715-a474a5997e2a
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# strstream-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt ein Objekt, das die Einfügung und Extraktion von Elementen und codierten Objekten mit einem Streampuffer der Klasse [strstreambuf](../standard-library/strstreambuf-class.md) steuert.  
  
## Syntax  
  
```  
  
class strstream : public iostream  
  
```  
  
## Hinweise  
 Das Objekt speichert ein Objekt der Klasse `strstreambuf`.  
  
> [!NOTE]
>  Diese Klasse ist veraltet.  Verwenden Sie stattdessen [stringstream](../Topic/stringstream.md) oder [wstringstream](../Topic/wstringstream.md).  
  
### Konstruktoren  
  
|||  
|-|-|  
|[strstream](../Topic/strstream::strstream.md)|Konstruiert ein Objekt vom Typ `strstream`.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[freeze](../Topic/strstream::freeze.md)|Bewirkt, dass ein Streampuffer durch Streampuffervorgänge nicht verfügbar ist.|  
|[pcount](../Topic/strstream::pcount.md)|Gibt die Anzahl der Elemente zurück, die in die kontrollierte Sequenz geschrieben wurde.|  
|[rdbuf](../Topic/strstream::rdbuf.md)|Gibt einen Zeiger auf das dem Stream zugeordnete `strstreambuf`\-Objekt zurück.|  
|[str](../Topic/strstream::str.md)|Ruft [freeze](../Topic/strstreambuf::freeze.md) auf gibt dann einen Zeiger am Anfang der kontrollierten Sequenz zurück.|  
  
## Anforderungen  
 **Header:** \<strstream\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [iostream](../Topic/iostream.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)