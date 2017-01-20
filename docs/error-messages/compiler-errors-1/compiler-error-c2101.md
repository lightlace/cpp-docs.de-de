---
title: "Compilerfehler C2101"
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
  - "C2101"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2101"
ms.assetid: 42f0136f-8cc1-4f2b-be1c-721ec9278e66
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2101
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"&" auf Konstante  
  
 Der address\-of\-Operator \(`&`\) muss einen l\-Wert als Operanden haben.  
  
 Im folgenden Beispiel wird C2101 generiert:  
  
```  
// C2101.cpp int main() { char test; test = &'a';   // C2101 test = 'a';   // OK }  
```