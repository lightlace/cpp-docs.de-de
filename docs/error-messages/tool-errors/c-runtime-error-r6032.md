---
title: "C-Laufzeitfehler R6032"
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
  - "R6032"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6032"
ms.assetid: 52092a63-cc51-444a-bfc3-fad965a3558e
caps.latest.revision: 7
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# C-Laufzeitfehler R6032
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht genügend Speicherplatz für Gebietsschemainformationen  
  
 Die Laufzeit verwaltet Gebietsschemainformationen auf jedem Thread, um Aufrufe von Funktionen verarbeiten zu können, die auf dem Gebietsschema basieren.  Wenn die Speicherplatzbelegung für diese Informationen fehlschlägt, kann die Laufzeit nicht fortfahren, da zu viele ihrer Basisfunktionen davon abhängen.