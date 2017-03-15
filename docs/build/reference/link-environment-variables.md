---
title: "LINK-Umgebungsvariablen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "link"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Umgebungsvariablen [C++], LINK"
  - "LIB-Umgebungsvariable"
  - "LINK-Tool [C++], Umgebungsvariablen"
  - "Variablen, Umgebung"
ms.assetid: 9a3d3291-0cc4-4a7d-9d50-80e351b90708
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# LINK-Umgebungsvariablen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das LINK\-Tool verwendet die folgenden Umgebungsvariablen:  
  
-   LINK und \_LINK\_, falls definiert.  Vor der Verarbeitung stellt das LINK\-Tool die Optionen und Argumente, die in der Umgebungsvariablen LINK definiert sind, vor die Befehlszeilenargumente und fügt die Optionen und Argumente, die in der Umgebungsvariablen \_LINK\_ definiert sind, hinter den Befehlszeilenargumenten an.  
  
-   LIB, falls definiert.  Die LINK\-Tools verwenden den LIB\-Pfad bei der Suche nach einem Objekt, einer Bibliothek oder anderen Datei, die in der Befehlszeile oder durch die [\/BASE](../../build/reference/base-base-address.md)\-Option angegeben wurde.  Der LIB\-Pfad wird auch verwendet, um nach einer in einem Objekt genannten PDB\-Datei zu suchen.  Die LIB\-Variable kann mehrere durch Semikolons getrennte Pfadangaben enthalten.  Ein Pfad muss auf das Unterverzeichnis \\lib der Visual C\+\+\-Installation zeigen.  
  
-   PATH, wenn das Tool CVTRES ausführen muss und die Datei nicht im selben Verzeichnis wie LINK findet.  \(LINK benötigt CVTRES, um eine RES\-Datei zu verknüpfen.\) PATH muss auf das Unterverzeichnis \\bin der Visual C\+\+\-Installation zeigen.  
  
-   TMP zum Angeben eines Verzeichnisses beim Verknüpfen von OMF oder RES\-Dateien  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)   
 [Festlegen der Pfad\- und Umgebungsvariablen für Befehlszeilenbuilds](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)