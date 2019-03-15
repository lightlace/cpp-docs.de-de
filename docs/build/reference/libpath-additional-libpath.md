---
title: /LIBPATH (Libpath-Pfad hinzufügen)
ms.date: 11/04/2016
f1_keywords:
- /libpath
- VC.Project.VCLinkerTool.AdditionalLibraryDirectories
helpviewer_keywords:
- LIBPATH linker option
- /LIBPATH linker option
- Additional Libpath linker option
- environment library path override
- -LIBPATH linker option
- library path linker option
ms.assetid: 7240af0b-9a3d-4d53-8169-2a92cd6958ba
ms.openlocfilehash: ab586c788825a854e7d3cb3760da6e4e5558de3a
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57819882"
---
# <a name="libpath-additional-libpath"></a>/LIBPATH (Libpath-Pfad hinzufügen)

```
/LIBPATH:dir
```

## <a name="parameters"></a>Parameter

*dir*<br/>
Gibt einen Pfad an, dass der Linker sucht, bevor er den in der Umgebungsvariablen LIB angegebenen Pfad durchsucht.

## <a name="remarks"></a>Hinweise

Verwenden Sie die Option/LIBPATH Bibliothekspfad der Umgebung überschreiben. Der Linker wird suchen zuerst im Pfad, indem Sie diese Option angegeben, und suchen Sie dann im Pfad, in der LIB-Umgebungsvariablen angegeben. Sie können nur ein Verzeichnis für jede/LIBPATH-Option angeben, die Sie eingeben. Wenn Sie mehrere Verzeichnisse angeben möchten, müssen Sie mehrere/LIBPATH-Optionen angeben. Der Linker sucht anschließend die angegebenen Verzeichnisse in der Reihenfolge.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **allgemeine** Eigenschaftenseite.

1. Ändern der **Zusätzliche Bibliotheksverzeichnisse** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalLibraryDirectories%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linker-Referenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
