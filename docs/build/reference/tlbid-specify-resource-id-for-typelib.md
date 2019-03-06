---
title: /TLBID (Ressourcen-ID für TypeLib festlegen)
ms.date: 11/04/2016
f1_keywords:
- /tlbid
- VC.Project.VCLinkerTool.TypeLibraryResourceID
helpviewer_keywords:
- tlb files, specifying resource ID
- -TLBID linker option
- .tlb files, specifying resource ID
- /TLBID linker option
- TLBID linker option
- type libraries, specifying resource ID
ms.assetid: 434b28a2-4656-4d52-ac82-8b18bf486fb2
ms.openlocfilehash: b65ef73e2c7802b960b8480fff83c96fbe869293
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57426471"
---
# <a name="tlbid-specify-resource-id-for-typelib"></a>/TLBID (Ressourcen-ID für TypeLib festlegen)

```
/TLBID:id
```

## <a name="arguments"></a>Argumente

*ID*<br/>
Ein vom Benutzer angegebener Wert für die vom Linker erstellte Typbibliothek. Es überschreibt die Standard-Ressourcen-ID 1.

## <a name="remarks"></a>Hinweise

Beim Kompilieren eines Programms, das Attribute verwendet, erstellt der Linker eine Typbibliothek. Der Linker weist eine Ressourcen-ID von 1 auf die Typbibliothek.

Wenn diese Ressourcen-ID mit einem Ihrer vorhandenen Ressourcen in Konflikt steht, können Sie eine andere ID mit/TLBID angeben. Der Wertebereich, die Sie an übergeben können `id` 1 und 65535.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **eingebettete IDL** Eigenschaftenseite.

1. Ändern der **TypeLib-Ressourcen-ID** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryResourceID%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)
