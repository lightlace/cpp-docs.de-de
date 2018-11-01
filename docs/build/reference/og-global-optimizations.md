---
title: /Og (Globale Optimierungen)
ms.date: 09/22/2017
f1_keywords:
- VC.Project.VCCLCompilerTool.GlobalOptimizations
- /og
helpviewer_keywords:
- -Og compiler option [C++]
- global optimizations compiler option [C++]
- automatic register allocation
- /Og compiler option [C++]
- loop structures, optimizing
- common subexpression elimination
- Og compiler option [C++]
ms.assetid: d10630cc-b9cf-4e97-bde3-8d7ee79e9435
ms.openlocfilehash: d6913be5bc02755730ffb6205e9f34811c9a5dbb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431940"
---
# <a name="og-global-optimizations"></a>/Og (Globale Optimierungen)

Veraltet. Enthält lokale und globale Optimierungen, automatische Registrierung Zuordnung und Optimierung einer Schleife. Es wird empfohlen, entweder [/O1 (Größe minimieren)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) oder ["/ O2" (Geschwindigkeit maximieren)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) stattdessen.

## <a name="syntax"></a>Syntax

> /Og

## <a name="remarks"></a>Hinweise

**"/ Og"** ist veraltet. Diese Optimierungen sind jetzt in der Regel standardmäßig aktiviert. Weitere Informationen zur Optimierung finden Sie unter [/O1, / O2 (Größe minimieren, Geschwindigkeit maximieren)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) oder [/Ox (ermöglichen die meisten Geschwindigkeitsoptimierungen)](../../build/reference/ox-full-optimization.md).

Die folgenden Optimierungen sind verfügbar unter **"/ Og"**:

- Lokale und globale allgemeine teilausdruckbeseitigung

   In dieser Optimierung wird der Wert eines gemeinsamen Teilausdrucks einmal berechnet. Im folgenden Beispiel wenn die Werte der `b` und `c` wirken sich nicht zwischen den drei Ausdrücken, die der Compiler kann zuweisen, der Berechnung der `b + c` in eine temporäre Variable, und Ersetzen Sie die Variable für `b + c`:

    ```C
    a = b + c;
    d = b + c;
    e = b + c;
    ```

   Bei der Optimierung lokalen gemeinsame Teilausdrücke überprüft der Compiler kurze Abschnitte des Codes für gemeinsamen Teilausdrücken. Für globale Optimierung für allgemeine Teilausdruck sucht der Compiler die gesamte Funktionen für die gemeinsame Teilausdrücke.

- Automatische registerreservierung

   Diese Optimierung ermöglicht dem Compiler, häufig verwendete Variablen und Teilausdrücke in Registern; die `register` Schlüsselwort wird ignoriert.

- Optimierung der Schleife

   Diese Optimierung entfernt invariante Teilausdrücke aus dem Text einer Schleife. Eine optimale Schleife enthält nur Ausdrücke, die sich bei der Ausführung der Schleife, deren Werte zu ändern. Im folgenden Beispiel ist der Ausdruck `x + y` ändert sich nicht in der Schleife:

    ```C
    i = -100;
    while( i < 0 ) {
        i += x + y;
    }
    ```

   Nach der Optimierung `x + y` wird berechnet, einmal statt bei jeder Ausführung die Schleife ausgeführt wird:

    ```C
    i = -100;
    t = x + y;
    while( i < 0 ) {
        i += t;
    }
    ```

   Optimierung der Schleife ist sehr viel effektiver, wenn der Compiler keine Verwendung von Aliasen, davon, die Sie festlegen ausgehen kann, mit ["__restrict"](../../cpp/extension-restrict.md), [Noalias](../../cpp/noalias.md), oder [einschränken](../../cpp/restrict.md).

   > [!NOTE]
   > Können Sie aktivieren oder deaktivieren Sie globale Optimierung für eine Funktion-von-Funktion mithilfe der `optimize` Pragma zusammen mit den `g` Option.

Weitere Informationen finden Sie unter [/Oi (systeminterne Funktionen erstellen)](../../build/reference/oi-generate-intrinsic-functions.md) und [/Ox (ermöglichen die meisten Geschwindigkeitsoptimierungen)](../../build/reference/ox-full-optimization.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Compileroption in der **zusätzliche Optionen** Feld.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[/O-Optionen (Code optimieren)](../../build/reference/o-options-optimize-code.md)

[Compileroptionen](../../build/reference/compiler-options.md)

[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)