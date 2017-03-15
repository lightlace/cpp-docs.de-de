---
title: "Compilerwarnung (Stufe 1) C4006 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4006"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4006"
ms.assetid: f1a59819-0fd2-4361-8e3a-99e4b514b8e1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 1) C4006
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#undef erwartet einen Bezeichner  
  
 Die `#undef`\-Direktive hat keinen Bezeichner zum Aufheben der Definition angegeben. Die Direktive wird ignoriert. Stellen Sie sicher, dass Sie einen Bezeichner angeben, um diese Warnung zu beheben. Im folgenden Beispiel wird C4006 generiert:  
  
```  
// C4006.cpp // compile with: /W1 #undef   // C4006 // try.. // #undef TEST int main() { }  
```