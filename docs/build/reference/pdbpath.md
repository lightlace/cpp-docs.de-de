---
title: "/PDBPATH"
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
  - "/pdbpath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pdb-Dateien, Pfad"
  - "/PDBPATH (dumpbin-Option)"
  - "PDB-Dateien, Pfad"
  - "PDBPATH (dumpbin-Option)"
  - "-PDBPATH (dumpbin-Option)"
ms.assetid: ccf67dcd-0b23-4250-ad47-06c48acbe82b
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# /PDBPATH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/PDBPATH[:VERBOSE] filename  
```  
  
## Hinweise  
 Hierbei ist:  
  
 *filename*  
 Der Name der DLL\- oder EXE\-Datei, für die Sie die entsprechende PDB\-Datei suchen möchten.  
  
 VERBOSE \(optional\)  
 Meldet alle Verzeichnisse, in denen versucht wurde, die PDB\-Datei zu finden.  
  
## Hinweise  
 \/PDBPATH durchsucht dieselben Computerpfade, die der Debugger auf der Suche nach einer PDB\-Datei verwendet. Dabei wird gemeldet, ob bzw. welche PDB\-Dateien der in *filename* angegebenen Datei entsprechen.  
  
 Beim Ausführen des Visual Studio\-Debuggers können Probleme auftreten, und zwar aufgrund der Tatsache, dass der Debugger eine PDB\-Datei für eine andere Version einer von Ihnen gedebuggten Datei verwendet.  
  
 \/PDBPATH sucht PDB\-Dateien unter den folgenden Pfaden:  
  
-   Suche an dem Speicherort, an dem sich die ausführbare Datei befindet.  
  
-   Suche an dem Speicherort der PDB, die in die ausführbare Datei geschrieben wurde.  Dieser entspricht in der Regel dem Speicherort, der beim Verknüpfen des Bildes gültig war.  
  
-   Suche entsprechend dem Suchpfad, der in der Visual Studio IDE konfiguriert ist.  
  
-   Suche entsprechend den Pfaden in den Umgebungsvariablen \_NT\_SYMBOL\_PATH und \_NT\_ALT\_SYMBOL\_PATH.  
  
-   Suche im Windows\-Verzeichnis  
  
## Siehe auch  
 [DUMPBIN\-Optionen](../../build/reference/dumpbin-options.md)   
 [\/PDBALTPATH \(Use Alternate PDB Path\)](../../build/reference/pdbaltpath-use-alternate-pdb-path.md)