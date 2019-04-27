---
title: /DELAYLOAD (Laden von Import verzögern)
ms.date: 11/04/2016
f1_keywords:
- /delayload
- VC.Project.VCLinkerTool.DelayLoadDLLS
helpviewer_keywords:
- DELAYLOAD linker option
- -DELAYLOAD linker option
- /DELAYLOAD linker option
- delayed loading of DLLs, /DELAYLOAD option
ms.assetid: 39ea0f1e-5c01-450f-9c75-2d9761ff9b28
ms.openlocfilehash: e92b470b7b5e76b39371f333cbbda150e7f6e8c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273354"
---
# <a name="delayload-delay-load-import"></a>/DELAYLOAD (Laden von Import verzögern)

> **/ DELAYLOAD:**_Dllname_

## <a name="parameters"></a>Parameter

*dllname*<br/>
Der Name einer DLL, die mit einer Verzögerung geladen werden soll.

## <a name="remarks"></a>Hinweise

Die /DELAYLOAD-Option bewirkt, dass die durch `dllname` angegebene DLL nur beim ersten Aufruf einer Funktion in dieser DLL vom Programm geladen wird. Weitere Informationen finden Sie unter [Linkerunterstützung für verzögert geladene DLLs](linker-support-for-delay-loaded-dlls.md). Sie können diese Option so oft wie notwendig verwenden, um die von Ihnen gewünschte Anzahl von DLLs festzulegen. Beim Verknüpfen des Programms müssen Sie "Delayimp.lib" verwenden. Sie können aber auch eine eigene Hilfsfunktion für das verzögerte Laden implementieren.

Die [/DELAY](delay-delay-load-import-settings.md) Option gibt an, zum Binden und laden die Optionen für die einzelnen verzögert geladenen DLLs.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. In der **Linker** Ordner, wählen die **Eingabe** Eigenschaftenseite.

1. Ändern der **verzögert geladene DLLs** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
