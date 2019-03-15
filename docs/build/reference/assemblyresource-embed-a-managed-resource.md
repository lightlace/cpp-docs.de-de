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
ms.openlocfilehash: 1eac489ffd01f6bd79fc8c5bbda23adb751c9486
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822651"
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

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **Eingabe** Eigenschaftenseite.

1. Ändern der **verwaltete Ressourcendatei einbetten** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EmbedManagedResourceFile%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linker-Referenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
