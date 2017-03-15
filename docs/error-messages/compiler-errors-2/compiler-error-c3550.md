---
title: "Compiler Error C3550 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3550"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3550"
ms.assetid: 9f2d5ffc-e429-41a1-89e3-7acc4fd47e14
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compiler Error C3550
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Kontext ist nur ein einfaches "decltype\(auto\)" zulässig.  
  
 Wenn `decltype(auto)` als Platzhalter für den Rückgabetyp einer Funktion dient, muss dieses allein verwendet werden.  Es kann nicht als Teil der Zeigerdeklaration \(`decltype(auto*)`\), einer Verweisdeklaration \(`decltype(auto&)`\) oder einer anderen Qualifizierung dieser Art verwendet werden.  
  
## Siehe auch  
 [auto](../../cpp/auto-cpp.md)