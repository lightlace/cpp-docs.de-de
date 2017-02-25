---
title: "/PDB (Programmdatenbank verwenden) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/pdb"
  - "VC.Project.VCLinkerTool.ProgramDatabaseFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pdb-Dateien, Erstellen"
  - "/PDB (Linkeroption)"
  - "PDB-Dateien, Erstellen"
  - "PDB (Linkeroption)"
  - "-PDB (Linkeroption)"
ms.assetid: d23db0ce-10cb-427a-bc60-d6b2a852723d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /PDB (Programmdatenbank verwenden)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/PDB:filename  
```  
  
## Hinweise  
 Hierbei ist:  
  
 *filename*  
 ein benutzerdefinierter Name für die vom Linker erzeugte Programmdatenbank \(PDB\).  Er wird anstelle des Standardnamens verwendet.  
  
## Hinweise  
 Wenn die Option [\/DEBUG](../../build/reference/debug-generate-debug-info.md) angegeben wird, erstellt der Linker standardmäßig eine Programmdatenbank \(PDB\), in der Debuginformationen enthalten sind.  Der Standarddateiname für die PDB enthält den Basisnamen des Programms und hat die Erweiterung ".pdb".  
  
 Geben Sie den Namen der PDB\-Datei mithilfe von **\/PDB**:*filename* an.  Wenn **\/DEBUG** nicht angegeben wurde, wird die Option **\/PDB** ignoriert.  
  
 Die Größe einer PDB\-Datei kann bis zu 2 GB betragen.  
  
 Weitere Informationen finden Sie unter [PDB\-Dateien als Eingabe für den Linker](../../build/reference/dot-pdb-files-as-linker-input.md).  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Debuggen**.  
  
4.  Ändern Sie die Eigenschaft **Programmdatenbank\-Datei erstellen**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProgramDatabaseFile*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)