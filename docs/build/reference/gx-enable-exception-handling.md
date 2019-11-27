---
title: /GX (Ausnahmebehandlung aktivieren)
ms.date: 11/19/2019
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
ms.openlocfilehash: 171ff0d0dfb1dec41bae5f6be63c941802c402a4
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245089"
---
# <a name="gx-enable-exception-handling"></a>/GX (Ausnahmebehandlung aktivieren)

Veraltet. Aktiviert die synchrone Ausnahmebehandlung mithilfe der Annahme, dass Funktionen, die mit `extern "C"` deklariert werden, nie eine Ausnahme auslösen.

## <a name="syntax"></a>Syntax

```
/GX
```

## <a name="remarks"></a>Hinweise

**/GX** ist veraltet. Verwenden Sie stattdessen die entsprechende [/EHsc](eh-exception-handling-model.md) -Option. Eine Liste der veralteten Compileroptionen finden Sie im Abschnitt " **veraltete und entfernte Compileroptionen** " unter [Compileroptionen nach Kategorie aufgelistet](compiler-options-listed-by-category.md).

Standardmäßig ist **/EHsc**, das Äquivalent von **/GX**, beim Kompilieren mithilfe der Visual Studio-Entwicklungsumgebung wirksam. Wenn Sie die Befehlszeilen Tools verwenden, wird keine Ausnahmebehandlung angegeben. Dies entspricht **/GX-** .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Wählen Sie im Navigationsbereich **Konfigurations Eigenschaften**, **CC++/** , **Befehlszeile**aus.

1. Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)<br/>
[/EH (Ausnahmebehandlungsmodell)](eh-exception-handling-model.md)
