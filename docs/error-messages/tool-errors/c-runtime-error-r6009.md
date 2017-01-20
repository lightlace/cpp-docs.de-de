---
title: "C-Laufzeitfehler R6009"
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
  - "R6009"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6009"
ms.assetid: edfb1f8b-3807-48f4-a994-318923b747ae
caps.latest.revision: 7
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# C-Laufzeitfehler R6009
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht genügend Speicher für Umgebung  
  
 Es war zwar noch genügend Arbeitsspeicher zum Laden des Programms vorhanden, für die Erstellung des envp\-Arrays stand jedoch nicht mehr genügend Speicher zur Verfügung.  
  
### Beachten Sie die folgenden Vorschläge zur Problembehebung:  
  
1.  Stellen Sie dem Programm mehr Speicher zur Verfügung.  
  
2.  Reduzieren Sie die Anzahl und die Größe der Befehlszeilenargumente.  
  
3.  Reduzieren Sie die Umgebungsgröße durch das Entfernen unnötiger lokaler Variablen.