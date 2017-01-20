---
title: "Compilerwarnung (Stufe 3) C4023"
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
  - "C4023"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4023"
ms.assetid: 615d5374-d7c1-42eb-acfd-917c053270c8
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 3) C4023
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Symbol': Zeiger auf ein separates Segment an Funktion ohne Prototyp übergeben: Parameternummer  
  
 Die Übergabe eines basierten Zeigers an eine Funktion ohne Prototyp bewirkt, dass der Zeiger normalisiert wird. Dies kann unvorhersehbare Folgen haben.  
  
 Diese Warnung kann möglicherweise behoben werden, wenn Sie Prototypfunktionen verwenden, denen basierte Zeiger übergeben werden.