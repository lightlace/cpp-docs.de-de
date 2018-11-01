---
title: /NOASSEMBLY (MSIL-Modul erstellen)
ms.date: 11/04/2016
f1_keywords:
- /NOASSEMBLY
- VC.Project.VCLinkerTool.TurnOffAssemblyGeneration
helpviewer_keywords:
- assemblies [C++]
- -NOASSEMBLY linker option
- /NOASSEMBLY linker option
- NOASSEMBLY linker option
- assemblies [C++], not creating an assembly
ms.assetid: 3cea4e70-f451-4395-a626-1930b1b127fe
ms.openlocfilehash: c1508de88b9678898990f0e5b946ad4ced8d6d24
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582038"
---
# <a name="noassembly-create-a-msil-module"></a>/NOASSEMBLY (MSIL-Modul erstellen)

```
/NOASSEMBLY
```

## <a name="remarks"></a>Hinweise

Die/NOASSEMBLY-Option weist den Linker an, ein Bild für die aktuelle Ausgabedatei ohne .NET Framework-Assembly erstellen. Eine MSIL-Ausgabedatei ohne Assemblymanifest wird ein Modul aufgerufen.

Standardmäßig wird eine Assembly erstellt. Sie können auch die [/ln (Create MSIL Module)](../../build/reference/ln-create-msil-module.md) -Compileroption verwenden, um ein Modul zu erstellen.

Andere Optionen des Linkers, die Generierung der Zielassembly betreffen sind:

- [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)

- [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)

- [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **erweitert** Eigenschaftenseite.

1. Ändern der **Assemblygenerierung deaktivieren** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TurnOffAssemblyGeneration%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)