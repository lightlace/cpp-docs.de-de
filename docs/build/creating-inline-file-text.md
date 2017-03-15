---
title: "Erstellen von Text f&#252;r die Inlinedatei | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Inlinedateien, Erstellen von Text"
  - "NMAKE (Programm), Inlinedateien"
  - "Text, Inlinedatei"
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erstellen von Text f&#252;r die Inlinedatei
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Inlinedateien sind temporär oder permanent.  
  
## Syntax  
  
```  
  
      inlinetext  
.  
.  
.  
<<[KEEP | NOKEEP]  
```  
  
## Hinweise  
 *inlinetext* wird in der ersten Zeile nach dem Befehl eingegeben.  Markieren Sie das Ende mit doppelten spitzen Klammern \(\<\<\) am Anfang eine eigene Zeile.  Die Datei enthält den gesamten *inlinetext* vor den begrenzenden Klammern.  *inlinetext* kann Makroerweiterungen und Makroersetzungen enthalten, jedoch keine Direktiven oder Makefilekommentare.  Leerzeichen, Tabstopps und Zeilenendemarken werden als Literalzeichen behandelt.  
  
 Eine temporäre Datei ist für die Dauer der Sitzung vorhanden und kann von anderen Befehlen wieder verwendet werden.  **KEEP** wird nach den abschließenden Winkelklammern eingegeben, damit die Datei nach der NMAKE\-Sitzung beibehalten wird. Eine unbenannte Datei bleibt auf dem Datenträger mit dem generierten Dateinamen erhalten.  Geben Sie **NOKEEP** oder nichts für eine temporäre Datei ein.  Bei **KEEP** und **NOKEEP** wird die Groß‑\/Kleinschreibung nicht beachtet.  
  
## Siehe auch  
 [Inlinedateien in einem Makefile](../build/inline-files-in-a-makefile.md)