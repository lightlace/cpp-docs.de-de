---
title: -MIDL (Optionen für MIDL-Befehlszeile festlegen) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /midl
- VC.Project.VCLinkerTool.MidlCommandFile
dev_langs:
- C++
helpviewer_keywords:
- -MIDL linker option
- MIDL
- /MIDL linker option
- MIDL linker option
- MIDL, command line options
ms.assetid: 22dc259e-b34c-4ed3-a380-4beb734482c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d125042041af1e20b6dfc4a02197c2124adbeb9a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="midl-specify-midl-command-line-options"></a>/MIDL (Optionen für MIDL-Befehlszeile festlegen)
```  
/MIDL:@file  
```  
  
## <a name="remarks"></a>Hinweise  
 Dabei gilt:  
  
 `file`  
 Der Name der Datei, die mit [MIDL-Befehlszeilenoptionen](http://msdn.microsoft.com/library/windows/desktop/aa366839).  
  
## <a name="remarks"></a>Hinweise  
 Bei allen Optionen für die Konvertierung einer IDL-Datei in eine TLB-Datei müssen im erhalten `file`; MIDL-Befehlszeilenoptionen können nicht in der Linker-Befehlszeile angegeben werden. / MIDL nicht angegeben ist, wird die MIDL-Compiler mit nur die Namen der IDL-Datei und keine anderen Optionen aufgerufen werden.  
  
 Die Datei muss es sich um eine MIDL-Befehlszeilenoption pro Zeile enthalten.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die **eingebettete IDL** Eigenschaftenseite.  
  
4.  Ändern der **MIDL-Befehle** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Optionen des Linkers](../../build/reference/linker-options.md)   
 [/ IDLOUT (Namen der MIDL-Ausgabedateien)](../../build/reference/idlout-name-midl-output-files.md)   
 [/ IGNOREIDL (Attribute nicht in verarbeiten "MIDL")](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [/ TLBOUT (Name. TLB-Datei)](../../build/reference/tlbout-name-dot-tlb-file.md)   
 [Erstellen eines attributierten Programms](../../windows/building-an-attributed-program.md)