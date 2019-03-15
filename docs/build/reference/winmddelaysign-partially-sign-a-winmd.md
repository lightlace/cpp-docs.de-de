---
title: /WINMDDELAYSIGN (eine winmd teilweise signieren)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDDelaySign
ms.assetid: 445cd602-62cb-400a-8e3a-4beb6572724d
ms.openlocfilehash: 5e6eab3fbc40543b634f03da826d3bd3477b9623
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57421459"
---
# <a name="winmddelaysign-partially-sign-a-winmd"></a>/WINMDDELAYSIGN (eine winmd teilweise signieren)

Ermöglicht es, teilweise Signieren einer Datei für die Windows-Runtime-Metadatendatei (.winmd) durch Platzieren den öffentlichen Schlüssel in der Datei.

```
/WINMDDELAYSIGN[:NO]
```

## <a name="remarks"></a>Hinweise

Ähnelt der [/delaysign](delaysign-partially-sign-an-assembly.md) -Linkeroption, die in der winmd-Datei angewendet wird. Verwendung **/WINMDDELAYSIGN** sollten Sie nur den öffentlichen Schlüssel in die winmd-Datei einfügen. Wird standardmäßig der Linker verhält sich wie **winmddelaysign** ; angegeben wurden, also werden sie nicht die Winmd-Datei bei.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Linker** Ordner.

1. Wählen Sie die **Windows-Metadaten** Eigenschaftenseite.

1. In der **Assemblysignaturverzögerung für Windows-Metadaten** Dropdown-Liste Wählen Sie die gewünschte Option.

## <a name="see-also"></a>Siehe auch

[MSVC-Linker-Referenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
