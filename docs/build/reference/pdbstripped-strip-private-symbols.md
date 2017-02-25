---
title: "/PDBSTRIPPED (Private Symbole entfernen) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/pdbstripped"
  - "VC.Project.VCLinkerTool.StripPrivateSymbols"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pdb-Dateien, Entfernen von privaten Symbolen"
  - "/PDBSTRIPPED (Linkeroption)"
  - "PDB-Dateien, Entfernen von privaten Symbolen"
  - "PDBSTRIPPED (Linkeroption)"
  - "-PDBSTRIPPED (Linkeroption)"
ms.assetid: 9b9e0070-6a13-4142-8180-19c003fbbd55
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /PDBSTRIPPED (Private Symbole entfernen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/PDBSTRIPPED:pdb_file_name  
```  
  
## Hinweise  
 Hierbei ist:  
  
 *pdb\_file\_name*  
 ein benutzerdefinierter Name für die vom Linker erzeugte und reduzierte Programmdatenbank \(PDB\).  
  
## Hinweise  
 Die Option **\/PDBSTRIPPED** generiert eine zweite Programmdatenbank\-Datei \(PDB\), wenn das Programmabbild mit einer der Compiler\- oder Linkeroptionen erstellt wurde, mit denen eine PDB\-Datei generiert wird \([\/DEBUG](../../build/reference/debug-generate-debug-info.md), [\/Z7](../../build/reference/z7-zi-zi-debug-information-format.md), **\/Zd** oder **\/Zi**\).  Die zweite PDB\-Datei enthält keine Symbole, die nicht an Kunden weitergegeben werden.  Sie enthält lediglich die folgenden Elemente:  
  
-   Symbole vom Typ `Public`  
  
-   Die Liste der Objektdateien und deren jeweiligen Anteil an der ausführbaren Datei  
  
-   Framezeigeroptimierungs\-Debugdatensätze \(FPO\-Datensätze\), die zum Durchsuchen des Stapels verwendet werden  
  
 Die reduzierte PDB enthält folgende Elemente nicht:  
  
-   Typinformationen  
  
-   Zeilennummerinformationen  
  
-   Objektdateibezogene **CodeView**\-Symbole, z. B. für Funktionen, lokale und statische Daten  
  
 Die vollständige PDB\-Datei wird bei Verwendung von **\/PDBSTRIPPED** weiterhin generiert.  
  
 Wenn Sie keine PDB\-Datei erstellen, wird **\/PDBSTRIPPED** ignoriert.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Debuggen**.  
  
4.  Ändern Sie die Eigenschaft **Private Symbole entfernen**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StripPrivateSymbols*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)