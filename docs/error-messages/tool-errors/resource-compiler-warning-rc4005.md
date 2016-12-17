---
title: "Ressourcencompiler: Warnung RC4005"
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
  - "RC4005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC4005"
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Ressourcencompiler: Warnung RC4005
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"Bezeichner": Makro\-Neudefinition  
  
 Der Bezeichner wird zweimal definiert.  Die zweite Makrodefinition wurde vom Compiler verwendet.  
  
 Diese Warnung kann dann auftreten, wenn ein Makro in der Befehlszeile und im Code über eine \#define\-Direktive definiert wird.  Sie kann auch durch Makros verursacht werden, die aus Includedateien importiert werden.  
  
 Um diese Warnung zu vermeiden, entfernen Sie entweder eine der Definitionen, oder verwenden Sie eine \#undef\-Direktive vor der zweiten Definition.