---
title: ".EXP-Dateien als Eingabe f&#252;r den Linker"
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
  - ".exp-Dateien [C++]"
  - "EXP-Dateien"
  - "Exportieren von Daten, Exportdateien (.exp)"
  - "Exportieren von Funktionen"
  - "Exportieren von Funktionen, Informationen über exportierte Funktionen"
  - "Funktionen [C++], Exportieren"
  - "Importbibliotheken, Linkerdateien"
  - "Verknüpfen [C++], Exporte"
ms.assetid: 399f5636-0a4d-462e-b500-5f5b9ae5ad22
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# .EXP-Dateien als Eingabe f&#252;r den Linker
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Exportdateien \(EXP\-Dateien\) enthalten Informationen über exportierte Funktionen und Datenelemente.  Beim Erstellen einer Importbibliothek erstellt **LIB** auch eine Exportdatei.  Sie verwenden diesen Dateityp, wenn Sie ein Programm verknüpfen, das in ein anderes Programm entweder direkt oder indirekt in ein anderes Programm exportiert sowie aus einem solchen importiert.  Wenn Sie mit einer EXP\-Datei verknüpfen, erstellt **LINK** keine Importbibliothek, da angenommen wird, dass **LIB** bereits eine erstellt hat.  Weitere Informationen über EXP\-Dateien und Importbibliotheken finden Sie unter [Arbeiten mit Importbibliotheken und Exportdateien](../../build/reference/working-with-import-libraries-and-export-files.md).  
  
## Siehe auch  
 [LINK\-Eingabedateien](../../build/reference/link-input-files.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)