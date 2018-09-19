---
title: -NATVIS (Natvis zu PDB hinzufügen) | Microsoft-Dokumentation
ms.date: 08/10/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /natvis
- VC.Project.VCLinkerTool.ImportLIbrary
dev_langs:
- C++
helpviewer_keywords:
- NATVIS linker option
- /NATVIS linker option
- -NATVIS linker option
- Add Natvis file to PDB
ms.assetid: 8747fc0c-701a-4796-bb4d-818ab4465cca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2c1a20fef785c0267eb630bf044c8cb9609605e2
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45708122"
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