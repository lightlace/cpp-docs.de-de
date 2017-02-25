---
title: "Projektbuildfehler PRJ0030 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0030"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0030"
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Projektbuildfehler PRJ0030
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Makroerweiterungsfehler.Überprüfungsrekursion überschritt 32 Ebenen für $\(Makro\).  
  
 Dieser Fehler wird durch Rekursion in den Makros verursacht.  Wenn Sie die Eigenschaft **Zwischenverzeichnis** \(siehe [Eigenschaftenseite "Allgemein" \(Projekt\)](../../ide/general-property-page-project.md)\) auf **$\(IntDir\)** setzen, tritt beispielsweise eine Rekursion auf.  
  
 Um diesen Fehler zu beheben, sollten Sie Makros oder Eigenschaften nicht in Form solcher Makros definieren, zu deren Definition sie verwendet werden.