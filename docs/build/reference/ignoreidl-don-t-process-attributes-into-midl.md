---
title: "/IGNOREIDL (Attribute nicht in MIDL verarbeiten) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.IgnoreEmbeddedIDL"
  - "/ignoreidl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/IGNOREIDL (Linkeroption)"
  - "IGNOREIDL (Linkeroption)"
  - "-IGNOREIDL (Linkeroption)"
ms.assetid: 29514098-6a1c-4317-af2f-1dc268972780
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /IGNOREIDL (Attribute nicht in MIDL verarbeiten)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/IGNOREIDL  
```  
  
## Hinweise  
 Die Option **\/IGNOREIDL** bestimmt, dass [IDL\-Attribute](../../windows/idl-attributes.md) im Quellcode nicht in eine IDL\-Datei verarbeitet werden sollen.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Eingebettete IDL**.  
  
4.  Ändern Sie die Eigenschaft **Eingebettetes IDL ignorieren**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreEmbeddedIDL*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)   
 [\/IDLOUT \(Namen der MIDL\-Ausgabedateien\)](../../build/reference/idlout-name-midl-output-files.md)   
 [\/TLBOUT \(TLB\-Datei benennen\)](../../build/reference/tlbout-name-dot-tlb-file.md)   
 [\/MIDL \(Optionen für MIDL\-Befehlszeile festlegen\)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [Building an Attributed Program](../../windows/building-an-attributed-program.md)