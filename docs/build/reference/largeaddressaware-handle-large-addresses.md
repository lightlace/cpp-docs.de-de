---
title: -LARGEADDRESSAWARE (umfangreiche Adressen verarbeiten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.LargeAddressAware
- /largeaddressaware
dev_langs:
- C++
helpviewer_keywords:
- LARGEADDRESSAWARE linker option
- -LARGEADDRESSAWARE linker option
- /LARGEADDRESSAWARE linker option
ms.assetid: a29756c8-e893-47a9-9750-1f0d25359385
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0a68b18f912d7e6ca0f0f642c85e8439be0e5b67
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726325"
---
# <a name="largeaddressaware-handle-large-addresses"></a>/LARGEADDRESSAWARE (Umfangreiche Adressen verarbeiten)

```
/LARGEADDRESSAWARE[:NO]
```

## <a name="remarks"></a>Hinweise

Die/LARGEADDRESSAWARE-Option weist den Linker, dass die Anwendung Adressen, die größer als 2 Gigabyte verarbeiten kann. In der 64-Bit-Compiler ist diese Option standardmäßig aktiviert. In der 32-Bit-Compiler ist/LARGEADDRESSAWARE: No aktiviert, wenn/LARGEADDRESSAWARE nicht anderweitig in der Linkerzeile angegeben ist.

Wenn eine Anwendung mit/LARGEADDRESSAWARE, DUMPBIN verknüpft wurde [/Headers](../../build/reference/headers.md) zeigt Informationen zu diesem Zweck an.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **System** Eigenschaftenseite.

1. Ändern der **große Adressen aktivieren** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LargeAddressAware%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)