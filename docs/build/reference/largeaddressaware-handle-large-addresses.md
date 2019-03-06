---
title: /LARGEADDRESSAWARE (Umfangreiche Adressen verarbeiten)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.LargeAddressAware
- /largeaddressaware
helpviewer_keywords:
- LARGEADDRESSAWARE linker option
- -LARGEADDRESSAWARE linker option
- /LARGEADDRESSAWARE linker option
ms.assetid: a29756c8-e893-47a9-9750-1f0d25359385
ms.openlocfilehash: 9ea26a87ce85f71188ca77345e4af055d3ffbf0e
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413744"
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
