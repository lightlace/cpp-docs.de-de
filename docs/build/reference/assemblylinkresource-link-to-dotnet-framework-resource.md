---
title: /ASSEMBLYLINKRESOURCE (Mit .NET Framework-Ressource verknüpfen)
ms.date: 11/04/2016
f1_keywords:
- /ASSEMBLYLINKRESOURCE
- VC.Project.VCLinkerTool.AssemblyLinkResource
helpviewer_keywords:
- -ASSEMBLYLINKRESOURCE linker option
- ASSEMBLYLINKRESOURCE linker option
- /ASSEMBLYLINKRESOURCE linker option
ms.assetid: 8b6ad184-1b33-47a4-8513-4803cf915b64
ms.openlocfilehash: fb707a2721ed40ee3ec37d01b2bbcfcc51f05c38
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "57807805"
---
# <a name="assemblylinkresource-link-to-net-framework-resource"></a>/ASSEMBLYLINKRESOURCE (Mit .NET Framework-Ressource verknüpfen)

```
/ASSEMBLYLINKRESOURCE:filename
```

## <a name="arguments"></a>Argumente

*filename*<br/>
Die Ressourcendatei von .NET Framework, die Sie mit der Assembly verknüpfen möchten

## <a name="remarks"></a>Hinweise

Die/ASSEMBLYLINKRESOURCE-Option erstellt einen Link zu einer .NET Framework-Ressource in der Ausgabedatei an. die Ressourcendatei wird nicht in der Ausgabedatei platziert. [/ ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md) bettet eine Ressourcendatei in die Ausgabedatei.

Verknüpfte Ressourcen sind öffentlich in der Assembly, wenn der Linker erstellt.

/ ASSEMBLYLINKRESOURCE erfordert, dass die Kompilierung ["/ CLR"](clr-common-language-runtime-compilation.md); [/Ln](ln-create-msil-module.md) oder [/noAssembly](noassembly-create-a-msil-module.md) ist mit/ASSEMBLYLINKRESOURCE nicht zulässig.

Wenn *Filename* ist eine .NET Framework-Ressourcendatei erstellt haben, z. B. durch [Resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator) oder in der Entwicklungsumgebung, können sie Zugriff mit Membern in der **System.Resources** Namespace. Weitere Informationen finden Sie unter [System.Resources.ResourceManager](/dotnet/api/system.resources.resourcemanager). Verwenden Sie für alle anderen Ressourcen die **GetManifestResource** \* Methoden in der **System.Reflection.Assembly** Klasse, um Zugriff auf die Ressource zur Laufzeit.

*FileName* kann einem beliebigen Dateiformat sein. Beispielsweise empfiehlt es sich um eine systemeigene DLL Teil der Assembly zu machen, damit es im globalen Assemblycache installiert und aus verwaltetem Code in der Assembly zugegriffen werden kann.

Andere Optionen des Linkers, die Generierung der Zielassembly betreffen sind:

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Option in der **zusätzliche Optionen** Feld.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linker-Referenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
