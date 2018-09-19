---
title: -LIBPATH (Libpath-Pfad) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /libpath
- VC.Project.VCLinkerTool.AdditionalLibraryDirectories
dev_langs:
- C++
helpviewer_keywords:
- LIBPATH linker option
- /LIBPATH linker option
- Additional Libpath linker option
- environment library path override
- -LIBPATH linker option
- library path linker option
ms.assetid: 7240af0b-9a3d-4d53-8169-2a92cd6958ba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 784281df23b0a8d43625766297b6cbbd20179c14
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717196"
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

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **allgemeine** Eigenschaftenseite.

1. Ändern der **Zusätzliche Bibliotheksverzeichnisse** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalLibraryDirectories%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)