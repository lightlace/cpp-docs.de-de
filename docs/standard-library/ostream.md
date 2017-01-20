---
title: "&lt;ostream&gt;"
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
  - "std.<ostream>"
  - "<ostream>"
  - "ostream/std::<ostream>"
  - "std::<ostream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ostream-Header"
ms.assetid: 90c3b6fb-57cd-4ae7-99b8-8512f24a67d2
caps.latest.revision: 20
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# &lt;ostream&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert die Vorlagenklasse [basic\_ostream](../standard-library/basic-ostream-class.md), die Einfügungen für die iostreams vermittelt.  Der Header definiert auch mehrere verwandte Manipulatoren.  Dieser Header wird in der Regel von einem der anderen iostreams\-Header für Sie eingefügt.  Sie müssen ihn nur selten direkt einfügen.\)  
  
## Syntax  
  
```  
  
#include <ostream>  
  
```  
  
### TypeDefs  
  
|||  
|-|-|  
|[ostream](../Topic/ostream.md)|Erstellt einen Typ aus `basic_ostream`, der auf `char` spezialisiert ist, und `char_traits`, spezialisiert auf `char`.|  
|[wostream](../Topic/wostream.md)|Erstellt einen Typ aus `basic_ostream`, der auf `wchar_t` spezialisiert ist, und `char_traits`, spezialisiert auf `wchar_t`.|  
  
### Manipulatoren  
  
|||  
|-|-|  
|[endl](../Topic/endl.md)|Beendet eine Zeile und leert den Puffer.|  
|[Ends](../Topic/ends%20\(Standard%20C++%20Library\).md)|Beendet eine Zeichenfolge.|  
|[flush](../Topic/flush%20\(Standard%20C++%20Library\).md)|Leert den Puffer.|  
||Tauscht die Werte des linken `basic_ostream`\-Objektparameters gegen diejenigen des rechten `basic_ostream`\-Objektparameters aus.|  
  
### Operatoren  
  
|||  
|-|-|  
|[Operator \<\<](../Topic/operator%3C%3C%20\(%3Costream%3E\).md)|Schreibt verschiedene Typen in den Stream.|  
  
### Klassen  
  
|||  
|-|-|  
|[basic\_ostream](../standard-library/basic-ostream-class.md)|Die Vorlagenklasse beschreibt ein Objekt, das das Einfügen von Elementen und codierten Objekten in einen Streampuffer steuert.|  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)