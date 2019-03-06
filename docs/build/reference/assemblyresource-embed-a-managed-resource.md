---
title: /ASSEMBLYRESOURCE (Verwaltete Ressource einbetten)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.EmbedManagedResourceFile
- /ASSEMBLYRESOURCE
helpviewer_keywords:
- ASSEMBLYRESOURCE linker option
- assemblies [C++]
- -ASSEMBLYRESOURCE linker option
- assemblies [C++], linking resource files
- /ASSEMBLYRESOURCE linker option
ms.assetid: 0ce6e1fb-921b-4b1b-a59c-d35388d789f2
ms.openlocfilehash: c18a014ca645cceb3196fb7efefd227e96f8e1fa
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57416215"
---
# <a name="assemblyresource-embed-a-managed-resource"></a>/ASSEMBLYRESOURCE (Verwaltete Ressource einbetten)

```
/ASSEMBLYRESOURCE:filename[,[name][,PRIVATE]]
```

## <a name="parameters"></a>Parameter

*filename*<br/>
Die verwaltete Ressource, die Sie in dieser Assembly einbetten möchten.

*name*<br/>
Dies ist optional. Der logische Name für die Ressource; der Name, der zum Laden der Ressource verwendet wird. Der Standardwert ist der Name der Datei.

Optional können Sie angeben, wenn die Datei in das Assemblymanifest privat werden soll. In der Standardeinstellung *Namen* in der Assembly öffentlich ist.

## <a name="remarks"></a>Hinweise

Verwenden Sie die Assemblylinkressource-Option, um eine Ressource in einer Assembly einzubetten.

Ressourcen sind öffentlich in der Assembly, wenn der Linker erstellt. Der Linker lässt nicht zu, dass Sie die Ressource in der Assembly umbenennen.

Wenn *Filename* ist eine .NET Framework-Ressourcendatei (.resources)-Datei erstellt, z. B. durch die [Resource File Generator (Resgen.exe)](/dotnet/framework/tools/resgen-exe-resource-file-generator) oder in der Entwicklungsumgebung, können sie Zugriff mit Membern in der **System.Resources** Namespace (finden Sie unter [System.Resources.ResourceManager](/dotnet/api/system.resources.resourcemanager) Informationen). Verwenden Sie für alle anderen Ressourcen die **GetManifestResource** \* Methoden in **System.Reflection.Assembly** Klasse, um Zugriff auf die Ressource zur Laufzeit.

Andere Optionen des Linkers, die Generierung der Zielassembly betreffen sind:

- [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)

- [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **Eingabe** Eigenschaftenseite.

1. Ändern der **verwaltete Ressourcendatei einbetten** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EmbedManagedResourceFile%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)
