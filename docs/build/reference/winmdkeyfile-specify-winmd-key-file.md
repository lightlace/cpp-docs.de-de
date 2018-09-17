---
title: -WINMDKEYFILE (Winmd Schlüsseldatei angeben) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKeyFile
dev_langs:
- C++
ms.assetid: 65d88fdc-fff9-49ea-8cfc-b2f408741734
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d688db3039681fc684e6344e4a27ae7a64544757
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714442"
---
# <a name="winmdkeyfile-specify-winmd-key-file"></a>/WINMDKEYFILE (winmd-Schlüsseldatei angeben)

Gibt an, einen Schlüssel oder ein Schlüsselpaar zum Signieren einer Windows-Runtime-Metadatendatei (.winmd)-Datei.

```
/WINMDKEYFILE:filename
```

## <a name="remarks"></a>Hinweise

Ähnelt der [/keyfile](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) -Linkeroption, die in einer winmd-Datei angewendet wird.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Linker** Ordner.

1. Wählen Sie die **Windows-Metadaten** Eigenschaftenseite.

1. In der **Windows-Metadaten-Schlüsseldatei** Geben Sie den Dateispeicherort.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)