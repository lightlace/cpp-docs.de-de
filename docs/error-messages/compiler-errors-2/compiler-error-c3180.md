---
title: "Compilerfehler C3180 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3180"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3180"
ms.assetid: 5281f583-7df7-418a-8507-d4da67ed6572
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C3180
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typname' : Name übersteigt die Metadatenbegrenzung von 'Grenze' Zeichen  
  
 Der Compiler hat den Namen für einen verwalteten Typ in den Metadaten abgeschnitten.  Die Kürzung führt dazu, dass der Typ mit der `#using`\-Direktive \(bzw. ihrer Entsprechung in einer anderen Sprache\) unbrauchbar wird.  
  
 Die Beschränkung für den Typnamen bezieht sich auf alle Namespacequalifizierungen.