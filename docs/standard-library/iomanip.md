---
title: "&lt; Iomanip &gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "iomanip/std::<iomanip>"
  - "std::<iomanip>"
  - "<iomanip>"
  - "std.<iomanip>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iomanip-Header"
ms.assetid: 3681c346-4763-4037-bba4-cf0dc3447974
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# &lt; Iomanip &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Beziehen Sie den `iostreams`\-Standardheader `<iomanip>` mit ein, um verschiedene Manipulatoren zu definieren, die jeweils ein einzelnes Argument verwenden.  
  
## Syntax  
  
```  
  
#include <iomanip>  
  
```  
  
## Hinweise  
 Jeder dieser Manipulatoren gibt einen nicht angegebenen Typ zurück, die **T1** bis **T10** genannt werden. Diese überladen `basic_istream`\<**Elem**, **Tr**\>`::`[operator\>\>](../Topic/operator%3E%3E%20\(%3Cistream%3E\).md) und `basic_ostream`\<**Elem**, **Tr**\>`::`[operator\<\<](../Topic/operator%3C%3C%20\(%3Costream%3E\).md).  
  
### Manipulatoren  
  
|||  
|-|-|  
|[get\_money](../Topic/%3Ciomanip%3E%20get_money.md)|Ruft einen Geldbetrag ab, optional in einem internationalen Format.|  
|[get\_time](../Topic/%3Ciomanip%3E%20get_time.md)|Ruft eine Uhrzeit in einer Zeitstruktur mithilfe eines angegebenen Formats ab.|  
|[put\_money](../Topic/%3Ciomanip%3E%20put_money.md)|Stellt einen Geldbetrag bereit, optional in einem internationalen Format.|  
|[put\_time](../Topic/%3Ciomanip%3E%20put_time.md)|Stellt eine Uhrzeit in einer Zeitstruktur und eine Formatzeichenfolge für die Verwendung bereit.|  
|[quoted](../Topic/quoted.md)|Ermöglicht praktische Roundtrips von Zeichenfolgen mit „insertion“ und „extraction“\-Operatoren.|  
|[resetiosflags](../Topic/resetiosflags.md)|Löscht die angegebenen Flags.|  
|[setbase](../Topic/setbase.md)|Legt die Basis für Ganzzahlen fest.|  
|[setfill](../Topic/setfill.md)|Legt das zum Auffüllen in einer rechts ausgerichteten Anzeige verwendete Zeichen fest.|  
|[setiosflags](../Topic/setiosflags.md)|Legt die angegebenen Flags fest.|  
|[setprecision](../Topic/setprecision.md)|Legt die Genauigkeit für Gleitkommawerte fest.|  
|[setw](../Topic/setw.md)|Gibt die Breite des Anzeigefelds an.|  
  
## Siehe auch  
 [Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)   
 [Threadsicherheit in der C\+\+\-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream\-Programmierung](../standard-library/iostream-programming.md)   
 [iostreams\-Konventionen](../standard-library/iostreams-conventions.md)