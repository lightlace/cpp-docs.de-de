---
title: "break-Anweisung (C) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "break"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "break-Schlüsselwort [C]"
ms.assetid: 015627c7-0924-49b2-a4d1-c77edf5eae6a
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# break-Anweisung (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die `break`\-Anweisung beendet die Ausführung der nächsten einschließenden `do`, `for`, `switch` oder `while`\-Anweisung, in der sie angezeigt wird.  Das Steuerelement wird an die Anweisung übergeben, die auf die beendete Anweisung folgt.  
  
## Syntax  
 *Sprunganweisung*:  
 `break;`  
  
 Die Anweisung `break` wird häufig verwendet, um die Verarbeitung eines besonderen Falls in einer `switch`\-Anweisung zu beenden.  Eine fehlende iterative oder `switch`\-Anweisung generiert einen Fehler.  
  
 Innerhalb von geschachtelten Anweisungen beendet die `break`\-Anweisung lediglich die Anweisung `do`, `for`, `switch` oder `while`, von der sie direkt eingeschlossen ist.  Sie können eine `return`\-Anweisung oder eine `goto`\-Anweisung verwenden, um das Steuerelement aus der geschachtelten Struktur an einen anderen Ort zu übertragen.  
  
 In diesem Beispiel wird die `break`\-Anweisung veranschaulicht.  
  
```  
#include <stdio.h>  
int main() {  
   char c;  
   for(;;) {  
      printf_s( "\nPress any key, Q to quit: " );  
  
      // Convert to character value  
      scanf_s("%c", &c);  
      if (c == 'Q')  
          break;  
   }  
} // Loop exits only when 'Q' is pressed  
```  
  
## Siehe auch  
 [break\-Anweisung](../cpp/break-statement-cpp.md)