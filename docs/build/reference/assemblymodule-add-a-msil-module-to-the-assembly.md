---
title: /ASSEMBLYMODULE (MSIL-Modul zur Assembly hinzufügen)
ms.date: 11/04/2016
f1_keywords:
- /assemblymodule
- VC.Project.VCLinkerTool.AddModuleNamesToAssembly
helpviewer_keywords:
- ASSEMBLYMODULE linker option
- assemblies [C++], adding modules to
- assemblies [C++]
- /ASSEMBLYMODULE linker option
- -ASSEMBLYMODULE linker option
ms.assetid: 67357da8-e4b6-49fd-932c-329a5777f143
ms.openlocfilehash: d08b5bca38f4ff590a0e1bfb8d8693c374a43444
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621506"
---
# <a name="assemblymodule-add-a-msil-module-to-the-assembly"></a>/ASSEMBLYMODULE (MSIL-Modul zur Assembly hinzufügen)

```
/ASSEMBLYMODULE:filename
```

## <a name="arguments"></a>Argumente

*filename*<br/>
Das Modul, die in dieser Assembly enthalten sein sollen.

## <a name="remarks"></a>Hinweise

Die ASSEMBLYMODULE-Option können Sie einen Modulverweis auf eine Assembly hinzufügen. Typinformationen im Modul wird an das Assemblyprogramm nicht verfügbar, die den Modulverweis hinzugefügt. Jedoch werden Typinformationen im Modul für alle Programme verfügbar sein, die die Assembly verweist.

Verwendung [#using](../../preprocessor/hash-using-directive-cpp.md) Modulverweis auf eine Assembly hinzugefügt und Informationen des Moduls an das Assemblyprogramm zur Verfügung zu stellen.

Betrachten Sie beispielsweise das folgende Szenario:

1. Erstellen Sie ein Modul mit [/ln](../../build/reference/ln-create-msil-module.md).

1. Verwenden Sie ASSEMBLYMODULE in einem anderen Projekt, um das Modul in der aktuellen Kompilierung, enthalten, dadurch wird eine Assembly erstellt werden. Dieses Projekt verweist nicht das Modul mit `#using`.

1. Projekte, die diese Assembly verweist, kann jetzt auch Typen aus dem Modul verwenden.

Andere Optionen des Linkers, die Generierung der Zielassembly betreffen sind:

- [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)

- [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)

- [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)

- [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)

Visual C++-Linker NETMODULE-Dateien als Eingabe akzeptiert und die vom Linker generierte Ausgabedatei ist eine Assembly oder eine NETMODULE-Datei mit keine Abhängigkeit zur Laufzeit auf die NETMODULE-Dateien, die an den Linker eingegeben wurden.  Weitere Informationen finden Sie unter [NETMODULE-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **Eingabe** Eigenschaftenseite.

1. Ändern der **Modul zur Assembly hinzufügen** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AddModuleNamesToAssembly%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)