---
title: "Compilerwarnung (Stufe 1) C4138 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4138"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4138"
ms.assetid: 65ebf929-bba0-4237-923b-c1b66adfe17d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4138
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"\*\/" wurde außerhalb des Kommentars gefunden  
  
 Dem schließenden Kommentartrennzeichen geht kein öffnendes Kommentartrennzeichen voran. Der Compiler nimmt an, dass zwischen dem Sternchen \(**\***\) und dem Schrägstrich \(\/\) ein Leerzeichen steht.  
  
## Beispiel  
  
```  
// C4138a.cpp // compile with: /W1 int */*comment*/ptr;   // C4138 Ambiguous first delimiter causes warning int main() { }  
```  
  
 Diese Warnung kann auf den Versuch zurückzuführen sein, Kommentare zu schachteln.  
  
 Die Warnung kann behoben werden, wenn Sie Codeabschnitte, die Kommentare enthalten, auskommentieren, den Code in einen **\#if\/\#endif**\-Block einschließen und den steuernden Ausdruck auf 0 \(null\) festlegen:  
  
```  
// C4138b.cpp // compile with: /W1 #if 0 int my_variable;   /* Declaration currently not needed */ #endif int main() { }  
```