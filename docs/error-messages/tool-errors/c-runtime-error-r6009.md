---
title: "C-Laufzeitfehler R6009 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6009"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6009"
ms.assetid: edfb1f8b-3807-48f4-a994-318923b747ae
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# C-Laufzeitfehler R6009
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht genügend Speicher für Umgebung  
  
 Es war zwar noch genügend Arbeitsspeicher zum Laden des Programms vorhanden, für die Erstellung des envp\-Arrays stand jedoch nicht mehr genügend Speicher zur Verfügung.  
  
### Beachten Sie die folgenden Vorschläge zur Problembehebung:  
  
1.  Stellen Sie dem Programm mehr Speicher zur Verfügung.  
  
2.  Reduzieren Sie die Anzahl und die Größe der Befehlszeilenargumente.  
  
3.  Reduzieren Sie die Umgebungsgröße durch das Entfernen unnötiger lokaler Variablen.