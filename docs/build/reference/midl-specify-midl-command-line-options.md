---
title: -MIDL (MIDL-Befehlszeilenoptionen angeben) | Microsoft-Dokumentation
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
ms.openlocfilehash: 7b3f20fddd657d1e5e57caf65ecc8e2c52afbf12
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2018
ms.locfileid: "42571385"
---
# <a name="midl-specify-midl-command-line-options"></a>/MIDL (Optionen für MIDL-Befehlszeile festlegen)
```  
/MIDL:@file  
```  
  
## <a name="remarks"></a>Hinweise  
 Dabei gilt:  
  
 `file`  
 Der Name der Datei, die enthält [MIDL-Befehlszeilenoptionen](http://msdn.microsoft.com/library/windows/desktop/aa366839).  
  
## <a name="remarks"></a>Hinweise  
 Bei allen Optionen für die Konvertierung einer IDL-Datei in eine TLB-Datei zugewiesen werden, der `file`; MIDL-Befehlszeilenoptionen können nicht auf dem Linker Befehlszeile angegeben werden. Wenn/MIDL nicht angegeben ist, wird der MIDL-Compiler mit nur den IDL-Dateinamen und keine anderen Optionen aufgerufen werden.  
  
 Die Datei sollte eine MIDL-Befehlszeilenoption pro Zeile enthalten.  
  
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
 [/ IGNOREIDL (keine Attribute in MIDL verarbeiten)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [/ TLBOUT (Name. TLB-Datei)](../../build/reference/tlbout-name-dot-tlb-file.md)   
 [Erstellen eines attributierten Programms](../../windows/building-an-attributed-program.md)