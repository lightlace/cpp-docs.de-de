---
title: "Wiederverwenden von Inlinedateien"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Inlinedateien, Wiederverwenden von NMAKE"
  - "NMAKE (Programm), Inlinedateien"
  - "Überarbeiten von Inlinedateien"
ms.assetid: d42dbffb-2cef-4ccb-9a1f-20b8ef81481c
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Wiederverwenden von Inlinedateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um eine Inlinedatei wiederzuverwenden, geben Sie *Dateinamen \<\<* in dem die Datei zunächst definiert und verwendet wird, dann Wiederverwendungsdateinamen außen \<\< später im gleichen oder anderen Befehl.  Der Befehl für das Erstellen der Inlinedatei muss vor allen anderen Befehlen ausgeführt werden, die diese Datei einsetzen.  
  
## Siehe auch  
 [Inlinedateien in einem Makefile](../build/inline-files-in-a-makefile.md)