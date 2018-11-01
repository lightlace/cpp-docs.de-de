---
title: /GX (Ausnahmebehandlung aktivieren)
ms.date: 11/04/2016
f1_keywords:
- /gx
helpviewer_keywords:
- exception handling, enabling
- /GX compiler option [C++]
- -GX compiler option [C++]
- cl.exe compiler, exception handling
- enable exception handling compiler option [C++]
- GX compiler option [C++]
ms.assetid: 933b43ba-de77-4ff8-a48b-7074de90bc1c
ms.openlocfilehash: 3e820791b651a029f048423daacf50ddc8b74a1d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620622"
---
# <a name="gx-enable-exception-handling"></a>/GX (Ausnahmebehandlung aktivieren)

Veraltet. Aktiviert synchrone Ausnahmebehandlung, die mit der Annahme, die Funktionen, indem deklariert `extern "C"` nie eine Ausnahme auslösen.

## <a name="syntax"></a>Syntax

```
/GX
```

## <a name="remarks"></a>Hinweise

**/ GX** ist veraltet. Verwenden Sie die Entsprechung [/EHsc](../../build/reference/eh-exception-handling-model.md) option. Eine Liste der Ersetzte Compileroptionen, finden Sie unter den **veraltete und entfernte Compileroptionen** im Abschnitt [Compiler Options Listed by Category](../../build/reference/compiler-options-listed-by-category.md).

In der Standardeinstellung **/EHsc**, entspricht der **/GX**, ist gültig, wenn Sie mit der Entwicklungsumgebung von Visual Studio kompilieren. Wenn Sie die Befehlszeilentools verwenden, wird keine Ausnahmebehandlung angegeben. Dies ist die Entsprechung der **/GX-**.

Weitere Informationen finden Sie unter [C++-Ausnahmebehandlung](../../cpp/cpp-exception-handling.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie im Navigationsbereich **Konfigurationseigenschaften**, **C/C++-**, **Befehlszeile**.

1. Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)<br/>
[/EH (Ausnahmebehandlungsmodell)](../../build/reference/eh-exception-handling-model.md)