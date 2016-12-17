---
title: "Projektbuildfehler PRJ0013"
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
  - "PRJ0013"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0013"
ms.assetid: 95e7bafd-63c8-4b2d-b778-f19cdf9ba36c
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Projektbuildfehler PRJ0013
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Möglicherweise sind nicht genügend Systemressourcen vorhanden.Ein Pipe, der zum Starten eines Builds erforderlich ist, konnte nicht erstellt werden.  
  
 Dieser Fehler weist darauf hin, dass möglicherweise nicht genügend Systemressourcen vorhanden sind.  Sie können diesen Fehler beheben, indem Sie die Systemressourcenauslastung durch andere Prozesse\/Anwendungen verringern.  
  
 Dieser Fehler kann auch auftreten, wenn Ihre Sicherheitsstufe nicht für das Erstellen von Pipes ausreicht \(siehe [CreatePipe](http://msdn.microsoft.com/library/windows/desktop/aa365152.aspx)\).