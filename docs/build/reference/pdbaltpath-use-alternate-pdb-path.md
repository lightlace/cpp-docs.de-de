---
title: "/PDBALTPATH (Use Alternate PDB Path) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/pdbaltpath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pdb-Dateien, Pfad"
  - "/PDBALTPATH (dumpbin-Option)"
  - "PDB-Dateien, Pfad"
  - "PDBALTPATH (dumpbin-Option)"
  - "-PDBALTPATH (dumpbin-Option)"
ms.assetid: 72e200aa-e2c3-4ad8-b687-25528da1aaaf
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /PDBALTPATH (Use Alternate PDB Path)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/PDBALTPATH:pdb_file_name  
```  
  
## Hinweise  
 Dabei gilt:  
  
 *pdb\_file\_name*  
 Der Pfad und der Dateiname für die .pdb\-Datei.  
  
## Hinweise  
 Verwenden Sie diese Option, um einen alternativen Speicherort für die Programmdatenbankdatei \(.pdb\) in einer kompilierten Binärdatei bereitzustellen.  Normalerweise zeichnet der Linker den Speicherort der .pdb\-Dateien in den Binärdateien auf, die er produziert.  Sie können diese Option verwenden, um einen anderen Pfad und Dateinamen für die .pdb\-Datei bereitzustellen.  Die mit \/PDBALTPATH bereitgestellten Informationen ändern weder den Standort noch den Namen der tatsächlichen .pdb\-Datei, sondern sie ändern die Informationen, die der Linker in die Binärdatei schreibt.  Damit können Sie einen Pfad bereitstellen, der unabhängig von der Dateistruktur des Buildcomputers ist.  Zwei typische Verwendungszwecke für die Option ist die Bereitstellung eines Netzwerkpfads oder einer Datei, die keine Pfadinformationen hat.  
  
 Der Wert von *pdb\_file\_name* kann eine beliebige Zeichenfolge, eine Umgebungsvariable oder **%\_PDB%** sein.  Der Linker erweitert eine Umgebungsvariable wie **%SystemRoot%** auf ihren Wert.  Der Linker definiert die Umgebungsvariablen **%\_PDB%** and **%\_EXT%**.  **%\_PDB%** wird auf den Dateinamen der tatsächlichen .pdb\-Datei ohne Pfadinformationen erweitert, und **%\_EXT%** ist die Erweiterung der generierten ausführbaren Datei.  
  
## Siehe auch  
 [DUMPBIN\-Optionen](../../build/reference/dumpbin-options.md)   
 [\/PDBPATH](../../build/reference/pdbpath.md)