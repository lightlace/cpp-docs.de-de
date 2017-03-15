---
title: "&lt;strstream&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.<strstream>"
  - "std::<strstream>"
  - "<strstream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strstream-Header"
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# &lt;strstream&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert mehrere Klassen, die iostreams\-Vorgänge für Sequenzen unterstützt, die in einem reservierten Array des `char`\-Objekts gespeichert werden.  Solche Sequenzen sind leicht in und aus C\-Zeichenfolgen zu konvertieren.  
  
## Syntax  
  
```  
  
#include <strstream>  
  
```  
  
## Hinweise  
 Objekte vom Typ `strstream` arbeiten mit `char` \*, die C\-Zeichenfolgen darstellen.  Verwenden Sie [\<sstream\>](../standard-library/sstream.md) zum Arbeiten mit Objekten des Typs [basic\_string](../standard-library/basic-string-class.md).  
  
> [!NOTE]
>  Die Klassen in `<strstream>` sind veraltet.  Verwenden Sie stattdessen die Klassen in `<sstream>`.  
  
### Klassen  
  
|||  
|-|-|  
|[strstreambuf\-Klasse](../standard-library/strstreambuf-class.md)|Die Klasse beschreibt einen Streampuffer, der die Übertragung von Elementen in eine bzw. aus einer Sequenz von Elementen steuert, die in einem `char`\-Arrayobjekt gespeichert sind.|  
|[istrstream\-Klasse](../standard-library/istrstream-class.md)|Die Klasse beschreibt ein Objekt, das die Extraktion von Elementen und codierten Objekten aus einem Streampuffer der Klasse [strstreambuf](../standard-library/strstreambuf-class.md) steuert.|  
|[ostrstream\-Klasse](../standard-library/ostrstream-class.md)|Die Klasse beschreibt ein Objekt, das die Einfügung von Elementen und codierten Objekten in einen Streampuffer der Klasse [strstreambuf](../standard-library/strstreambuf-class.md) steuert.|  
|[strstream\-Klasse](../standard-library/strstream-class.md)|Die Klasse beschreibt ein Objekt, das die Einfügung und Extraktion von Elementen und codierten Objekten mit einem Streampuffer der Klasse [strstreambuf](../standard-library/strstreambuf-class.md) steuert.|  
  
## Siehe auch  
 [\<strstream\>](../standard-library/strstream.md)   
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)