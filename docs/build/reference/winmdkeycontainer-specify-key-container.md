---
title: /WINMDKEYCONTAINER (Schlüsselcontainer angeben)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKEYCONTAINER
ms.assetid: c2fc44dc-7cb5-42b9-897f-1b124928f2f7
ms.openlocfilehash: 5424b928f80bf73aedb731f835b72d20bfd0c4a2
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57416591"
---
# <a name="winmdkeycontainer-specify-key-container"></a>/WINMDKEYCONTAINER (Schlüsselcontainer angeben)

Gibt einen Schlüsselcontainer zum Signieren einer Windows-Metadatendatei (.winmd).

```
/WINMDKEYCONTAINER:name
```

## <a name="remarks"></a>Hinweise

Ähnelt der [/keycontainer](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md) -Linkeroption, die in einer Datei (.winmd) angewendet wird.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Linker** Ordner.

1. Wählen Sie die **Windows-Metadaten** Eigenschaftenseite.

1. In der **Windows-Metadaten-Schlüsselcontainer** Geben Sie den Speicherort.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)
