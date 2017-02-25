---
title: "Schwerwiegender Fehler C1208 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1208"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1208"
ms.assetid: 4eefd8f0-5c2e-4a11-9e63-293e1139db65
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Schwerwiegender Fehler C1208
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das Zuordnen von Verweisklassen im Stapel wird von der installierten Laufzeitversion nicht unterstützt.  
  
 C1208 tritt auf, wenn Sie einen Compiler der aktuellen Version, aber eine Common Language Runtime \(CLR\) einer früheren Version verwenden.  
  
 Bestimmte Funktionen des Compilers funktionieren möglicherweise nicht in einer früheren Version der Laufzeit.  
  
 Installieren Sie die CLR\-Version, die für die Verwendung mit dem Compiler vorgesehen ist.