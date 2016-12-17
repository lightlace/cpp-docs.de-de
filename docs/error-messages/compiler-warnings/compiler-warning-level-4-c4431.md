---
title: "Compilerwarnung (Stufe 4) C4431"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4431"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4431"
ms.assetid: 58434ab6-dd8d-427b-953a-602fb7453ae6
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
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