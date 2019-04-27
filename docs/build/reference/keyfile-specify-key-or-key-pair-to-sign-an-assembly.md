---
title: /KEYFILE (Schlüsselcontainer oder Schlüsselpaar zum Signieren einer Assembly festlegen)
ms.date: 11/04/2016
f1_keywords:
- /keyfile
- VC.Project.VCLinkerTool.KeyFile
helpviewer_keywords:
- /KEYFILE linker option
- -KEYFILE linker option
- KEYFILE linker option
ms.assetid: 9b71f8c0-541c-4fe5-a0c7-9364f42ecb06
ms.openlocfilehash: d309390c1ac1a19d9d4a982908dbbbac0bd52714
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291560"
---
# <a name="keyfile-specify-key-or-key-pair-to-sign-an-assembly"></a>/KEYFILE (Schlüsselcontainer oder Schlüsselpaar zum Signieren einer Assembly festlegen)

```
/KEYFILE:filename
```

## <a name="arguments"></a>Argumente

*filename*<br/>
Datei, die den Schlüssel enthält. Schließen Sie die Zeichenfolge in doppelte Anführungszeichen (""), wenn sie ein Leerzeichen enthält.

## <a name="remarks"></a>Hinweise

Der Linker fügt den öffentlichen Schlüssel in das Assemblymanifest ein und klicken Sie dann die endgültige Assembly mit dem privaten Schlüssel signiert. Um eine Schlüsseldatei zu generieren, geben [sn – k](/dotnet/framework/tools/sn-exe-strong-name-tool) *Filename* an der Befehlszeile eingeben. Wird als eine signierte Assembly einen starken Namen haben.

Bei der Kompilierung mit [/ln](ln-create-msil-module.md), der Name der Schlüsseldatei im Modul aufbewahrt und in die Assembly, die erstellt wird, wenn Sie eine Assembly, die einen expliziten Verweis auf das Modul Kompilieren über enthält integriert [#using](../../preprocessor/hash-using-directive-cpp.md), oder beim Verknüpfen mit [ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md).

Außerdem können Sie Ihre Verschlüsselungsinformationen übergeben, an dem Linker mit [/keycontainer](keycontainer-specify-a-key-container-to-sign-an-assembly.md). Verwendung [/delaysign](delaysign-partially-sign-an-assembly.md) , wenn Sie eine Assembly teilweise signiert werden soll. Finden Sie unter [Assemblys mit starken Namen (Assemblysignierung) (C++ / CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) für Weitere Informationen zum Signieren einer Assemblys.

Sowohl **/keyfile** und **/keycontainer** angegeben werden (entweder durch die Befehlszeilenoption oder durch ein benutzerdefiniertes Attribut), versucht der Linker zuerst den Schlüsselcontainer. Wenn dies erfolgreich ist, wird die Assembly mit den Informationen im Schlüsselcontainer signiert. Wenn der Linker den Schlüsselcontainer nicht findet, wird mit/KeyFile angegebene Datei versucht. Wenn dies erfolgreich ist, wird die Assembly mit den Informationen in der Schlüsseldatei signiert, und die Schlüsselinformationen werden im Schlüsselcontainer installiert (vergleichbar mit „sn -i“), sodass der Schlüsselcontainer bei der nächsten Kompilierung gültig ist.

Beachten Sie, dass die Schlüsseldatei möglicherweise nur den öffentlichen Schlüssel enthält.

Finden Sie unter [erstellen und Assemblys mit starkem Namen](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies) für Weitere Informationen zum Signieren einer Assemblys.

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

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
