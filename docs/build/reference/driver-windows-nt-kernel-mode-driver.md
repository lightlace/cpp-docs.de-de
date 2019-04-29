---
title: /DRIVER (Treiber für den Kernelmodus von Windows NT)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.driver
- /driver
helpviewer_keywords:
- kernel mode driver
- -DRIVER linker option
- DRIVER linker option
- /DRIVER linker option
ms.assetid: aeee8e28-5d97-40f5-ba16-9f370fe8a1b8
ms.openlocfilehash: ab7253d7e386bf385bcb3a586c5e0e1c1e860694
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293107"
---
# <a name="driver-windows-nt-kernel-mode-driver"></a>/DRIVER (Treiber für den Kernelmodus von Windows NT)

>/ DRIVER [: UPONLY |: WDM]

## <a name="remarks"></a>Hinweise

Verwenden der **/Driver** Linkeroption, um einen Windows NT-Kernelmodustreiber zu erstellen.

**: UPONLY** bewirkt, dass der Linker Hinzufügen der **IMAGE_FILE_UP_SYSTEM_ONLY** bit den Merkmalen im Ausgabeheader um anzugeben, dass es sich um einen uniprozessortreiber (UP)-Treiber ist. Das Betriebssystem verweigert die Anforderung einen UP-Treiber in einem Multiprozessorsystem von (MP) zu laden.

**/ Driver: WDM** bewirkt, dass der Linker legen Sie die **IMAGE_DLLCHARACTERISTICS_WDM_DRIVER** bit im DllCharacteristics-Feld des optionalen Headers.

Wenn **/Driver** nicht angegeben ist, werden diese Komponenten sind nicht vom Linker festgelegt.

Wenn **/Driver** angegeben wird:

- **/ Fixed: No** ist aktiviert. Weitere Informationen finden Sie unter [/FIXED (Feste Basisadresse)](fixed-fixed-base-address.md).

- Die Erweiterung der Ausgabedatei wird auf .sys festgelegt. Verwendung **/OUT** so ändern Sie den Standarddateinamen und die Erweiterung. Weitere Informationen finden Sie unter [/OUT (Ausgabedateiname)](out-output-file-name.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **System** Eigenschaftenseite.

1. Ändern der **Treiber** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Finden Sie unter [VCLinkerTool.driver Eigenschaft](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.driver?view=visualstudiosdk-2017#Microsoft_VisualStudio_VCProjectEngine_VCLinkerTool_driver).

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
