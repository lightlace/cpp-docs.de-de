---
title: / NATVIS (Natvis zu PDB hinzufügen)
ms.date: 08/10/2017
f1_keywords:
- /natvis
- VC.Project.VCLinkerTool.ImportLIbrary
helpviewer_keywords:
- NATVIS linker option
- /NATVIS linker option
- -NATVIS linker option
- Add Natvis file to PDB
ms.assetid: 8747fc0c-701a-4796-bb4d-818ab4465cca
ms.openlocfilehash: 983cbe4c4bd4164d81b83a23fe19569318d5193c
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57424976"
---
# <a name="natvis-add-natvis-to-pdb"></a>/ NATVIS (Natvis zu PDB hinzufügen)

> / NATVIS:*Dateiname*

## <a name="parameters"></a>Parameter

*filename*<br/>
Eine Natvis-Datei, die PDB-Datei hinzu. Es werden die Debuggervisualisierungen in der Natvis-Datei in die PDB-Datei eingebettet.

## <a name="remarks"></a>Hinweise

Die Option /NATVIS bettet die Debuggervisualisierungen, die in der Natvis-Datei definierten *Filename* in die PDB-Datei, die von LINK generierte. Dadurch kann der Debugger die Visualisierungen unabhängig von der die natvis-Datei angezeigt. Sie können mehrere /NATVIS-Optionen verwenden, um mehr als eine Natvis-Datei in der generierten PDB-Datei einzubetten.

LINK /NATVIS ignoriert, wenn eine PDB-Datei nicht erstellt wird, mit einem [/DEBUG](../../build/reference/debug-generate-debug-info.md) Option. Weitere Informationen zum Erstellen und Verwenden von natvis-Dateien, finden Sie unter [Erstellen benutzerdefinierter Ansichten systemeigener Objekte im Visual Studio-Debugger](/visualstudio/debugger/create-custom-views-of-native-objects).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Befehlszeile** Eigenschaftenseite in der **Linker** Ordner.

1. Die /NATVIS-Option zum Hinzufügen der **zusätzliche Optionen** Textfeld.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Diese Option ist keine programmgesteuerte Variante verfügbar sein.

## <a name="see-also"></a>Siehe auch

[Erstellen Sie benutzerdefinierter Ansichten systemeigener Objekte im Visual Studio-debugger](/visualstudio/debugger/create-custom-views-of-native-objects)<br/>
[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)
