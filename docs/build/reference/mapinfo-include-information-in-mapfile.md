---
title: -MAPINFO (Informationen in Zuordnungsdatei einbeziehen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.MapLines
- VC.Project.VCLinkerTool.MapInfoFixups
- VC.Project.VCLinkerTool.MapExports
- /mapinfo
dev_langs:
- C++
helpviewer_keywords:
- /MAPINFO linker option
- MAPINFO linker option
- -MAPINFO linker option
ms.assetid: 533d2bce-f9b7-4fea-ae1c-0b4864c9d10b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f52e044962007c4a820bf234d45b5cb9ffd584f6
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723085"
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