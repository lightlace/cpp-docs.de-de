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
ms.openlocfilehash: 728e8a84ff8d1afac99f99dbb975c7fd9360bcc1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273015"
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

1. Erstellen Sie ein Modul mit [/ln](ln-create-msil-module.md).

1. Verwenden Sie ASSEMBLYMODULE in einem anderen Projekt, um das Modul in der aktuellen Kompilierung, enthalten, dadurch wird eine Assembly erstellt werden. Dieses Projekt verweist nicht das Modul mit `#using`.

1. Projekte, die diese Assembly verweist, kann jetzt auch Typen aus dem Modul verwenden.

Andere Optionen des Linkers, die Generierung der Zielassembly betreffen sind:

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

- [/DELAYSIGN](delaysign-partially-sign-an-assembly.md)

- [/NOASSEMBLY](noassembly-create-a-msil-module.md)

- [/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)

- [/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)

Der MSVC-Linker NETMODULE-Dateien als Eingabe akzeptiert und die vom Linker generierte Ausgabedatei ist eine Assembly oder eine NETMODULE-Datei mit keine Abhängigkeit zur Laufzeit auf die NETMODULE-Dateien, die an den Linker eingegeben wurden.  Weitere Informationen finden Sie unter [NETMODULE-Dateien als Eingabe für den Linker](netmodule-files-as-linker-input.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **Eingabe** Eigenschaftenseite.

1. Ändern der **Modul zur Assembly hinzufügen** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AddModuleNamesToAssembly%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
