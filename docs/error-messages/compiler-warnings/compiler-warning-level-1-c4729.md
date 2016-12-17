---
title: "Compilerwarnung (Stufe 1) C4729"
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
  - "C4729"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4729"
ms.assetid: 36a0151f-f258-48d9-9444-ae6d41ff70a4
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4729
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Funktion ist zu groß für auf Verlaufdiagrammen basierende Warnungen.  
  
 Diese Warnung wird ausgegeben, wenn eine Funktion zu groß ist, um sie während der Kompilierung zuverlässig auf Situationen zu überprüfen, in denen eine Warnung auftreten könnte. Diese Warnung wird nur bei Verwendung der [\/Od](../../build/reference/od-disable-debug.md)\-Compileroption generiert.  
  
 Unterteilen Sie die Funktion in kleinere Funktionen, um diese Warnung zu vermeiden.