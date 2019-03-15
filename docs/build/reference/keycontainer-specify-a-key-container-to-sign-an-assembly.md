---
title: /KEYCONTAINER (Schlüsselcontainer zum Signieren einer Assembly festlegen)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.KeyContainer
- /keycontainer
helpviewer_keywords:
- KEYCONTAINER linker option
- /KEYCONTAINER linker option
- -KEYCONTAINER linker option
ms.assetid: 94882d12-b77a-49c7-96d0-18a31aee001e
ms.openlocfilehash: 96d2f5fed0e450224f82ee909cea9d56082505fb
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807844"
---
# <a name="keycontainer-specify-a-key-container-to-sign-an-assembly"></a>/KEYCONTAINER (Schlüsselcontainer zum Signieren einer Assembly festlegen)

```
/KEYCONTAINER:name
```

## <a name="arguments"></a>Argumente

*name*<br/>
Container, der den Schlüssel enthält. Schließen Sie die Zeichenfolge in doppelte Anführungszeichen (""), wenn sie ein Leerzeichen enthält.

## <a name="remarks"></a>Hinweise

Der Linker erstellt eine signierte Assembly, indem er einen öffentlichen Schlüssel in das Assemblymanifest einfügt und die endgültige Assembly mit dem privaten Schlüssel signiert. Um eine Schlüsseldatei zu generieren, geben [sn – k](/dotnet/framework/tools/sn-exe-strong-name-tool) *Filename* an der Befehlszeile eingeben. **sn -i** installiert das Schlüsselpaar in einem Container.

Bei der Kompilierung mit [/ln](ln-create-msil-module.md), der Name der Schlüsseldatei im Modul aufbewahrt und in die Assembly, die erstellt wird, wenn Sie eine Assembly, die einen expliziten Verweis auf das Modul Kompilieren über enthält integriert [#using](../../preprocessor/hash-using-directive-cpp.md), oder beim Verknüpfen mit [ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md).

Sie können auch Ihre Verschlüsselungsinformationen mit an den Compiler übergeben [/keyfile](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md). Verwendung [/delaysign](delaysign-partially-sign-an-assembly.md) , wenn Sie eine Assembly teilweise signiert werden soll. Finden Sie unter [Assemblys mit starken Namen (Assemblysignierung) (C++ / CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) für Weitere Informationen zum Signieren einer Assemblys.

Andere Optionen des Linkers, die Generierung der Zielassembly betreffen sind:

- [/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)

- [/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)

- [/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)

- [/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)

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
