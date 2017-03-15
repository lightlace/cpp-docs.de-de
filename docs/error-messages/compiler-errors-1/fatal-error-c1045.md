---
title: "Schwerwiegender Fehler C1045 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1045"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1045"
ms.assetid: 766c2f89-4ecd-4281-adaa-14b270cc0829
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Schwerwiegender Fehler C1045
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compilerlimit : Zu tiefe Schachtelung von Linkerangaben  
  
 Geschachtelte Externe überschreiten das Compilerlimit. Geschachtelte Externe sind mit dem externen Verknüpfungstyp zulässig, z. B. `extern` "C\+\+". Reduzieren Sie die Anzahl der geschachtelten Externe, um den Fehler zu beheben.