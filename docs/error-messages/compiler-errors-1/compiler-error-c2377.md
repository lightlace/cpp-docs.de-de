---
title: "Compilerfehler C2377 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2377"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2377"
ms.assetid: f7660965-bf4c-4cd9-8307-1bd7016678a1
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2377
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Neudefinition. Typdefinition kann nicht mit einem anderen Symbol überladen werden.  
  
 Ein `typedef`\-Bezeichner wird neu definiert.  
  
 Im folgenden Beispiel wird C2377 generiert:  
  
```  
// C2377.cpp // compile with: /c typedef int i; int i;   // C2377 int j;   // OK  
```