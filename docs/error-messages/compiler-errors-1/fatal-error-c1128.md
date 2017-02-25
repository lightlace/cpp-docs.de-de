---
title: "Schwerwiegender Fehler C1128 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1128"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1128"
ms.assetid: 6f9580fd-ecef-48be-9780-dcf666704279
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Schwerwiegender Fehler C1128
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Anzahl der Abschnitte überschreitet Objektdateiformatgrenze: Kompilieren mit \/bigobj  
  
 Eine OBJ\-Datei hat die Anzahl der zulässigen Abschnitte überschritten. Hierbei handelt es sich um eine Formatbeschränkung für COFF\-Objektdateien.  
  
 Das Erreichen dieser Abschnittsbeschränkung kann aus der Verwendung von [\/Gy](../../build/reference/gy-enable-function-level-linking.md) für ein Debugbuild resultieren. Durch **\/Gy** werden Funktionen ihren eigenen COMDAT\-Abschnitten zugeordnet.  Ein Debugbuild enthält für jede COMDAT\-Funktion einen Abschnitt mit Debuginformationen.  
  
 C1128 kann auch durch die Verwendung zu vieler Inlinefunktionen verursacht werden.  
  
 Um diesen Fehler zu beheben, teilen Sie die Quelldatei in mehrere Quellcodedateien auf und kompilieren ohne **\/Gy**, oder Sie kompilieren mit [\/bigobj \(Erhöhen der Anzahl von Abschnitten in der OBJ\-Datei\)](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md).  Wenn Sie nicht mit **\/Gy** kompilieren, müssen Sie die Optimierungen einzeln angeben, da sowohl **\/O2** als auch **\/O1 \/Gy** implizieren.  
  
 Kompilieren Sie nach Möglichkeit ohne Debuginformationen.  
  
 Möglicherweise benötigen Sie außerdem spezifische Vorlageninstanziierungen in separaten Quellcodedateien, anstatt sie vom Compiler ausgeben zu lassen.  
  
 Beim Portieren von Code wird C1128 wahrscheinlich erst bei Benutzung des x64\-Compilers auftreten, und viel später bei einem x86\-Compiler. Bei x64 sind mindestens 4 Bereiche jeder kompilierten Funktion \(**\/Gy**\) oder Inlinefunktion \(Vorlagen oder Klassen\) zugeordnet: Code, pdata, Debuginformationen sowie möglicherweise xdata.  Bei X86 ist der pdata\-Abschnitt nicht vorhanden.