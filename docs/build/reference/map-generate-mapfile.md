---
title: /MAP (Zuordnungsdatei generieren)
ms.date: 11/04/2016
f1_keywords:
- /map
- VC.Project.VCLinkerTool.MapFileName
- VC.Project.VCLinkerTool.GenerateMapFile
helpviewer_keywords:
- mapfiles, creating linker
- generate mapfile linker option
- mapfile linker option
- mapfiles, information about program being linked
- MAP linker option
- -MAP linker option
- mapfiles, specifying file name
- /MAP linker option
ms.assetid: 9ccce53d-4e36-43da-87b0-7603ddfdea63
ms.openlocfilehash: 8ff2a8f54caa54247050c607004ed328c0d1b11d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436453"
---
# <a name="map-generate-mapfile"></a>/MAP (Zuordnungsdatei generieren)

```
/MAP[:filename]
```

## <a name="arguments"></a>Argumente

*filename*<br/>
Ein vom Benutzer angegebener Name für die Zuordnungsdatei. Sie können den Standardnamen ersetzt.

## <a name="remarks"></a>Hinweise

Die Option/Map weist den Linker an, eine Zuordnungsdatei erstellen.

In der Standardeinstellung benennt der Linker die Map-Datei durch den Basisnamen des Programms und der Erweiterung .map. Der optionale *Filename* können Sie den Standardnamen für eine MAP-Datei zu überschreiben.

Eine MAP-Datei ist eine Textdatei, die die folgende Informationen zu der zu verknüpfende Programm enthält:

- Den Namen des Moduls, der der Basisname der Datei ist

- Der Zeitstempel aus dem Programm-Dateiheader (nicht aus dem Dateisystem)

- Eine Liste der Gruppen im Programm, mit der Startadresse für eine Gruppe (als *Abschnitt*:*Offset*), Länge, Gruppenname und -Klasse

- Eine Liste der öffentlichen Symbole, die mit jeder Adresse (als *Abschnitt*:*Offset*), Symbolnamen, Flatfile-Adresse und der OBJ-Datei, in dem das Symbol definiert ist,

- Der Einstiegspunkt (als *Abschnitt*:*Offset*)

Die [/MapInfo](../../build/reference/mapinfo-include-information-in-mapfile.md) Option gibt an, zusätzliche Informationen, die in die Zuordnungsdatei eingeschlossen werden.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **Debuggen** Eigenschaftenseite.

1. Ändern der **Zuordnungsdatei generieren** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Weitere Informationen finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateMapFile%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapFileName%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)