---
title: "ostrstream-Klasse"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "std.oststream"
  - "oststream"
  - "std::oststream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ostrstream-Klasse"
ms.assetid: e2e34679-b266-4728-a8e1-8eda5d400e46
caps.latest.revision: 20
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# ostrstream-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt ein Objekt, das das Einfügen von Elementen und codierten Objekten in einen Streampuffer der Klasse [strstreambuf](../standard-library/strstreambuf-class.md) steuert.  
  
## Syntax  
  
```  
  
class ostrstream : public ostream  
  
```  
  
## Hinweise  
 Das Objekt speichert ein Objekt der Klasse `strstreambuf`.  
  
> [!NOTE]
>  Diese Klasse ist veraltet.  Verwenden Sie stattdessen [ostringstream](../Topic/ostringstream.md) oder [wostringstream](../Topic/wostringstream.md).  
  
### Konstruktoren  
  
|||  
|-|-|  
|[ostrstream](../Topic/ostrstream::ostrstream.md)|Konstruiert ein Objekt vom Typ `ostrstream`.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[freeze](../Topic/ostrstream::freeze.md)|Bewirkt, dass ein Streampuffer durch Streampuffervorgänge nicht verfügbar ist.|  
|[pcount](../Topic/ostrstream::pcount.md)|Gibt die Anzahl der Elemente zurück, die in die kontrollierte Sequenz geschrieben wurde.|  
|[rdbuf](../Topic/ostrstream::rdbuf.md)|Gibt einen Zeiger auf das dem Stream zugeordnete `strstreambuf`\-Objekt zurück.|  
|[str](../Topic/ostrstream::str.md)|Ruft [freeze](../Topic/strstreambuf::freeze.md) auf gibt dann einen Zeiger am Anfang der kontrollierten Sequenz zurück.|  
  
## Anforderungen  
 **Header:** \<strstream\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [ostream](../Topic/ostream.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)