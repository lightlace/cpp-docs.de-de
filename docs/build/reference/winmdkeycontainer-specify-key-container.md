---
title: /WINMDKEYCONTAINER (Schlüsselcontainer angeben)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKEYCONTAINER
ms.assetid: c2fc44dc-7cb5-42b9-897f-1b124928f2f7
ms.openlocfilehash: 0b6cb42fc391d94634ae90e5a4cc17e69a14ff09
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57813070"
---
# <a name="winmdkeycontainer-specify-key-container"></a>/WINMDKEYCONTAINER (Schlüsselcontainer angeben)

Gibt einen Schlüsselcontainer zum Signieren einer Windows-Metadatendatei (.winmd).

```
/WINMDKEYCONTAINER:name
```

## <a name="remarks"></a>Hinweise

Ähnelt der [/keycontainer](keycontainer-specify-a-key-container-to-sign-an-assembly.md) -Linkeroption, die in einer Datei (.winmd) angewendet wird.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Linker** Ordner.

1. Wählen Sie die **Windows-Metadaten** Eigenschaftenseite.

1. In der **Windows-Metadaten-Schlüsselcontainer** Geben Sie den Speicherort.

## <a name="see-also"></a>Siehe auch

[MSVC-Linker-Referenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
