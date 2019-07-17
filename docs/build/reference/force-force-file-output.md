---
title: /FORCE (Dateiausgabe erzwingen)
ms.date: 07/19/2019
f1_keywords:
- VC.Project.VCLinkerTool.ForceLink
- /force
helpviewer_keywords:
- FORCE linker option
- file output in linker
- /FORCE linker option
- -FORCE linker option
ms.assetid: b1e9a218-a5eb-4e60-a4a4-65b4be15e5da
ms.openlocfilehash: 28b1c21382832c8775ffe0406038a482e74076c5
ms.sourcegitcommit: 7f5b29e24e1be9b5985044a030977485fea0b50c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/17/2019
ms.locfileid: "68299719"
---
# <a name="force-force-file-output"></a>/FORCE (Dateiausgabe erzwingen)

```
/FORCE:[MULTIPLE|UNRESOLVED]
```

## <a name="remarks"></a>Hinweise

Die/Force-Option weist den Linker an, eine gültige exe-Datei oder dll zu erstellen, auch wenn auf ein Symbol verwiesen wird, aber nicht definiert oder multipliziert definiert ist.

Die/Force-Option kann ein optionales Argument annehmen:

- Verwenden Sie/Force: Multiple, um eine Ausgabedatei zu erstellen, unabhängig davon, ob Link mehr als eine Definition für ein Symbol findet oder nicht.

- Verwenden Sie/Force: nicht aufgelöst, um eine Ausgabedatei zu erstellen, unabhängig davon, ob Link ein nicht definiertes Symbol findet /Force: nicht aufgelöste wird ignoriert, wenn das Einstiegspunkt Symbol nicht aufgelöst wird.

/Force ohne Argumente impliziert sowohl mehrfach als auch nicht aufgelöst.

Eine mit dieser Option erstellte Datei kann möglicherweise nicht wie erwartet ausgeführt werden. Der Linker wird nicht inkrementell verknüpft, wenn die/Force-Option angegeben wird.

Wenn ein Modul mit **/CLR**kompiliert wird, erstellt **/Force** kein Image.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf das Projekt, und wählen Sie **Eigenschaften**aus. 

1. Klicken Sie auf den Ordner **Linker**.

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Option im Feld **zusätzliche Optionen** ein.

Weitere Informationen finden Sie unter [Festlegen des Compilers und der Buildeigenschaften](../working-with-project-properties.md).

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
