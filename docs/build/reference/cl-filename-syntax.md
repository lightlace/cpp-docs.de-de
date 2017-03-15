---
title: "Syntax f&#252;r Dateinamen bei CL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe-Compiler, filename-Syntax"
  - "Erweiterungen, Angeben für den Compiler"
  - "Dateinamen [C++]"
  - "Dateinamen [C++], CL-Compiler"
  - "Pfade, CL-Compilerdateinamensyntax"
  - "Syntax, Compilerdateiname"
ms.assetid: 3ca72586-75be-4477-b323-a1be232e80d4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Syntax f&#252;r Dateinamen bei CL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CL akzeptiert Dateinamen, die FAT\-, HPFS\- oder NTFS\-Namenskonventionen entsprechen.  Jeder Dateiname kann einen vollständigen oder teilweisen Pfad umfassen.  Ein vollständiger Pfad enthält einen Laufwerksnamen sowie einen oder mehrere Verzeichnisnamen.  CL akzeptiert Dateinamen getrennt durch Backslash \(\\\) oder Schrägstriche \(\/\).  Dateinamen, die Leerzeichen enthalten, müssen in doppelte Anführungszeichen eingeschlossen werden.  Ein partieller Pfad lässt den Servernamen weg, den CL als das aktuelle Laufwerk ansieht.  Wenn Sie einen Pfad angeben, nimmt CL an, dass die Datei im aktuellen Verzeichnis ist.  
  
 Die Dateierweiterung bestimmt, wie Dateien verarbeitet werden.  C\- und C\+\+\-Dateien, die die Erweiterung .c, .cxx oder .cpp haben, werden kompiliert.  Andere Dateien, einschließlich .obj\-Dateien, Bibliotheken \(.lib\) und Moduldefinitionsdateien \(.def\)\-Dateien, werden unverarbeitet an den Linker übergeben.  
  
## Siehe auch  
 [Syntax für die Compilerbefehlszeile](../../build/reference/compiler-command-line-syntax.md)