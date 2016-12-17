---
title: "Compilerwarnung (Stufe 1) C4006"
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
  - "C4006"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4006"
ms.assetid: f1a59819-0fd2-4361-8e3a-99e4b514b8e1
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4006
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#undef erwartet einen Bezeichner  
  
 Die `#undef`\-Direktive hat keinen Bezeichner zum Aufheben der Definition angegeben. Die Direktive wird ignoriert. Stellen Sie sicher, dass Sie einen Bezeichner angeben, um diese Warnung zu beheben. Im folgenden Beispiel wird C4006 generiert:  
  
```  
// C4006.cpp // compile with: /W1 #undef   // C4006 // try.. // #undef TEST int main() { }  
```