---
title: "/Fd (Programmdatenbank-Dateiname)"
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
  - "/FD"
  - "VC.Project.VCCLWCECompilerTool.ProgramDataBaseFileName"
  - "VC.Project.VCCLCompilerTool.ProgramDataBaseFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pdb-Dateien, Erstellen"
  - "/FD (Compileroption) [C++]"
  - "FD (Compileroption) [C++]"
  - "-FD (Compileroption) [C++]"
  - "PDB-Dateien, Erstellen"
  - "Programmdatenbank (Compileroption) [C++]"
  - "Programmdatenbank-Dateiname [C++]"
ms.assetid: 3977a9ed-f0ac-45df-bf06-01cedd2ba85a
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# /Fd (Programmdatenbank-Dateiname)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt einen Dateinamen für die von [\/Z7, \/Zi, \/ZI \(Debuginformationsformat\)](../../build/reference/z7-zi-zi-debug-information-format.md) erstellte Programmdatenbankdatei \(PDB\) an.  
  
## Syntax  
  
```  
/Fdpathname  
```  
  
## Hinweise  
 Ohne **\/Fd** lautet der Name der PDB\-Datei standardmäßig VC`x`0.pdb., wobei `x` die Hauptversion des verwendeten Visual C\+\+ angibt.  
  
 Wenn Sie einen Pfadnamen angeben, der keinen Dateinamen enthält \(Pfad beenden im umgekehrten Schrägstrich\), erstellt der Compiler eine PDB\-Datei, die `x`0.pdb VC im angegebenen Verzeichnis.  
  
 Wenn Sie einen Dateinamen angeben, der keine Erweiterung enthält, fügt der Compiler die Erweiterung **.pdb** an.  
  
 Diese Option legt auch den Namen der Zustandsdatei \(IDB\-Datei\) des Compilers für die minimale Neuerstellung und inkrementelle Kompilierung fest.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Ausgabedateien**.  
  
4.  Ändern Sie die Eigenschaft **Programmdatenbank\-Dateiname**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ProgramDataBaseFileName*>.  
  
## Beispiel  
 Mit dieser Befehlszeile wird eine PDF\-Datei mit dem Namen **PROG.pdb** und eine IDB\-Datei mit dem Namen **PROG.idb** erstellt:  
  
```  
CL /DDEBUG /Zi /FdPROG.PDB PROG.CPP  
```  
  
## Siehe auch  
 [\/F\-Optionen \(Ausgabedateioptionen\)](../../build/reference/output-file-f-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)