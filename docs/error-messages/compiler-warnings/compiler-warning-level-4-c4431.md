---
title: "Compilerwarnung (Stufe 4) C4431 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4431"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4431"
ms.assetid: 58434ab6-dd8d-427b-953a-602fb7453ae6
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerwarnung (Stufe 4) C4431
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fehlender Typspezifizierer \- int wird angenommen.Hinweis: default\-int wird von C\+\+ nicht unterstützt  
  
 Dieser Fehler kann infolge einer Verbesserung der Compilerkonformität für Visual C\+\+ 2005 ausgegeben werden: Visual C\+\+ erstellt in der Standardeinstellung keine Bezeichner ohne Typ als "int".  Der Typ eines Bezeichners muss explizit angegeben werden.  
  
 Diese Warnung ist standardmäßig deaktiviert.  Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C4431 generiert.  
  
```  
// C4431.c  
// compile with: /c /W4  
#pragma warning(default:4431)  
i;   // C4431  
int i;   // OK  
```