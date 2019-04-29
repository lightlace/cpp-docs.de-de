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
ms.openlocfilehash: c52bfb9e4b6d0e94cecb77c766ac9e82b52f1e66
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317795"
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

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **eingebettete IDL** Eigenschaftenseite.

1. Ändern der **TypeLib-Ressourcen-ID** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryResourceID%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
