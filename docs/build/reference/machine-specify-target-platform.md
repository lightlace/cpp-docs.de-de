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
ms.openlocfilehash: e64aa7b2ca9e50ebdc0760f64a9b25e851b45310
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818127"
---
# <a name="machine-specify-target-platform"></a>/MACHINE (Zielplattform angeben)

```
/MACHINE:{ARM|EBC|X64|X86}
```

## <a name="remarks"></a>Hinweise

Die /MACHINE-Option gibt die Zielplattform für das Programm an.

Normalerweise müssen Sie die /MACHINE-Option nicht angeben. LINK leitet den Computertyp aus den OBJ-Dateien ab. In einigen Fällen LINK kann jedoch nicht ermittelt den Typ des Computers und den Problemen eine [linkertoolwarnung Fehler LNK1113](../../error-messages/tool-errors/linker-tools-error-lnk1113.md). Geben Sie "/MACHINE" an, wenn ein solcher Fehler auftritt.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **erweitert** Eigenschaftenseite.

1. Ändern der **Zielcomputer** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TargetMachine%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linker-Referenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
