---
title: "/IDLOUT (Namen der MIDL-Ausgabedateien)"
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
  - "/idlout"
  - "VC.Project.VCLinkerTool.MergedIDLBaseFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".idl-Dateien, Pfad"
  - "/IDLOUT (Linkeroption)"
  - "IDL-Dateien, Pfad"
  - "IDLOUT (Linkeroption)"
  - "-IDLOUT (Linkeroption)"
  - "MIDL"
  - "MIDL, Ausgabedateinamen"
ms.assetid: 10d00a6a-85b4-4de1-8732-e422c6931509
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# /IDLOUT (Namen der MIDL-Ausgabedateien)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/IDLOUT:[path\]filename  
```  
  
## Parameter  
 *path*  
 eine absolute oder relative Pfadangabe.  Die Pfadangabe wirkt sich nur auf den Speicherort von IDL\-Dateien aus; alle anderen Dateien werden im Projektverzeichnis abgelegt.  
  
 *filename*  
 der Name der vom MIDL\-Compiler erstellten IDL\-Datei.  Es wird keine Dateierweiterung angenommen. Wenn Sie eine IDL\-Erweiterung wünschen, müssen Sie *Dateiname*.idl eingeben.  
  
## Hinweise  
 Die \/IDLOUT\-Option gibt den Namen und die Erweiterung der IDL\-Datei an.  
  
 Der MIDL\-Compiler wird beim Verknüpfen von Projekten mit dem [Modul](../../windows/module-cpp.md)attribut durch den Visual C\+\+\-Linker aufgerufen.  
  
 Mit **\/IDLOUT** werden auch die Dateinamen anderer mit dem MIDL\-Compiler verknüpfter Ausgabedateien festgelegt:  
  
-   *Dateiname*.tlb  
  
-   *Dateiname*\_p.c  
  
-   *Dateiname*\_i.c  
  
-   *Dateiname*.h  
  
 *Dateiname* ist der Parameter, den Sie an **\/IDLOUT** übergeben.  Wenn [\/TLBOUT](../../build/reference/tlbout-name-dot-tlb-file.md) angegeben wird, erhält die TLB\-Datei den Namen über **\/TLBOUT***Dateiname*.  
  
 Wenn weder **\/IDLOUT** noch **\/TLBOUT** festgelegt wurde, werden vom Linker die Dateien **vc70.tlb**, **vc70.idl**, **vc70\_p.c**, **vc70\_i.c** und **vc70.h** erstellt.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Eingebettete IDL**.  
  
4.  Ändern Sie die Eigenschaft **Zusammengefügter IDL\-Basisdateiname**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergedIDLBaseFileName*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)   
 [\/IGNOREIDL \(Attribute nicht in MIDL verarbeiten\)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [\/MIDL \(Optionen für MIDL\-Befehlszeile festlegen\)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [Building an Attributed Program](../../windows/building-an-attributed-program.md)