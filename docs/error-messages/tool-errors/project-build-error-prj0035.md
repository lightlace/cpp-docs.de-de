---
title: "Projektbuildfehler PRJ0035"
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
  - "PRJ0035"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0035"
ms.assetid: 0667116d-338c-40a4-972c-da875f778cb5
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Projektbuildfehler PRJ0035
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die XML\-Datei "Datei" enthält Unicodeinhalt, der nicht in die ANSI\-Codepage des Benutzers übersetzt werden konnte.  
  
 ***UNICODE\-Inhalt der Datei***  
  
 ***file***  entspricht der XML\-Datei, die als Befehlszeile für das Web Deployment Tool erstellt wurde.  
  
 Das Projektsystem hat Unicode\-Zeichen in einer Eigenschaft auf der Eigenschaftenseite **Webbereitstellung** gefunden, die wahrscheinlich nicht in ANSI übersetzt werden können.  
  
 Die Lösung dieses Problems besteht darin, dass Sie den Inhalt der Eigenschaft für die Verwendung von ANSI aktualisieren oder die Codepage auf dem Computer installieren und als Systemstandard festlegen.