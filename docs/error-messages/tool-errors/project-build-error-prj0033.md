---
title: "Projektbuildfehler PRJ0033 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0033"
ms.assetid: 84d4a052-0586-4b78-9315-81c1e8386c1e
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Projektbuildfehler PRJ0033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die 'Additional Dependencies'\-Eigenschaft für den benutzerdefinierten Buildschritt für die Datei 'Datei' enthält 'Makro', das als 'Makroerweiterung' ausgewertet wird.  
  
 Ein benutzerdefinierter Buildschritt für eine Datei weist einen Fehler in seiner zusätzlichen Abhängigkeit auf. Dies liegt möglicherweise an einem Problem mit der Makroauswertung.  Dieser Fehler kann außerdem darauf hinweisen, dass die Pfadangaben fehlerhaft sind; sie enthalten möglicherweise Zeichen oder Zeichenkombinationen, die in einem Dateipfad nicht zulässig sind.  
  
 Um diesen Fehler zu beheben, korrigieren Sie das Makro oder die Pfadangabe.  Der ausgewertete Pfad ist ein absoluter Pfad aus dem Projektverzeichnis.