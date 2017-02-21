---
title: "Ressourcencompiler: Warnung RC4005 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC4005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC4005"
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ressourcencompiler: Warnung RC4005
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Bezeichner": Makro\-Neudefinition  
  
 Der Bezeichner wird zweimal definiert.  Die zweite Makrodefinition wurde vom Compiler verwendet.  
  
 Diese Warnung kann dann auftreten, wenn ein Makro in der Befehlszeile und im Code über eine \#define\-Direktive definiert wird.  Sie kann auch durch Makros verursacht werden, die aus Includedateien importiert werden.  
  
 Um diese Warnung zu vermeiden, entfernen Sie entweder eine der Definitionen, oder verwenden Sie eine \#undef\-Direktive vor der zweiten Definition.