---
title: /WINMDFILE (winmd-Datei angeben)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.GenerateWindowsMetadataFile
ms.assetid: 062b41b3-14d6-432c-a361-fdb66e918931
ms.openlocfilehash: 5d24d1d1aad8442f549dcb1aa4bd6414070c282c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57815982"
---
# <a name="winmdfile-specify-winmd-file"></a>/WINMDFILE (winmd-Datei angeben)

Gibt den Dateinamen für die Windows-Runtime-Metadatendatei (.winmd)-Ausgabedatei, die vom generierten der [/WINMD](winmd-generate-windows-metadata.md) -Linkeroption.

```
/WINMDFILE:filename
```

## <a name="remarks"></a>Hinweise

Verwenden Sie den Wert, der im angegebenen `filename` zum Überschreiben des Standardnamens winmd-Datei (`binaryname`.winmd). Beachten Sie, dass Sie keine ".winmd" zum Anfügen `filename`.  Wenn mehrere Werte aufgeführt sind, auf die **/winmdfile** über die Befehlszeile, die letzte Vorrang.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Linker** Ordner.

1. Wählen Sie die **Windows-Metadaten** Eigenschaftenseite.

1. In der **Windows-Metadatendatei** Geben Sie den Dateispeicherort.

## <a name="see-also"></a>Siehe auch

[/WINMD (Windows-Metadaten generieren)](winmd-generate-windows-metadata.md)<br/>
[MSVC-Linker-Referenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
