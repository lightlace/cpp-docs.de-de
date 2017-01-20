---
title: "ML Fatal Error A1008"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "A1008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A1008"
ms.assetid: fe592f9d-c37b-4cd8-a51d-e3c15ddcab83
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# ML Fatal Error A1008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Makro ohne Übereinstimmung einem tiefer geschachtelten**  
  
 Entweder ein Makro wurde nicht abgeschlossen, bevor das Ende der Datei oder des Direktivenprozessors endenden [ENDM](../../assembler/masm/endm.md) außerhalb eines Makros blocks gefunden wurde.  
  
 Eine Ursache dieses Fehlers ist ausgelassener Punkt vor [.REPEAT](../../assembler/masm/dot-repeat.md) oder [.WHILE](../../assembler/masm/dot-while.md).  
  
## Siehe auch  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)