---
title: "&lt; Istream &gt;"
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
  - "istream/std::<istream>"
  - "std.<istream>"
  - "<istream>"
  - "std::<istream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "istream-Header"
ms.assetid: efcf24e4-05d1-4719-ab0b-9e7ebe845d89
caps.latest.revision: 20
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# &lt; Istream &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert die Vorlagenklasse basic\_istream, die Extraktionen für die Iostreams vermittelt, und die Vorlagenklasse basic\_iostream, die Einfügungen und Extraktionen vermittelt. Der Header definiert auch einen verknüpften Manipulator. Diese Headerdatei wird in der Regel von einem anderen Iostreams\-Header eingeschlossen. Sie müssen sie nur selten direkt einschließen.  
  
## Syntax  
  
```  
  
#include <istream>  
  
```  
  
### TypeDefs  
  
|||  
|-|-|  
|[iostream](../Topic/iostream.md)|Ein `basic_iostream`\-Typ, der auf `char` spezialisiert ist.|  
|[istream](../Topic/istream.md)|Ein `basic_istream`\-Typ, der auf `char` spezialisiert ist.|  
|[wiostream](../Topic/wiostream.md)|Ein `basic_iostream`\-Typ, der auf **wchar** spezialisiert ist.|  
|[wistream](../Topic/wistream.md)|Ein `basic_istream`\-Typ, der auf **wchar** spezialisiert ist.|  
  
### Manipulatoren  
  
|||  
|-|-|  
|[ws](../Topic/ws.md)|Überspringt Leerraum im Datenstrom.|  
|[swap](../Topic/%3Cistream%3E%20swap.md)|Tauscht zwei Streamobjekte.|  
  
### Operatoren  
  
|||  
|-|-|  
|[Operator \>\>](../Topic/operator%3E%3E%20\(%3Cistream%3E\).md)|Extrahiert von Zeichenfolgen und Zeichen aus dem Stream.|  
  
### Klassen  
  
|||  
|-|-|  
|[basic\_iostream](../standard-library/basic-iostream-class.md)|Eine Streamklasse für Ein\- und Ausgabe.|  
|[basic\_istream](../standard-library/basic-istream-class.md)|Die Vorlagenklasse beschreibt ein Objekt, das das Extrahieren von Elementen und codierten Objekten aus einem Streampuffer mit Elementen vom Typ **Elem** steuert, der auch als [char\_type](../Topic/basic_ios::char_type.md) bekannt ist, und dessen Zeichenmerkmale von der Klasse **Tr** bestimmt werden, die auch als [traits\_type](../Topic/basic_ios::traits_type.md) bekannt ist.|  
  
## Siehe auch  
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)