---
title: "Compilerwarnung (Stufe 1) C4810 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4810"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4810"
ms.assetid: 39e2cae0-9c1c-4ac1-aaa0-5f661d06085b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4810
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wert von pragma pack\(show\) \=\= n  
  
 Diese Warnung wird ausgegeben, wenn Sie die **show**\-Option des [pack](../../preprocessor/pack.md)\-Pragmas verwenden.*n* ist der aktuelle pack\-Wert.  
  
 Der folgende Code zeigt z. B. die Funktionsweise der C4810\-Warnung mit dem pack\-Pragma:  
  
```  
// C4810.cpp // compile with: /W1 /LD // C4810 expected #pragma pack(show) #pragma pack(4) #pragma pack(show)  
```