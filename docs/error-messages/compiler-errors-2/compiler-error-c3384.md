---
title: "Compilerfehler C3384 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3384"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3384"
ms.assetid: c9f92c6a-62a9-4333-b2b1-bc55c7f288b6
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# Compilerfehler C3384
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"type\_parameter" : Die Werteinschränkung und die ref\-Einschränkung schließen sich gegenseitig aus  
  
 Sie können einen generischen Typ nicht gleichzeitig auf `value class` und `ref class` einschränken.  
  
 Weitere Informationen finden Sie unter [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## Beispiel  
 Im folgenden Beispiel wird C3384 generiert.  
  
```  
// C3384.cpp // compile with: /c /clr generic <typename T> where T : ref class where T : value class   // C3384 ref class List {};  
```