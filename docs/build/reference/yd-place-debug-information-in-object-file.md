---
title: /Yd (Debuginformationen in Objektdatei ablegen)
ms.date: 11/04/2016
f1_keywords:
- /yd
helpviewer_keywords:
- /Yd compiler option [C++]
- -Yd compiler option [C++]
- debugging [C++], debug information files
- Yd compiler option [C++]
ms.assetid: c5a699fe-65ce-461e-964c-7f5eb2a8320a
ms.openlocfilehash: eda3dd38449f89d9b8d767b460970d659f6c9dc9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50430016"
---
# <a name="yd-place-debug-information-in-object-file"></a>/Yd (Debuginformationen in Objektdatei ablegen)

Überprüfen Sie alle Funktionen vollständige Debuginformationen in allen Objektdateien erstellt aus einer vorkompilierten Headerdatei (.pch)-Datei bei der Verwendung mit der ["/ Yc"](../../build/reference/yc-create-precompiled-header-file.md) und ["/ Z7"](../../build/reference/z7-zi-zi-debug-information-format.md) Optionen. Veraltet.

## <a name="syntax"></a>Syntax

```
/Yd
```

## <a name="remarks"></a>Hinweise

**/ Yd ablegen** ist veraltet. Visual C++ unterstützt jetzt mehrere Objekte, die in eine einzelne PDB-Datei schreiben, verwenden Sie **"/ Zi"** stattdessen. Eine Liste der Ersetzte Compileroptionen, finden Sie unter **veraltete und entfernte Compileroptionen** in [Compiler Options Listed by Category](../../build/reference/compiler-options-listed-by-category.md).

Verwenden, es sei denn, Sie eine Bibliothek mit debugging-Informationen zu verteilen müssen, die ["/ Zi"](../../build/reference/z7-zi-zi-debug-information-format.md) Option statt **"/ Z7"** und **/Yd ablegen**.

Speichern vollständige Debuginformationen in jeder OBJ-Datei ist nur erforderlich, um Bibliotheken zu verteilen, die Debuginformationen enthalten. Sie verlangsamt die Kompilierung und viel Speicherplatz benötigt. Wenn **"/ Yc"** und **"/ Z7"** werden verwendet, ohne **/Yd ablegen**, speichert der Compiler allgemeine Debuginformationen in der ersten OBJ-Datei, die aus der PCH-Datei erstellt. Der Compiler fügt diese Informationen nicht in OBJ-Dateien, die anschließend von PCH-Datei erstellt ein; Es fügt Querverweise auf die Informationen ein. Unabhängig davon, wie viele OBJ-Dateien die PCH-Datei verwenden enthält nur eine OBJ-Datei die allgemeine Debuginformationen.

Obwohl diese standardmäßige Verhalten führt zu Builds schneller und verringert den Bedarf der Speicherplatz, ist es nicht erwünscht, wenn eine kleine Änderung erfordert die Neuerstellung der OBJ-Datei, die die allgemeine Debuginformationen enthält. In diesem Fall muss der Compiler alle OBJ-Dateien, die mit Querverweisen, in der ursprünglichen OBJ-Datei neu erstellen. Wenn eine allgemeine PCH-Datei, die von verschiedenen Projekten verwendet wird, ist auf Querverweise in einer einzelnen OBJ-Datei auch schwierig.

Weitere Informationen zu vorkompilierten Headern finden Sie unter:

- [/Y (Vorkompilierte Header)](../../build/reference/y-precompiled-headers.md)

- [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="examples"></a>Beispiele

Angenommen, Sie haben zwei Basisdateien F.cpp und g.cpp zu, und jede enthält diese **#include** Anweisungen:

```
#include "windows.h"
#include "etc.h"
```

Der folgende Befehl erstellt den vorkompilierten Header ETC.pch und die Objektdatei F.obj:

```
CL /YcETC.H /Z7 F.CPP
```

Die Objektdatei F.obj enthält Typ und Symbolinformationen für WINDOWS.h und etc.h ein (und andere Headerdateien, die sie enthalten). Jetzt können Sie den vorkompilierten Header ETC.pch, um die Quelldatei g.cpp zu kompilieren:

```
CL /YuETC.H /Z7 G.CPP
```

Die Objektdatei ein enthält keine Debuginformationen für den vorkompilierten Header jedoch einfach verweist auf diese Informationen in der Datei F.obj. Beachten Sie, dass Sie eine Verknüpfung mit der Datei F.obj herstellen müssen.

Wenn der vorkompilierte Header nicht mit kompiliert wurde **"/ Z7"**, noch können Sie sie in späteren Kompilierungen zusammen mit **"/ Z7"**. Allerdings wird die Debuginformationen in der aktuellen Objektdatei platziert, und lokale Symbole für Funktionen und in der vorkompilierten Headerdatei definierten Typen sind nicht verfügbar ist, an den Debugger.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)