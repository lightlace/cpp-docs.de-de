---
title: /INCREMENTAL (inkrementell verknüpfen)
ms.date: 11/04/2016
f1_keywords:
- /incremental
- VC.Project.VCLinkerTool.LinkIncremental
helpviewer_keywords:
- /INCREMENTAL linker option
- -INCREMENTAL linker option
- INCREMENTAL linker option
- link incrementally option
- LINK tool [C++], options for full linking
- incremental linking
ms.assetid: 135656ff-94fa-4ad4-a613-22e1a2a5d16b
ms.openlocfilehash: 189affe57694a8369e9cf7ac98815cc5888b69aa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62270011"
---
# <a name="incremental-link-incrementally"></a>/INCREMENTAL (inkrementell verknüpfen)

```
/INCREMENTAL[:NO]
```

## <a name="remarks"></a>Hinweise

Steuert, wie der Linker inkrementelle Verknüpfungen behandelt.

Standardmäßig wird der Linker im inkrementellen Modus ausgeführt. Um einen inkrementellen Standardlink zu überschreiben, müssen Sie "/INCREMENTAL:NO" angeben.

Ein inkrementell verknüpftes Programm ist funktionell gleichwertig mit der ein Programm, das nicht inkrementell verknüpft ist. Aber da es für spätere inkrementelle Links, eine inkrementell verknüpfte ausführbare Datei, die statische Bibliothek oder Dynamic Link Library-Datei vorbereitet wird:

- Ist größer als ein nicht inkrementell verknüpftes Programm aufgrund von Code und Daten. Auffüllung ermöglicht es den Linker, die Größe von Funktionen und Daten zu erhöhen, ohne die Datei neu zu erstellen.

- Sie kann Sprung-Thunks enthalten, um das Verschieben von Funktionen auf neue Adressen zu verarbeiten.

   > [!NOTE]
   > Um sicherzustellen, dass das Releasebuild keine Füllzeichen oder Thunks enthält, wird verknüpfen Sie das Programm nicht inkrementell.

Um unabhängig von der Standardeinstellung die inkrementelle Verknüpfung vorzunehmen, müssen Sie "/INCREMENTAL" angeben. Wenn diese Option ausgewählt ist, wird der Linker eine Warnung ausgegeben, wenn er keine inkrementelle Verknüpfung kann nicht, und klicken Sie dann das Programm nicht inkrementell verknüpft. Bei bestimmten Optionen und in bestimmten Situationen wird "/INCREMENTAL" überschrieben.

Die meisten Programme können inkrementell verknüpft werden. Einige Änderungen sind jedoch zu umfangreich, und bestimmte Optionen sind mit dem inkrementellen Verknüpfen nicht kompatibel. LINK führt einen vollständigen Verknüpfungsvorgang durch, wenn eine der folgenden Optionen angegeben wurde:

- Inkrementell verknüpfen wurde nicht ausgewählt ("/INCREMENTAL:NO").

- "/OPT:REF" wurde ausgewählt.

- "/OPT:ICF" wurde ausgewählt.

- "/OPT:LBR" wurde ausgewählt.

- "/ORDER" wurde ausgewählt.

/ INCREMENTAL wird impliziert, wenn [/DEBUG](debug-generate-debug-info.md) angegeben ist.

Außerdem führt "LINK" einen vollständigen Verknüpfungsvorgang durch, wenn eine der folgenden Situationen eintritt:

- Die inkrementelle Statusdatei (ILK-Datei) fehlt. (LINK erstellt eine neue ILK-Datei zur Vorbereitung auf spätere inkrementelle Verknüpfungen.)

- Es sind keine Schreibrechte für die ILK-Datei vorhanden. (LINK berücksichtigt die ILK-Datei und verknüpft nicht inkrementell.)

- Die EXE- oder DLL-Ausgabedatei fehlt.

- Der Zeitstempel der ILK-, EXE- oder DLL-Datei hat sich geändert.

- Eine LINK-Option hat sich geändert. Die meisten LINK-Optionen führen, wenn sie zwischen zwei Erstellungsvorgängen geändert werden, zu einer vollständigen Verknüpfung.

- Eine Objektdatei (OBJ-Datei) wurde hinzugefügt oder ausgelassen.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Linker** Ordner.

1. Wählen Sie die Eigenschaftenseite **Allgemein** aus.

1. Ändern der **inkrementelles Verknüpfen aktivieren** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkIncremental%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
