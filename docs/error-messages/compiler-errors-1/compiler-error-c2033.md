---
title: "Compilerfehler C2033"
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
  - "C2033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2033"
ms.assetid: fd5a1637-9db2-4c98-a7cc-b63b39737cd9
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Bitfelder dürfen keine Dereferenzierungen haben.  
  
 Das Bitfeld wurde als Zeiger deklariert, was nicht zulässig ist.  
  
 Im folgenden Beispiel wird C2033 generiert:  
  
```  
// C2033.cpp struct S { int *b : 1;  // C2033 };  
```  
  
 Mögliche Lösung:  
  
```  
// C2033b.cpp // compile with: /c struct S { int b : 1; };  
```