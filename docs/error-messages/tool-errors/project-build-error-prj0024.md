---
title: "Projektbuildfehler PRJ0024"
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
  - "PRJ0024"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0024"
ms.assetid: 8bde6368-6c1b-4e04-bc5e-3c6d0b8fa1d7
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Projektbuildfehler PRJ0024
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unicodepfad 'Pfad' konnte nicht in die ANSI\-Codepage des Benutzers übersetzt werden.  
  
 ***path***  entspricht der ursprünglichen Unicodeversion der Pfadzeichenfolge.  Dieser Fehler kann bei einem Unicodepfad auftreten, der für die aktuelle Systemcodepage nicht direkt in ANSI übersetzt werden kann.  
  
 Eine weitere Fehlerursache kann sein, dass Sie mit einem Projekt arbeiten, das mithilfe einer Codepage entwickelt wurde, die auf Ihrem Computer nicht verfügbar ist.  
  
 Die Lösung besteht darin, dass Sie den Pfad unter Verwendung von ANSI\-Text aktualisieren oder die Codepage auf dem Computer installieren und als Systemstandard festlegen.