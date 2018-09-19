---
title: -WINMDDELAYSIGN (eine Winmd teilweise Signieren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.WINMDDelaySign
dev_langs:
- C++
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b31f6ae5baf9aadbb40b4b45f532b344b6b2e037
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723852"
---
# <a name="winmddelaysign-partially-sign-a-winmd"></a>/WINMDDELAYSIGN (eine winmd teilweise signieren)

Ermöglicht es, teilweise Signieren einer Datei für die Windows-Runtime-Metadatendatei (.winmd) durch Platzieren den öffentlichen Schlüssel in der Datei.

```
/WINMDDELAYSIGN[:NO]
```

## <a name="remarks"></a>Hinweise

Ähnelt der [/delaysign](../../build/reference/delaysign-partially-sign-an-assembly.md) -Linkeroption, die in der winmd-Datei angewendet wird. Verwendung **/WINMDDELAYSIGN** sollten Sie nur den öffentlichen Schlüssel in die winmd-Datei einfügen. Wird standardmäßig der Linker verhält sich wie **winmddelaysign** ; angegeben wurden, also werden sie nicht die Winmd-Datei bei.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Linker** Ordner.

1. Wählen Sie die **Windows-Metadaten** Eigenschaftenseite.

1. In der **Assemblysignaturverzögerung für Windows-Metadaten** Dropdown-Liste Wählen Sie die gewünschte Option.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)