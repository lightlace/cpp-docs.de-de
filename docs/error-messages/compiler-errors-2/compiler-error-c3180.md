---
title: "Compilerfehler C3180"
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
  - "C3180"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3180"
ms.assetid: 5281f583-7df7-418a-8507-d4da67ed6572
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3180
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typname' : Name übersteigt die Metadatenbegrenzung von 'Grenze' Zeichen  
  
 Der Compiler hat den Namen für einen verwalteten Typ in den Metadaten abgeschnitten.  Die Kürzung führt dazu, dass der Typ mit der `#using`\-Direktive \(bzw. ihrer Entsprechung in einer anderen Sprache\) unbrauchbar wird.  
  
 Die Beschränkung für den Typnamen bezieht sich auf alle Namespacequalifizierungen.