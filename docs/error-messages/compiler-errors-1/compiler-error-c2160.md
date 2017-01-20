---
title: "Compilerfehler C2160"
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
  - "C2160"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2160"
ms.assetid: a1f694a7-fb16-4437-b7f5-a1af6da94bc5
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2160
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"\#\#" kann nicht am Anfang einer Makrodefinition stehen  
  
 Eine Makrodefinition begann mit einem tokeneinfügenden Operator \(\#\#\).  
  
 Im folgenden Beispiel wird C2160 generiert:  
  
```  
// C2160.cpp // compile with: /c #define mac(a,b) #a   // OK #define mac(a,b) ##a   // C2160  
```