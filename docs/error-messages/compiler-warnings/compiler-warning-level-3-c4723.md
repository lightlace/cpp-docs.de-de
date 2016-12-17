---
title: "Compilerwarnung (Stufe 3) C4723"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C4723"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4723"
ms.assetid: 07669d14-3fd8-4a43-94bc-b61c50e58460
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 3) C4723
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mögliche Division durch Null  
  
 Der zweite Operand einer Division ergab zur Kompilierungszeit den Wert 0 und führte somit zu nicht definierten Ergebnissen.  
  
 Diese Warnung wird nur bei Verwendung von [\/Og](../../build/reference/og-global-optimizations.md) oder einer Optimierungsoption ausgegeben, die **\/Og** beinhaltet.  
  
 Möglicherweise wurde der 0\-Operand vom Compiler generiert.