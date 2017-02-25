---
title: "Linkertoolwarnung LNK4219 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4219"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4219"
ms.assetid: 363fedf4-b10c-4985-811a-55a9fba688d6
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Linkertoolwarnung LNK4219
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fixup\-Name Fixup\-Überlauf.Ziel 'Zielsymbolname' ist außerhalb des Bereichs, Thunk wird eingefügt  
  
 Der Linker hat einen Thunk eingefügt, während die Adresse bzw. der Offset zu groß für die angegebene Anweisung war, da die Entfernung zwischen Zielsymbol und Anweisung zu groß ist.  
  
 Sie können die Anwendung \(z. B. mit der [\/ORDER](../../build/reference/order-put-functions-in-order.md)\-Option\) neu anordnen, um die zusätzliche Dereferenzierungsebene zu vermeiden.