---
title: "Projektbuildfehler PRJ0036 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0036"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0036"
ms.assetid: ee215cd1-2d66-474d-9a63-b9096f1c4923
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Projektbuildfehler PRJ0036
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Eigenschaft 'Additional Files' für das Webbereitstellungstool enthält einen ungültigen Eintrag.  
  
 Die Eigenschaft **Additional Files** auf der Eigenschaftenseite **Webbereitstellung** enthielt einen Fehler, der möglicherweise auf ein Problem mit der Makroauswertung zurückzuführen ist.  Dieser Fehler kann außerdem darauf hinweisen, dass die Pfadangaben fehlerhaft sind; sie enthalten möglicherweise Zeichen oder Zeichenkombinationen, die in einem Dateipfad nicht zulässig sind.  
  
 Um diesen Fehler zu beheben, korrigieren Sie das Makro oder die Pfadangabe.  Der ausgewertete Pfad ist ein absoluter Pfad aus dem Projektverzeichnis.  
  
 Dieser Fehler könnte auch darauf hinweisen, dass eine der Dateien, auf die verwiesen wird, nicht existiert.