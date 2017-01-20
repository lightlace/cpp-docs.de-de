---
title: "Linkertoolwarnung LNK4219"
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
  - "LNK4219"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4219"
ms.assetid: 363fedf4-b10c-4985-811a-55a9fba688d6
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolwarnung LNK4219
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fixup\-Name Fixup\-Überlauf.Ziel 'Zielsymbolname' ist außerhalb des Bereichs, Thunk wird eingefügt  
  
 Der Linker hat einen Thunk eingefügt, während die Adresse bzw. der Offset zu groß für die angegebene Anweisung war, da die Entfernung zwischen Zielsymbol und Anweisung zu groß ist.  
  
 Sie können die Anwendung \(z. B. mit der [\/ORDER](../../build/reference/order-put-functions-in-order.md)\-Option\) neu anordnen, um die zusätzliche Dereferenzierungsebene zu vermeiden.