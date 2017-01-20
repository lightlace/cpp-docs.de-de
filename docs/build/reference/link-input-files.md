---
title: "LINK-Eingabedateien"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "link"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Befehlseingabe für Linkerdateien [C++]"
  - "Dateien [C++], LINK"
  - "Importbibliotheken [C++], Linkerdateien"
  - "Eingabedateien [C++], LINK"
  - "LINK-Tool [C++], Eingabedateien"
  - "Linker [C++], Eingabedateien"
  - "Moduldefinitionsdateien"
  - "Moduldefinitionsdateien, Linkerdateien"
  - "Ressourcen [C++], Linkerdateien"
ms.assetid: bb26fcc5-509a-4620-bc3e-b6c6e603a412
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# LINK-Eingabedateien
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sie stellen dem Linker Dateien zur Verfügung, die Objekte, Import\- und Standardbibliotheken, Ressourcen, Moduldefinitionen und Befehlseingaben enthalten.  **LINK** nimmt keine Annahmen über den Inhalt einer Datei aufgrund ihrer Dateierweiterung vor.  Stattdessen untersucht **LINK** jede Eingabedatei, um festzustellen, welcher Dateityp vorliegt.  
  
 Objektdateien in der Befehlszeile werden in der Reihenfolge verarbeitet, in der sie in der Befehlszeile angezeigt werden.  Bibliotheken werden ebenfalls in der Reihenfolge durchsucht, in der sie in der Befehlszeile angezeigt werden, jedoch mit der folgenden Einschränkung: Nach Symbolen, die beim Importieren einer Objektdatei aus einer Bibliothek nicht aufgelöst sind, wird zuerst in dieser Bibliothek gesucht. Dann werden die in der Befehlszeile folgenden Bibliotheken und [\/DEFAULTLIB \(Standardbibliothek festlegen\)](../../build/reference/defaultlib-specify-default-library.md)\-Direktiven durchsucht, und schließlich die Bibliotheken am Anfang der Befehlszeile.  
  
> [!NOTE]
>  Ein Semikolon \(oder jedes andere Zeichen\) wird von LINK in Antwort\- und Anordnungsdateien nicht mehr als Anfang eines Kommentars interpretiert.  Das Semikolon wird nur noch in Moduldefinitionsdateien \(DEF\-Dateien\) als Anfang eines Kommentars interpretiert.  
  
 **LINK** verwendet für die Eingabe folgende Dateitypen:  
  
-   [OBJ\-Dateien](../../build/reference/dot-obj-files-as-linker-input.md)  
  
-   [.netmodule\-Dateien](../../build/reference/netmodule-files-as-linker-input.md)  
  
-   [LIB\-Dateien](../../build/reference/dot-lib-files-as-linker-input.md)  
  
-   [EXP\-Dateien](../../build/reference/dot-exp-files-as-linker-input.md)  
  
-   [DEF\-Dateien](../../build/reference/dot-def-files-as-linker-input.md)  
  
-   [PDB\-Dateien](../../build/reference/dot-pdb-files-as-linker-input.md)  
  
-   [RES\-Dateien](../../build/reference/dot-res-files-as-linker-input.md)  
  
-   [EXE\-Dateien](../../build/reference/dot-exe-files-as-linker-input.md)  
  
-   [TXT\-Dateien](../../build/reference/dot-txt-files-as-linker-input.md)  
  
-   [ILK\-Dateien](../../build/reference/dot-ilk-files-as-linker-input.md)  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)