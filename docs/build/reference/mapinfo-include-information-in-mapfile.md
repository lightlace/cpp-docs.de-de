---
title: /MAPINFO (Daten in Zuordnungsdatei einfügen)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.MapLines
- VC.Project.VCLinkerTool.MapInfoFixups
- VC.Project.VCLinkerTool.MapExports
- /mapinfo
helpviewer_keywords:
- /MAPINFO linker option
- MAPINFO linker option
- -MAPINFO linker option
ms.assetid: 533d2bce-f9b7-4fea-ae1c-0b4864c9d10b
ms.openlocfilehash: bfb8273a8299349ea9aa0b78f1ee14a6cbb6276c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50440312"
---
# <a name="mapinfo-include-information-in-mapfile"></a>/MAPINFO (Daten in Zuordnungsdatei einfügen)

```
/MAPINFO:EXPORTS
```

## <a name="remarks"></a>Hinweise

Die/MapInfo-Option weist den Linker an den angegebenen Informationen in einer Zuordnungsdatei, die erstellt wird, wenn Sie angeben, enthalten die [/MAP](../../build/reference/map-generate-mapfile.md) Option.  EXPORTS weist den Linker an, exportierte Funktionen einzuschließen.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **Debuggen** Eigenschaftenseite.

1. Ändern von der **Zuordnungsexport** Eigenschaften:

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapExports%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)