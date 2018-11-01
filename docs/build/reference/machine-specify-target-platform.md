---
title: /MACHINE (Zielplattform angeben)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.TargetMachine
- /machine
helpviewer_keywords:
- mapfiles, creating linker
- target platform
- -MACHINE linker option
- /MACHINE linker option
- MACHINE linker option
ms.assetid: 8d41bf4b-7e53-4ab9-9085-d852b08d31c2
ms.openlocfilehash: 872370269e9ab8acaaa8cafe7fb47b1121bcbb97
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50546435"
---
# <a name="machine-specify-target-platform"></a>/MACHINE (Zielplattform angeben)

```
/MACHINE:{ARM|EBC|X64|X86}
```

## <a name="remarks"></a>Hinweise

Die /MACHINE-Option gibt die Zielplattform für das Programm an.

Normalerweise müssen Sie die /MACHINE-Option nicht angeben. LINK leitet den Computertyp aus den OBJ-Dateien ab. In einigen Fällen LINK kann jedoch nicht ermittelt den Typ des Computers und den Problemen eine [linkertoolwarnung Fehler LNK1113](../../error-messages/tool-errors/linker-tools-error-lnk1113.md). Geben Sie "/MACHINE" an, wenn ein solcher Fehler auftritt.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **erweitert** Eigenschaftenseite.

1. Ändern der **Zielcomputer** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TargetMachine%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)