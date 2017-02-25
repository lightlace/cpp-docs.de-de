---
title: "ML Fatal Error A1008 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A1008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A1008"
ms.assetid: fe592f9d-c37b-4cd8-a51d-e3c15ddcab83
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Fatal Error A1008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Makro ohne Übereinstimmung einem tiefer geschachtelten**  
  
 Entweder ein Makro wurde nicht abgeschlossen, bevor das Ende der Datei oder des Direktivenprozessors endenden [ENDM](../../assembler/masm/endm.md) außerhalb eines Makros blocks gefunden wurde.  
  
 Eine Ursache dieses Fehlers ist ausgelassener Punkt vor [.REPEAT](../../assembler/masm/dot-repeat.md) oder [.WHILE](../../assembler/masm/dot-while.md).  
  
## Siehe auch  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)