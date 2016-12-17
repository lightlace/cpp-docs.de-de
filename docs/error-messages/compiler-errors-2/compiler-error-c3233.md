---
title: "Compilerfehler C3233"
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
  - "C3233"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3233"
ms.assetid: a9210830-1136-4f02-ba41-030c85f93547
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3233
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„type“: Der generische Typparameter wird bereits eingeschränkt.  
  
 Es ist nicht zulässig, einen generischen Parameter in mehr als einer `where`\-Klausel einzuschränken.  
  
 Im folgenden Beispiel wird C3233 generiert:  
  
```  
// C3233.cpp // compile with: /clr /LD interface struct C {}; interface struct D {}; generic <class T> where T : C where T : D ref class E {};   // C3233  
```