---
title: /HEAP (Heapgröße festlegen)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.HeapCommitSize
- /heap
- VC.Project.VCLinkerTool.HeapReserveSize
helpviewer_keywords:
- -HEAP linker option
- heap allocation, setting heap size
- /HEAP linker option
- HEAP linker option
ms.assetid: a3f71927-7f1d-492c-9fdb-dfccb1a043da
ms.openlocfilehash: 715eaa358d052d4ae646f38f2e784f0235dffccb
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57813292"
---
# <a name="heap-set-heap-size"></a>/HEAP (Heapgröße festlegen)

```
/HEAP:reserve[,commit]
```

## <a name="remarks"></a>Hinweise

Durch die Option wird die Größe des Heaps in Bytes. Diese Option ist nur für die Verwendung, wenn Sie eine .exe-Datei zu erstellen.

Die *reservieren* Argument gibt die Gesamtgröße der Heapzuordnung im virtuellen Speicher. Die Standard-Heapgröße beträgt 1 MB. Der Linker rundet den angegebenen Wert in die nächsten 4 Bytes ab.

Der optionale `commit` Argument gibt die Menge an physikalischem Arbeitsspeicher, zu einem Zeitpunkt zuordnen. Die Zusicherung von virtuellem Speicher bewirkt die Belegung von Speicher in der Auslagerungsdatei. Eine höhere `commit` -Wert spart Zeit, wenn die Anwendung benötigt mehr Heapspeicher, erhöht aber die arbeitsspeicheranforderungen und möglicherweise die Startzeit.

Geben Sie die *reservieren* und `commit` Werten in Decimal oder C-Notation.

Diese Funktion steht auch über eine Moduldefinitionsdatei mit [HEAPSIZE](heapsize.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **System** Eigenschaftenseite.

1. Ändern der **Heapgröße Commit** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Weitere Informationen finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapReserveSize%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.HeapCommitSize%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linker-Referenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
