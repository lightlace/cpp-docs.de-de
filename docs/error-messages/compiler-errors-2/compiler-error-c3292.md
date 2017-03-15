---
title: "Compilerfehler C3292 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3292"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3292"
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
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