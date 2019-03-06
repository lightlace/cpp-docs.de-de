---
title: /FORCE (Dateiausgabe erzwingen)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.ForceLink
- /force
helpviewer_keywords:
- FORCE linker option
- file output in linker
- /FORCE linker option
- -FORCE linker option
ms.assetid: b1e9a218-a5eb-4e60-a4a4-65b4be15e5da
ms.openlocfilehash: fb5b5b586a9c428d20a7e931a312c8903eb6e8e2
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57424469"
---
# <a name="force-force-file-output"></a>/FORCE (Dateiausgabe erzwingen)

```
/FORCE:[MULTIPLE|UNRESOLVED]
```

## <a name="remarks"></a>Hinweise

Der/Force-Option weist den Linker zum Erstellen einer gültigen .exe-Datei oder DLL auch, wenn ein Symbol, aber nicht verwiesen wird definiert oder mehrfach definiert ist.

Die Option/Force kann es sich um ein optionales Argument aufweisen:

- Verwenden Sie Multiple, um eine Ausgabedatei erstellt, und zwar unabhängig davon, ob LINK mehr als eine Definition für ein Symbol findet.

- Verwenden Sie/Force: Erstellen einer Ausgabedatei, und zwar unabhängig davon, ob LINK ein nicht definiertes Symbol findet nicht AUFGELÖST. / FORCE: nicht AUFGELÖSTE wird ignoriert, wenn das Einstiegspunktsymbol nicht aufgelöst wird.

/ FORCE ohne Argumente impliziert sowohl mehrfach als auch nicht aufgelöst werden.

Eine mit dieser Option erstellte Datei kann nicht wie erwartet ausgeführt. Der Linker wird kein inkrementelles Verknüpfen, wenn der/Force-Option angegeben wird.

Wenn die Kompilierung mit einem Modul **"/ CLR"**, **/FORCE** ein Bild wird nicht erstellt werden.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Option in der **zusätzliche Optionen** Feld.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)
