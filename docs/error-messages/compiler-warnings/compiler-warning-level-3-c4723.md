---
title: "Compilerwarnung (Stufe 3) C4723 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4723"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4723"
ms.assetid: 07669d14-3fd8-4a43-94bc-b61c50e58460
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 3) C4723
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mögliche Division durch Null  
  
 Der zweite Operand einer Division ergab zur Kompilierungszeit den Wert 0 und führte somit zu nicht definierten Ergebnissen.  
  
 Diese Warnung wird nur bei Verwendung von [\/Og](../../build/reference/og-global-optimizations.md) oder einer Optimierungsoption ausgegeben, die **\/Og** beinhaltet.  
  
 Möglicherweise wurde der 0\-Operand vom Compiler generiert.