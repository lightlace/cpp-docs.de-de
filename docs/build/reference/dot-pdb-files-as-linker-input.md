---
title: "PDB-Dateien als Eingabe f&#252;r den Linker"
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
  - ".pdb-Dateien, Als Linkereingabe"
  - "PDB-Dateien, Als Linkereingabe"
ms.assetid: c1071478-2369-4b03-9df8-71761cf82f3b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# PDB-Dateien als Eingabe f&#252;r den Linker
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit der Option **\/Zi** kompilierte Objektdateien \(OBJ\-Dateien\) enthalten den Namen einer Programmdatenbank \(PDB\).  Der PDB\-Dateiname des Objekts muss im Linkerprogramm nicht angegeben werden, da **LINK** die PDB\-Datei gegebenenfalls über den eingebetteten Namen findet.  Dies trifft auch auf debugfähige Objekte in einer Bibliothek zu; die PDB einer debugfähigen Bibliothek muss dem Linker zusammen mit der Bibliothek zur Verfügung stehen.  
  
 **LINK** verwendet auch eine PDB, um Debuginformationen für die EXE\- oder DLL\-Datei zu speichern.  Die PDB eines Programms ist gleichermaßen Eingabe\- als auch Ausgabedatei, da **LINK** die PDB aktualisiert, wenn das Programm neu erstellt wird.  
  
## Siehe auch  
 [LINK\-Eingabedateien](../../build/reference/link-input-files.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)