---
title: -Og (globale Optimierungen) | Microsoft Docs
ms.custom: ''
ms.date: 09/22/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.GlobalOptimizations
- /og
dev_langs:
- C++
helpviewer_keywords:
- -Og compiler option [C++]
- global optimizations compiler option [C++]
- automatic register allocation
- /Og compiler option [C++]
- loop structures, optimizing
- common subexpression elimination
- Og compiler option [C++]
ms.assetid: d10630cc-b9cf-4e97-bde3-8d7ee79e9435
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03ef87f31e478bfbc8691b7e678186dd1a0621e5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="og-global-optimizations"></a>/Og (Globale Optimierungen)

Veraltet. Enthält lokale und globale Optimierungen automatische Registrierung Zuordnung und Optimierung einer Schleife. Es wird empfohlen, entweder [/O1 (Größe minimieren)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) oder [/O2 (Geschwindigkeit maximieren)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) stattdessen.

## <a name="syntax"></a>Syntax

> /Og

## <a name="remarks"></a>Hinweise

**/ Og** ist veraltet. Diese Optimierungen sind jetzt in der Regel standardmäßig aktiviert. Weitere Informationen zur Optimierung finden Sie unter [/O1, / O2 (Größe minimieren, Geschwindigkeit maximieren)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) oder [/Ox (ermöglichen die meisten Geschwindigkeit Optimierungen)](../../build/reference/ox-full-optimization.md).

Die folgenden Optimierungen sind verfügbar unter **/Og**:

- Lokale und globale allgemeine teilausdruckbeseitigung

     Diese Optimierung wird der Wert eines gemeinsamen Teilausdrucks einmal berechnet. Im folgenden Beispiel wenn die Werte der `b` und `c` nicht zwischen drei Ausdrücke ändern, der Compiler kann die Berechnung der zuweisen `b + c` in eine temporäre Variable, und Ersetzen Sie die Variable für `b + c`:

    ```C
    a = b + c;
    d = b + c;
    e = b + c;
    ```

     Bei der Optimierung lokaler gemeinsamer Teilausdruck überprüft der Compiler kurze Abschnitte des Codes für gemeinsame Teilausdrücke. Für globale Optimierung gemeinsamer Teilausdruck sucht der Compiler die gesamte Funktionen für gemeinsame Teilausdrücke.

- Automatische registerreservierung

     Diese Optimierung ermöglicht es dem Compiler zu speichern, die häufig verwendete Variablen und Teilausdrücke in Registern; die `register` Schlüsselwort wird ignoriert.

- Loop-Optimierung

     Diese Optimierung entfernt der invariante Teilausdrücke aus dem Text einer Schleife. Eine optimale Schleife enthält nur Ausdrücke, deren Werte sich bei der Ausführung der Schleife zu ändern. Im folgenden Beispiel wird der Ausdruck `x + y` ändert sich nicht im Schleifenkörper:

    ```C
    i = -100;
    while( i < 0 ) {
        i += x + y;
    }
    ```

     Nach der Optimierung `x + y` einmal anstatt jedes Mal die Schleife berechnet wird:

    ```C
    i = -100;
    t = x + y;
    while( i < 0 ) {
        i += t;
    }
    ```

     Schleife Optimierung ist viel effizienter, wenn der Compiler kein Aliasing davon, die Sie festlegen ausgehen kann, mit [__restrict](../../cpp/extension-restrict.md), [Noalias](../../cpp/noalias.md), oder [beschränken](../../cpp/restrict.md).

    > [!NOTE]
    > Sie aktivieren oder deaktivieren Sie die globale Optimierung für einen Basis Funktion, indem Sie mithilfe der `optimize` Pragma zusammen mit den `g` Option.

 Weitere Informationen finden Sie unter [/Oi (systeminterne Funktionen erstellen)](../../build/reference/oi-generate-intrinsic-functions.md) und [/Ox (ermöglichen die meisten Geschwindigkeit Optimierungen)](../../build/reference/ox-full-optimization.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Compileroption "in der **Zusatzoptionen** Feld.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[/O-Optionen (Code optimieren)](../../build/reference/o-options-optimize-code.md)

[Compileroptionen](../../build/reference/compiler-options.md)

[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)