---
title: "Compilerfehler C2378 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2378"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2378"
ms.assetid: 507a91c6-ca72-48df-b3a4-2cf931c86806
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Compilerfehler C2378
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Bezeichner": Neudefinition; Symbol kann nicht mit typedef überladen werden  
  
 Der Bezeichner wurde als eine `typedef` neu definiert.  
  
 Im folgenden Beispiel wird C2378 generiert:  
  
```  
// C2378.cpp // compile with: /c int i; typedef int i;   // C2378 typedef int b;   // OK  
```