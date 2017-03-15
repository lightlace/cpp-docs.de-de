---
title: "/TLBOUT (TLB-Datei benennen)"
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
  - "VC.Project.VCLinkerTool.TypeLibraryFile"
  - "/tlbout"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".tlb-Dateien, Umbenennen"
  - "/TLBOUT (Linkeroption)"
  - "TLB-Dateien, Umbenennen"
  - "TLBOUT (Linkeroption)"
  - "-TLBOUT (Linkeroption)"
ms.assetid: 0df6d078-2e48-46c9-a1a5-02674d85dce8
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# /TLBOUT (TLB-Datei benennen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/TLBOUT:[path\]filename  
```  
  
## Hinweise  
 Hierbei ist:  
  
 *path*  
 eine absolute oder relative Angabe des Pfads, in dem die TLB\-Datei erstellt werden soll, und  
  
 *filename*  
 der Name der vom MIDL\-Compiler erstellten TLB\-Datei.  Es wird keine Dateierweiterung angenommen. Wenn Sie eine TLB\-Erweiterung wünschen, müssen Sie *Dateiname*.tlb eingeben.  
  
## Hinweise  
 Die \/TLBOUT\-Option gibt den Namen und die Erweiterung der TLB\-Datei an.  
  
 Der MIDL\-Compiler wird beim Verknüpfen von Projekten mit dem [Modul](../../windows/module-cpp.md)attribut durch den Visual C\+\+\-Linker aufgerufen.  
  
 Wenn **\/TLBOUT** nicht angegeben wird, erhält die TLB\-Datei den Namen über [\/IDLOUT](../../build/reference/idlout-name-midl-output-files.md)*Dateiname*.  Wird auch **\/IDLOUT** nicht angegeben, erhält die TLB\-Datei den Namen **vc70.tlb**.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Eingebettete IDL**.  
  
4.  Ändern Sie die Eigenschaft **Typbibliothek**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryFile*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)   
 [\/IGNOREIDL \(Attribute nicht in MIDL verarbeiten\)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [\/MIDL \(Optionen für MIDL\-Befehlszeile festlegen\)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [Building an Attributed Program](../../windows/building-an-attributed-program.md)