---
title: -ASSEMBLYLINKRESOURCE (mit .NET Framework-Ressource verknüpfen) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /ASSEMBLYLINKRESOURCE
- VC.Project.VCLinkerTool.AssemblyLinkResource
dev_langs:
- C++
helpviewer_keywords:
- -ASSEMBLYLINKRESOURCE linker option
- ASSEMBLYLINKRESOURCE linker option
- /ASSEMBLYLINKRESOURCE linker option
ms.assetid: 8b6ad184-1b33-47a4-8513-4803cf915b64
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a922ac1a96a59d574f46f7b04db8b160a5079918
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="assemblylinkresource-link-to-net-framework-resource"></a>/ASSEMBLYLINKRESOURCE (Mit .NET Framework-Ressource verknüpfen)
```  
/ASSEMBLYLINKRESOURCE:filename  
```  
  
## <a name="remarks"></a>Hinweise  
 Dabei gilt:  
  
 *filename*  
 Die Ressourcendatei von .NET Framework, die Sie mit der Assembly verknüpfen möchten  
  
## <a name="remarks"></a>Hinweise  
 Die Option/ASSEMBLYLINKRESOURCE erstellt einen Link zu einer .NET Framework-Ressource in die Ausgabedatei an. die Ressourcendatei wird nicht in die Ausgabedatei eingefügt. [/ ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md) eine Ressourcendatei in die Ausgabedatei eingebettet.  
  
 Verknüpfte Ressourcen sind in der Assembly, die bei Erstellung mit der Linker öffentlich.  
  
 / ASSEMBLYLINKRESOURCE erfordert, dass es sich bei der Kompilierung ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md); [/Ln](../../build/reference/ln-create-msil-module.md) oder [/noAssembly](../../build/reference/noassembly-create-a-msil-module.md) ist nicht mit/ASSEMBLYLINKRESOURCE zulässig.  
  
 Wenn *Filename* ist eine .NET Framework-Ressourcendatei erstellt haben, z. B. durch [Resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator) oder in der Entwicklungsumgebung können sie Zugriff mit Membern in der **System.Resources** Namespace. Weitere Informationen finden Sie unter [System.Resources.ResourceManager](https://msdn.microsoft.com/en-us/library/system.resources.resourcemanager.aspx). Verwenden Sie für alle anderen Ressourcen die **GetManifestResource** \* Methoden in der **System.Reflection.Assembly** Klasse, um zur Laufzeit auf die Ressource zugreifen.  
  
 *FileName* kann beliebiges Dateiformat aufweisen. Beispielsweise empfiehlt es sich um eine systemeigene DLL Teil der Assembly zu machen, damit im globalen Assemblycache installiert und aus verwaltetem Code in der Assembly zugegriffen werden kann.  
  
 Andere Optionen des Linkers, die beeinflussen Generieren der Assembly sind:  
  
-   [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
-   [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
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