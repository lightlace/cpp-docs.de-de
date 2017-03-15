---
title: "Projektbuildfehler PRJ0035 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0035"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0035"
ms.assetid: 0667116d-338c-40a4-972c-da875f778cb5
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Projektbuildfehler PRJ0035
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die XML\-Datei "Datei" enthält Unicodeinhalt, der nicht in die ANSI\-Codepage des Benutzers übersetzt werden konnte.  
  
 ***UNICODE\-Inhalt der Datei***  
  
 ***file***  entspricht der XML\-Datei, die als Befehlszeile für das Web Deployment Tool erstellt wurde.  
  
 Das Projektsystem hat Unicode\-Zeichen in einer Eigenschaft auf der Eigenschaftenseite **Webbereitstellung** gefunden, die wahrscheinlich nicht in ANSI übersetzt werden können.  
  
 Die Lösung dieses Problems besteht darin, dass Sie den Inhalt der Eigenschaft für die Verwendung von ANSI aktualisieren oder die Codepage auf dem Computer installieren und als Systemstandard festlegen.