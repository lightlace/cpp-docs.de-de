---
title: -FORCE (DateiAusgabe erzwingen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.ForceLink
- /force
dev_langs:
- C++
helpviewer_keywords:
- FORCE linker option
- file output in linker
- /FORCE linker option
- -FORCE linker option
ms.assetid: b1e9a218-a5eb-4e60-a4a4-65b4be15e5da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 95a746a37183f26585fd013327a964b922589221
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699764"
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