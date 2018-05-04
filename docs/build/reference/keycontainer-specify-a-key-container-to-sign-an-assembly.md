---
title: -KEYCONTAINER (Schlüsselcontainer zum Signieren einer Assembly festlegen) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.KeyContainer
- /keycontainer
dev_langs:
- C++
helpviewer_keywords:
- KEYCONTAINER linker option
- /KEYCONTAINER linker option
- -KEYCONTAINER linker option
ms.assetid: 94882d12-b77a-49c7-96d0-18a31aee001e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13058978b0833a17abbbfb68a2ed753aacfb6d49
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="keycontainer-specify-a-key-container-to-sign-an-assembly"></a>/KEYCONTAINER (Schlüsselcontainer zum Signieren einer Assembly festlegen)
```  
/KEYCONTAINER:name  
```  
  
## <a name="remarks"></a>Hinweise  
 wobei  
  
 *name*  
 Container, der den Schlüssel enthält. Schließen Sie die Zeichenfolge in doppelte Anführungszeichen (""), wenn es sich um ein Leerzeichen enthält.  
  
## <a name="remarks"></a>Hinweise  
 Der Linker erstellt eine signierte Assembly, indem ein öffentlicher Schlüssel in das Assemblymanifest eingefügt und die endgültige Assembly mit dem privaten Schlüssel signiert. Um eine Schlüsseldatei zu generieren, geben Sie [sn – k](/dotnet/framework/tools/sn-exe-strong-name-tool) *Filename* in der Befehlszeile. **"sn" -i** installiert das Schlüsselpaar in einem Container.  
  
 Beim Kompilieren mit [/ln](../../build/reference/ln-create-msil-module.md), der Namen der Datei mit dem Schlüssel ist im Modul gespeichert und in die Assembly, die erstellt wird, wenn eine Assembly zu, die Kompilieren über keinen expliziten Verweis auf das Modul enthält integriert [#using](../../preprocessor/hash-using-directive-cpp.md), oder wenn die Verknüpfung mit [ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md).  
  
 Sie können auch die Verschlüsselungsinformationen mit an den Compiler übergeben [/keyfile](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md). Verwendung [/delaysign /](../../build/reference/delaysign-partially-sign-an-assembly.md) , wenn Sie eine Assembly teilweise signiert werden soll. Finden Sie unter [Assemblys mit starken Namen (Assembly signieren) (C + c++ / CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) für Weitere Informationen zum Signieren einer Assemblys.  
  
 Andere Optionen des Linkers, die beeinflussen Generieren der Assembly sind:  
  
-   [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Option in der **Zusatzoptionen** Feld.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)