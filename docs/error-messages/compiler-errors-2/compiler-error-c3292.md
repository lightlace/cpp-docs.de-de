---
title: "Compilerfehler C3292"
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
  - "C3292"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3292"
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3292
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der cli\-Namespace kann nicht erneut geöffnet werden.  
  
 Der cli\-Namespace kann nicht in Ihrem Code deklariert werden.  Weitere Informationen finden Sie unter [Platform, default, and cli Namespaces](../../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3292 generiert:  
  
```  
// C3292.cpp // compile with: /clr /c namespace cli {};   // C3292  
```