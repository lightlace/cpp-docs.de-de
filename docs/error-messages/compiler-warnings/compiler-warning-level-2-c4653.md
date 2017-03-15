---
title: "Compilerwarnung (Stufe 2) C4653 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4653"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4653"
ms.assetid: 90ec3317-3d39-4b4c-bcd1-97e7c799e1b6
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 2) C4653
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compileroption 'Option' steht in Konflikt mit der vorkompilierten Headerdatei; aktuelle Befehlszeilenoption wird ignoriert  
  
 Eine mit der [\/Yu](../../build/reference/yu-use-precompiled-header-file.md)\-Option \(Vorkompilierten Header verwenden\) angegebene Option und die beim Erstellen des vorkompilierten Headers angegebenen Optionen sind inkonsistent.  Bei dieser Kompilierung wurde die Option verwendet, die bei der Erstellung des vorkompilierten Headers festgelegt wurde.  
  
 Diese Warnung kann auftreten, wenn während der Kompilierung des vorkompilierten Headers ein abweichender Wert für die Option "Pack Structures" \([\/Zp](../../build/reference/zp-struct-member-alignment.md)\) angegeben wurde.