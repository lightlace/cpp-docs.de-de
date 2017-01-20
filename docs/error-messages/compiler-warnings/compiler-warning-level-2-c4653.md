---
title: "Compilerwarnung (Stufe 2) C4653"
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
  - "C4653"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4653"
ms.assetid: 90ec3317-3d39-4b4c-bcd1-97e7c799e1b6
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 2) C4653
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compileroption 'Option' steht in Konflikt mit der vorkompilierten Headerdatei; aktuelle Befehlszeilenoption wird ignoriert  
  
 Eine mit der [\/Yu](../../build/reference/yu-use-precompiled-header-file.md)\-Option \(Vorkompilierten Header verwenden\) angegebene Option und die beim Erstellen des vorkompilierten Headers angegebenen Optionen sind inkonsistent.  Bei dieser Kompilierung wurde die Option verwendet, die bei der Erstellung des vorkompilierten Headers festgelegt wurde.  
  
 Diese Warnung kann auftreten, wenn während der Kompilierung des vorkompilierten Headers ein abweichender Wert für die Option "Pack Structures" \([\/Zp](../../build/reference/zp-struct-member-alignment.md)\) angegeben wurde.