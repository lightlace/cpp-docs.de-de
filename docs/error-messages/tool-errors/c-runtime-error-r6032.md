---
title: "C-Laufzeitfehler R6032 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6032"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6032"
ms.assetid: 52092a63-cc51-444a-bfc3-fad965a3558e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# C-Laufzeitfehler R6032
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht genügend Speicherplatz für Gebietsschemainformationen  
  
 Die Laufzeit verwaltet Gebietsschemainformationen auf jedem Thread, um Aufrufe von Funktionen verarbeiten zu können, die auf dem Gebietsschema basieren.  Wenn die Speicherplatzbelegung für diese Informationen fehlschlägt, kann die Laufzeit nicht fortfahren, da zu viele ihrer Basisfunktionen davon abhängen.