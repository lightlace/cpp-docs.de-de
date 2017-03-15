---
title: "strstreambuf-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.strstreambuf"
  - "strstreambuf"
  - "std::strstreambuf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strstreambuf-Klasse"
ms.assetid: b040b8ea-0669-4eba-8908-6a9cc159c54b
caps.latest.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 25
---
# strstreambuf-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beschreibt einen Streampuffer, der die Übertragung von Elementen in eine bzw. aus einer Sequenz von Elementen steuert, die in einem `char`\-Arrayobjekt gespeichert sind.  
  
## Syntax  
  
```  
  
class strstreambuf : public streambuf  
  
```  
  
## Hinweise  
 Je nachdem, wie das Objekt aufgebaut ist, kann es nach Bedarf reserviert, erweitert und freigegeben werden, um Änderungen in der Sequenz zu berücksichtigen.  
  
 Ein aus der Klasse `strstreambuf` abgeleitetes Objekt speichert mehrere Bits mit Modusinformationen als seinen `strstreambuf`\-Modus. Diese Bits geben an, ob Folgendes für die gesteuerte Sequenz zutrifft:  
  
-   Sie wurde reserviert und muss schließlich freigegeben werden.  
  
-   Sie kann geändert werden.  
  
-   Sie kann durch erneute Reservierung von Speicher erweitert werden.  
  
-   Sie wurde eingefroren und muss daher „aufgetaut“ werden, bevor das Objekt zerstört wird, oder sie muss \(sofern reserviert\) durch ein Element freigegeben werden, das nicht mit dem Objekt identisch ist.  
  
 Eine gesteuerte Sequenz, die eingefroren ist, kann weder geändert noch erweitert werden, unabhängig vom Status dieser einzelnen Modusbits.  
  
 Das Objekt speichert auch Zeiger auf zwei Funktionen, mit denen die `strstreambuf`\-Speicherbelegung gesteuert wird. Sind diese Zeiger NULL\-Zeiger, muss für das Objekt eine eigene Methode des Belegens und Freigebens von Speicher für die gesteuerte Sequenz formuliert sein.  
  
> [!NOTE]
>  Diese Klasse ist veraltet. In Betracht [stringbuf](../Topic/stringbuf.md) oder [wstringbuf](../Topic/wstringbuf.md) stattdessen.  
  
### Konstruktoren  
  
|||  
|-|-|  
|[strstreambuf](../Topic/strstreambuf::strstreambuf.md)|Konstruiert ein Objekt vom Typ `strstreambuf`.|  
  
### Memberfunktionen  
  
|||  
|-|-|  
|[freeze](../Topic/strstreambuf::freeze.md)|Bewirkt, dass ein Streampuffer durch Streampuffervorgänge nicht verfügbar ist.|  
|[Überlauf](../Topic/strstreambuf::overflow.md)|Eine geschützte virtuelle Funktion, die aufgerufen werden kann, wenn ein neues Zeichen in einen vollen Puffer eingefügt wird.|  
|[pbackfail](../Topic/strstreambuf::pbackfail.md)|Eine geschützte virtuelle Memberfunktion, die versucht, ein Element in den Eingabestreams zurückzuschreiben, und es dann zum aktuellen Element macht \(auf das der nächste Zeiger zeigt\).|  
|[pcount](../Topic/strstreambuf::pcount.md)|Gibt die Anzahl der Elemente zurück, die in die kontrollierte Sequenz geschrieben wurde.|  
|[seekoff](../Topic/strstreambuf::seekoff.md)|Eine geschützte virtuelle Memberfunktion, die versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.|  
|[seekpos](../Topic/strstreambuf::seekpos.md)|Eine geschützte virtuelle Memberfunktion, die versucht, die aktuellen Positionen für die gesteuerten Streams zu ändern.|  
|[str](../Topic/strstreambuf::str.md)|Ruft [freeze](../Topic/strstreambuf::freeze.md) auf gibt dann einen Zeiger am Anfang der kontrollierten Sequenz zurück.|  
|[underflow](../Topic/strstreambuf::underflow.md)|Eine geschützte virtuelle Funktion zum Extrahieren des aktuellen Elements aus dem Eingabestream.|  
  
## Anforderungen  
 **Header:** \<strstream\>  
  
 **Namespace:** std  
  
## Siehe auch  
 [streambuf](../Topic/streambuf.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)