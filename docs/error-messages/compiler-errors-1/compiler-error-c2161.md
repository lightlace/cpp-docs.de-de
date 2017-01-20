---
title: "Compilerfehler C2161"
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
  - "C2161"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2161"
ms.assetid: d6798821-13bb-4e60-924f-85f7bf955387
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2161
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"\#\#" kann nicht am Ende einer Makrodefinition stehen  
  
 Eine Makrodefinition endete mit einem tokeneinfügenden Operator \(\#\#\).  
  
 Im folgenden Beispiel wird C2161 generiert:  
  
```  
// C2161.cpp // compile with: /c #define mac(a,b) a   // OK #define mac(a,b) a##   // C2161  
```