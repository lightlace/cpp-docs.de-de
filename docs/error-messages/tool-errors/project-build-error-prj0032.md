---
title: "Projektbuildfehler PRJ0032 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0032"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0032"
ms.assetid: bc6acbea-4041-4237-8b5a-f0434705d89f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Projektbuildfehler PRJ0032
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die 'Outputs'\-Eigenschaft für den benutzerdefinierten Buildschritt auf Projektebene enthält 'Makro', das als 'Makroerweiterung' ausgewertet wird.  
  
 In einem benutzerdefinierten Buildschritt für ein Projekt wurden fehlerhaften Daten ausgegeben. Dies liegt möglicherweise an einem Problem mit der Makroauswertung.  Dieser Fehler kann außerdem darauf hinweisen, dass die Pfadangaben fehlerhaft sind; sie enthalten möglicherweise Zeichen oder Zeichenkombinationen, die in einem Dateipfad nicht zulässig sind.  
  
 Um diesen Fehler zu beheben, korrigieren Sie das Makro oder die Pfadangabe.  Der ausgewertete Pfad ist ein absoluter Pfad aus dem Projektverzeichnis.