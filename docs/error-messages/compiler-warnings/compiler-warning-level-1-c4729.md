---
title: "Compilerwarnung (Stufe 1) C4729 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4729"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4729"
ms.assetid: 36a0151f-f258-48d9-9444-ae6d41ff70a4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4729
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Funktion ist zu groß für auf Verlaufdiagrammen basierende Warnungen.  
  
 Diese Warnung wird ausgegeben, wenn eine Funktion zu groß ist, um sie während der Kompilierung zuverlässig auf Situationen zu überprüfen, in denen eine Warnung auftreten könnte. Diese Warnung wird nur bei Verwendung der [\/Od](../../build/reference/od-disable-debug.md)\-Compileroption generiert.  
  
 Unterteilen Sie die Funktion in kleinere Funktionen, um diese Warnung zu vermeiden.