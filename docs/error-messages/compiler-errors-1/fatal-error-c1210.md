---
title: "Schwerwiegender Fehler C1210 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1210"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1210"
ms.assetid: e2208309-c284-425c-a7e8-48e96e66f35b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Schwerwiegender Fehler C1210
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/clr:pure und \/clr:safe werden von der installierten Laufzeitversion nicht unterstützt.  
  
 C1210 tritt auf, wenn Sie einen Compiler der aktuellen Version, aber eine Common Language Runtime \(CLR\) einer früheren Version verwenden.  
  
 Bestimmte Funktionen des Compilers funktionieren möglicherweise nicht in einer früheren Version der Laufzeit.  
  
 Installieren Sie die CLR\-Version, die für die Verwendung mit dem Compiler vorgesehen ist, um den Fehler C1210 zu beheben.