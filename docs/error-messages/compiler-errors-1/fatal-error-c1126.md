---
title: "Schwerwiegender Fehler C1126 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1126"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1126"
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Schwerwiegender Fehler C1126
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Automatische Reservierung überschreitet Größe  
  
 Der für lokale Variablen einer Funktion reservierte Speicherplatz \(sowie eine begrenzte, vom Compiler verwendete Speicherkapazität, z. B. 20 Bytes zusätzlich für austauschbare Funktionen\) überschreitet die maximale Größe.  
  
 Um diesen Fehler zu beheben, verwenden Sie zum Reservieren großer Datenmengen `malloc` oder `new`.