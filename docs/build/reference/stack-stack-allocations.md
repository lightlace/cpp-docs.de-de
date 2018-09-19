---
title: -STACK (Stapelreservierungen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.StackReserveSize
- VC.Project.VCLinkerTool.StackCommitSize
- /stack
dev_langs:
- C++
helpviewer_keywords:
- STACK linker option
- -STACK linker option
- memory allocation, stack
- /STACK linker option
- stack, setting size
ms.assetid: 73283660-e4bd-47cc-b5ca-04c5d739034c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7bd61f1cd56043dd7e2a2234630d722850850735
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703338"
---
# <a name="stack-stack-allocations"></a>/STACK (Stapelreservierungen)

```
/STACK:reserve[,commit]
```

## <a name="remarks"></a>Hinweise

Durch die Option /STACK wird die Stapelgröße in Bytes festgelegt. Verwenden Sie diese Option nur zum Erstellen von EXE-Dateien.

Der `reserve`-Wert gibt die gesamte Stapelzuordnung im virtuellen Speicher an. Für ARM X86- und X64 Computer, die standardmäßige Stapelgröße beträgt 1 MB.

Wie das `commit`-Argument interpretiert wird, hängt vom jeweiligen Betriebssystem ab. Unter Windows RT wird damit die physische Speichermenge bezeichnet, die zu einem Zeitpunkt belegt werden soll. Die Zusicherung von virtuellem Speicher bewirkt die Belegung von Speicher in der Auslagerungsdatei. Ein höherer `commit`-Wert spart Zeit, wenn die Anwendung mehr Stapelspeicher benötigt, erhöht aber auch den Arbeitsspeicherbedarf und möglicherweise die Startzeit. Für ARM X86- und X64 Computer, der Standardcommitwert 4 KB ist.

Geben Sie die Werte für `reserve` und `commit` dezimal oder in C-Notation an.

Eine weitere Möglichkeit zum Festlegen der Größe des Stapels wird mit der [STACKSIZE](../../build/reference/stacksize.md) -Anweisung in einer Moduldefinitionsdatei (.def). **STACKSIZE** überschreibt die (/ STACK) option, wenn beide angegeben werden. Sie können die Größe des Stapels ändern, nach der Erstellung der .exe-Datei mithilfe der [EDITBIN](../../build/reference/editbin-reference.md) Tool.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Linker** Ordner.

1. Wählen Sie die **System** Eigenschaftenseite.

1. Ändern Sie eine der folgenden Eigenschaften:

   - **Stapelcommitgröße**

   - **Stapelreservierungsgröße**

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Siehe die Eigenschaften <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackCommitSize%2A> und <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackReserveSize%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)