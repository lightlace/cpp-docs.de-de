---
title: "return-Anweisung in Programmbeendigung (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Datentypen [C++], Funktionsrückgabetypen"
  - "Funktionsrückgabetypen, return-Anweisung"
  - "return-Schlüsselwort [C++], Syntax"
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# return-Anweisung in Programmbeendigung (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Ausgabe einer `return`\-Anweisung aus **main** entspricht von der Funktion her dem Aufruf der **exit**\-Funktion.  Betrachten Sie das folgende Beispiel:  
  
```  
// return_statement.cpp  
#include <stdlib.h>  
int main()  
{  
    exit( 3 );  
    return 3;  
}  
```  
  
 Die Anweisungen **exit** sowie `return` in dem vorangegangenen Beispiel sind in ihrer Funktion identisch.  Allerdings erfordert C\+\+, dass Funktionen, die andere Rückgabetypen als `void` haben, einen Wert zurückgeben.  Mit der `return`\-Anweisung können Sie einen Wert von **Main** zurückgeben.  
  
## Siehe auch  
 [Programmbeendigung](../cpp/program-termination.md)