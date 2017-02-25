---
title: "ML Nonfatal Error A2096 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A2096"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2096"
ms.assetid: bab0b5ee-b39f-4e44-a41a-3f949fab4297
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Nonfatal Error A2096
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Segment, Gruppe oder Segmentregister erwartet**  
  
 Ein Segment oder eine Gruppe waren, erwartet wurde jedoch nicht gefunden.  
  
 Eines der folgenden Schritte ausgeführt:  
  
-   Der linke Operand für den Segmentüberschreibungsoperator \(**:**\) angegeben wurde, war kein Segmentregister \(CS \(DS, SS, ES, FS\), GS oder Gruppenname, oder Segment des Segments Ausdruck.  
  
-   Die [Herstellen einer Verbindung mit NEHMEN](../../assembler/masm/assume.md)\-Direktive war ein Segmentregister ohne eine gültige Segment adresse, Segmentregister, Gruppe oder die spezielle **FLAT** Gruppe angegeben.  
  
## Siehe auch  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)