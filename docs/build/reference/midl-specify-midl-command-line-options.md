---
title: "/MIDL (Optionen f&#252;r MIDL-Befehlszeile festlegen) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/midl"
  - "VC.Project.VCLinkerTool.MidlCommandFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MIDL (Linkeroption)"
  - "MIDL"
  - "MIDL (Linkeroption)"
  - "-MIDL (Linkeroption)"
  - "MIDL, Befehlszeilenoptionen"
ms.assetid: 22dc259e-b34c-4ed3-a380-4beb734482c1
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /MIDL (Optionen f&#252;r MIDL-Befehlszeile festlegen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MIDL:@file  
```  
  
## Hinweise  
 Hierbei ist:  
  
 `file`  
 der Name der Datei, die die [MIDL\-Befehlszeilenoptionen](http://msdn.microsoft.com/library/windows/desktop/aa366839) enthält.  
  
## Hinweise  
 Alle für die Konvertierung einer IDL\-Datei in eine TLB\-Datei notwendigen Optionen müssen in `file` angegeben sein; MIDL\-Befehlszeilenoptionen können in der Befehlszeile des Linkers nicht angegeben werden.  Falls **\/MIDL** nicht angegeben wurde, wird der MIDL\-Compiler mit nur einem IDL\-Dateinamen ohne weitere Optionen aufgerufen.  
  
 Die Datei sollte pro Zeile eine MIDL\-Befehlszeilenoption enthalten.  
  
### So legen Sie diese Linkeroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Festlegen von Visual C\+\+\-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **Linker**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Eingebettete IDL**.  
  
4.  Ändern Sie die Eigenschaft **MIDL\-Befehle**.  
  
### So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile*>.  
  
## Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)   
 [\/IDLOUT \(Namen der MIDL\-Ausgabedateien\)](../../build/reference/idlout-name-midl-output-files.md)   
 [\/IGNOREIDL \(Attribute nicht in MIDL verarbeiten\)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [\/TLBOUT \(TLB\-Datei benennen\)](../../build/reference/tlbout-name-dot-tlb-file.md)   
 [Building an Attributed Program](../../windows/building-an-attributed-program.md)