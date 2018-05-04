---
title: -Treibers (Windows NT-Kernelmodustreiber) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.driver
- /driver
dev_langs:
- C++
helpviewer_keywords:
- kernel mode driver
- -DRIVER linker option
- DRIVER linker option
- /DRIVER linker option
ms.assetid: aeee8e28-5d97-40f5-ba16-9f370fe8a1b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 66291391ed38c27ce7446eccc6fca227c7c2c2d7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="driver-windows-nt-kernel-mode-driver"></a>/DRIVER (Treiber für den Kernelmodus von Windows NT)

>/ DRIVER [: UPONLY |: WDM]

## <a name="remarks"></a>Hinweise

Verwenden der **/Driver** Linkeroption, um einen Windows NT-Kernelmodustreiber zu erstellen.

**/DRIVER:UPONLY** bewirkt, dass den Linker Hinzufügen der **IMAGE_FILE_UP_SYSTEM_ONLY** -Bit in den Eigenschaften in der Ausgabeheader, um anzugeben, dass es sich um einen Uniprozessor (Treiber DRILLUP) ist. Das Betriebssystem lehnt einen nach-oben-Treiber in einem Multiprozessorsystem (MP) zu laden.

**/ Driver: WDM** bewirkt, dass den Linker Festlegen der **IMAGE_DLLCHARACTERISTICS_WDM_DRIVER** -Bit im optionalen Headerfeld DllCharacteristics.

Wenn **/Driver** nicht angegeben ist, werden diese Bits nicht vom Linker festgelegt werden.

Wenn **/Driver** angegeben ist:

- **Fixed** wirksam wird. Weitere Informationen finden Sie unter [/FIXED (Feste Basisadresse)](../../build/reference/fixed-fixed-base-address.md).

- Die Erweiterung der Ausgabedatei ist auf ".sys" festgelegt. Verwendung **/OUT** so ändern Sie den Standarddateinamen und die Erweiterung. Weitere Informationen finden Sie unter [/OUT (Ausgabedateiname)](../../build/reference/out-output-file-name.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **System** Eigenschaftenseite.

1. Ändern der **Treiber** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Finden Sie unter [VCLinkerTool.driver Eigenschaft](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.driver?view=visualstudiosdk-2017#Microsoft_VisualStudio_VCProjectEngine_VCLinkerTool_driver).

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
[Linkeroptionen](../../build/reference/linker-options.md)
