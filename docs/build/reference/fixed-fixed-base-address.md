---
title: /FIXED (Feste Basisadresse)
ms.date: 11/04/2016
f1_keywords:
- /fixed
- VC.Project.VCLinkerTool.FixedBaseAddress
helpviewer_keywords:
- preferred base address for loading program
- /FIXED linker option
- -FIXED linker option
- FIXED linker option
ms.assetid: 929bba5e-b7d8-40ed-943e-056aa3710fc5
ms.openlocfilehash: 6cc89df76e48ee258a7c6608aab12573ab11729b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811523"
---
# <a name="fixed-fixed-base-address"></a>/FIXED (Feste Basisadresse)

```
/FIXED[:NO]
```

## <a name="remarks"></a>Hinweise

Weist das Betriebssystem an, das Programm nur an seine bevorzugte Basisadresse zu laden. Wenn diese Basisadresse nicht zur Verfügung steht, lädt das Betriebssystem die Datei nicht. Weitere Informationen finden Sie unter [/BASE (Basisadresse)](base-base-address.md).

Für eine DLL ist "/FIXED:NO" die Standardeinstellung; bei anderen Projekttypen lautet die Standardeinstellung "/FIXED".

Bei Angabe von "/FIXED" generiert LINK keinen Verschiebungsabschnitt im Programm. Wenn das Betriebssystem das Programm zur Laufzeit nicht an der angegebenen Adresse laden kann, wird eine Fehlermeldung ausgegeben, und der Ladevorgang wird nicht ausgeführt.

Bei Angabe von "/FIXED:NO" wird ein Verschiebungsabschnitt im Programm generiert.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Linker** Ordner.

1. Wählen Sie die **Befehlszeile** Eigenschaftenseite.

1. Geben Sie den Optionsnamen und Festlegen von in die **zusätzliche Optionen** Feld.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linker-Referenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
