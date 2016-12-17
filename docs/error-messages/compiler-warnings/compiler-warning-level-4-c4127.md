---
title: "Compilerwarnung (Stufe 4) C4127"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C4127"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4127"
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
caps.latest.revision: 12
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4127
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Bedingter Ausdruck ist konstant  
  
 Der Kontrollausdruck einer `if`\-Anweisung oder `while`\-Schleife wird in eine Konstante ausgewertet. Wenn der Kontrollausdruck einer `while`\-Schleife eine Konstante ist, da die Schleife in der Mitte beendet wird, können Sie die `while`\-Schleife durch eine `for`\-Schleife ersetzen. Sie können die Initialisierung, den Beendigungstest und die Schleifenerhöhung einer `for`\-Schleife auslassen, wodurch die Schleife zu einer unendlichen Schleife wird \(wie `while(1)`\). Sie können die Schleife dann über den Text der `for`\-Anweisung beenden.  
  
 Im folgenden Beispiel wird C4127 generiert.  
  
```  
// C4127.cpp // compile with: /W4 #include <stdio.h> int main() { if (1 == 1) {}   // C4127 while (1) { break; }   // C4127 // OK for ( ; ; ) { printf("test\n"); break; } }  
```