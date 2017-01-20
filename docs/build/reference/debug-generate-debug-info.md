---
title: "/DEBUG (Debuginfo generieren)"
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
  - "VC.Project.VCLinkerTool.GenerateDebugInformation"
  - "/debug"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pdb-Dateien, Generieren von Debuginformationen"
  - "/DEBUG (Linkeroption)"
  - "DEBUG (Linkeroption)"
  - "-DEBUG (Linkeroption)"
  - "Debuggen [C++], Debuginformationsdateien"
  - "Debuggen [C++], Linkeroption"
  - "Debuginfo generieren (Linkeroption)"
  - "PDB-Dateien"
  - "PDB-Dateien, Generieren von Debuginformationen"
  - "Programmdatenbanken [C++]"
ms.assetid: 1af389ae-3f8b-4d76-a087-1cdf861e9103
caps.latest.revision: 11
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# /DEBUG (Debuginfo generieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DEBUG  
```  
  
## Hinweise  
 Die \/DEBUG\-Option erstellt Debuginformationen für die EXE\-Datei oder DLL.  
  
 Der Linker stellt die Debuginformationen in eine Programmdatenbank \(PDB\).  Die PDB wird während nachfolgender Builds des Programms aktualisiert.  
  
 Die zum Debuggen erstellte EXE\-Datei oder DLL enthält den Namen und den Pfad der entsprechenden PDB.  Der Debugger liest den eingeschlossenen Namen und verwendet die PDB, wenn Sie das Programm debuggen.  Der Linker verwendet den Basisnamen des Programms und die Erweiterung **.pdb**, um die Programmdatenbank zu benennen, und schließt den Pfad ein, in dem sie erstellt wurde.  Sie können diese Standardeinstellung überschreiben, indem Sie die Option [\/PDB](../../build/reference/pdb-use-program-database.md) setzen und einen anderen Dateinamen festlegen.  
  
 Die Option [Nur Zeilennummern](../../build/reference/z7-zi-zi-debug-information-format.md) \(**\/Zd**\) oder die Option [C7\-Kompatibel](../../build/reference/z7-zi-zi-debug-information-format.md) \(**\/Z7**\) des Compilers weist den Compiler an, die Debuginformationen in den OBJ\-Dateien zu belassen.  Sie können die Debuginformationen für die OBJ\-Datei auch mithilfe der Compileroption [Programmdatenbank](../../build/reference/z7-zi-zi-debug-information-format.md) \(**\/Zi**\) in einer PDB\-Datei speichern.  Der Linker sucht nach der PDB\-Datei des Objekts zunächst im absoluten Pfad, der in der OBJ\-Datei enthalten ist, und dann in dem Verzeichnis, das die OBJ\-Datei enthält.  Sie können dem Linker den Dateinamen oder Speicherort einer PDB\-Datei nicht direkt übergeben.  
  
 Beim Festlegen von **\/DEBUG** wird [\/INCREMENTAL](../../build/reference/incremental-link-incrementally.md) impliziert.  
  
 \/DEBUG ändert die Standards für die [\/OPT](../../build/reference/opt-optimizations.md)\-Option von REF in NOREF und von ICF in NOICF. \(Sie müssen also explizit \/OPT:REF bzw. \/OPT:ICF angeben.\)  
  
 Weitere Informationen zu PDB\- und DBG\-Dateien finden Sie im Knowledge Base\-Artikel Q121366, "INFO: PDB and DBG Files – What They Are and How They Work" \(nur auf Englisch verfügbar\).  Knowledge Base\-Artikel finden Sie in der MSDN Library oder an [http:\/\/support.microsoft.com](http://support.microsoft.com/) suchen.  
  
 Es ist nicht möglich, ein EXE\-Datei oder eine DLL\-Datei mit Debuginformationen zu erstellen.  Debuginformationen werden immer in eine PDB\-Datei geschrieben.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Debugging** .  
  
4.  Ändern Sie die Eigenschaft **Debuginfo generieren**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateDebugInformation*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)