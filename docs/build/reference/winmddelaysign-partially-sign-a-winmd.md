---
title: /WINMDDELAYSIGN (eine winmd teilweise signieren)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDDelaySign
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
ms.openlocfilehash: 85698362a753e147a28922db19b456d4d649e55d
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57421459"
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
