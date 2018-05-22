---
title: -fp (Festlegen des Gleitkommaverhaltens) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.floatingPointModel
- VC.Project.VCCLWCECompilerTool.FloatingPointExceptions
- /fp
- VC.Project.VCCLWCECompilerTool.floatingPointModel
- VC.Project.VCCLCompilerTool.FloatingPointExceptions
dev_langs:
- C++
helpviewer_keywords:
- -fp compiler option [C++]
- /fp compiler option [C++]
ms.assetid: 10469d6b-e68b-4268-8075-d073f4f5d57e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 520a6e2d675c55e47a0424ab93c6a76d521f2358
ms.sourcegitcommit: 5e932a0e110e80bc241e5f69e3a1a7504bfab1f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2018
---
# <a name="fp-specify-floating-point-behavior"></a>/fp (Festlegen des Gleitkommaverhaltens)

Gibt das Gleitkommaverhalten in einer Quellcodedatei an.

## <a name="syntax"></a>Syntax

> **/ fp:**[**präzise** | **außer**[**-**] | **schnelle** | **strenge**]

### <a name="arguments"></a>Argumente

#### <a name="precise"></a>Präzise

Der Standardwert von **/fp** ist **/fp: präzise**.

Die **/fp: präzise** Flag verbessert die Konsistenz von gleitkommatests auf Gleichheit und Ungleichheit durch Deaktivierung von Optimierungen, die die Genauigkeit von gleitkommaberechnungen ändern können. (Für die strikte ANSI-Konformität ist eine bestimmte Genauigkeit erforderlich.) Standardmäßig in Code für X86 80-Bit-Architekturen, dass verwenden X87 Coprozessor Anweisungen, die der Compiler verwendet den Coprozessor der Register, um die Zwischenergebnisse von gleitkommaberechnungen zu speichern. Damit wird die Geschwindigkeit des Programms erhöht und die Größe verringert. Da allerdings die Berechnung mit Gleitkomma-Datentypen durchgeführt wird, die im Speicher mit weniger als 80 Bit dargestellt werden, kann die Verwendung der zusätzlichen Bits für die Genauigkeit (80 Bit minus der Anzahl von Bits in einem kleineren Gleitkommatyp) in längeren Berechnungen jedoch zu inkonsistenten Ergebnissen führen.

Mit **/fp: präzise** auf X86 Prozessoren, führt der Compiler bei Variablen vom Typ Rundung `float` die entsprechende Genauigkeit für Zuweisungen und Typumwandlungen und wenn Parameter an eine Funktion übergeben werden. Durch diese Rundung wird gewährleistet, dass die Daten keinen höheren Stellenwert als die Kapazität ihres Typs beibehalten. Kompilieren eines Programms mit **/fp: präzise** kann langsamer und größer als 1 ohne kompiliert **/fp: präzise**. **/ fp: präzise** systeminterne Funktionen deaktiviert; der standard-Laufzeitbibliothek Routinen dienen. Weitere Informationen finden Sie unter [/Oi (Systeminterne Funktionen erstellen)](../../build/reference/oi-generate-intrinsic-functions.md).

Das folgende Gleitkommaverhalten aktiviert **/fp: präzise**:

- Kontraktionen, das bedeutet das Ersetzen mehrerer Operationen durch Verwendung einer zusammengesetzten Operation mit einer einzigen Rundung am Ende.

- Unzulässig sind Ausdruckoptimierungen, die für spezielle Werte (NaN, +unendlich, –unendlich, + 0, – 0) ungültig sind. Das X-"X" Optimierungen > 0 = X * 0 = > 0, x-0 = > X, X + 0 = > x und 0 X = > - X sind aus verschiedenen Gründen ungültig. (Siehe IEEE 754 und C99-Standard.)

- Der Compiler verarbeitet Vergleichsoperationen bezüglich NaN ordnungsgemäß. Z. B. X! = X ergibt **"true"** Wenn `x` gleich NaN ist und geordnete Vergleiche mit NaN eine Ausnahme ausgelöst.

- Die Auswertung des Ausdrucks folgt C99 FLT_EVAL_METHOD=2 mit folgender Ausnahme: Beim Programmieren für x86-Prozessoren wird die Genauigkeit "long double" angewendet, da die FPU auf eine Genauigkeit von 53 Bit festgelegt ist.

- Die Multiplikation mit exakt 1,0 wird so umgewandelt, dass nur der andere Faktor verwendet wird. X * y\*1.0 wird transformiert in x\*y. Auf ähnliche Weise X\*1.0\*y wird transformiert in x\*y.

- Die Division durch exakt 1,0 wird so transformiert, dass nur der Dividend verwendet wird. X * Y/1.0 wird transformiert in x\*y. Auf ähnliche Weise X / 1.0\*y wird transformiert in x\*y.

Mit **/fp: präzise** Wenn [Fenv_access](../../preprocessor/fenv-access.md) wird auf deaktiviert Optimierungen, wie z. B. den Zeitpunkt der Kompilierung auswertungen von Gleitkomma-Ausdrücke. Angenommen, Sie verwenden [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) so ändern Sie den Rundungsmodus und der Compiler eine Gleitkommazahl Berechnung ausführt, angegebene Rundungsmodus ist nicht aktiviert, es sei denn, `fenv_access`auf ON festgelegt ist.

**/ fp: präzise** ersetzt die **op** -Compileroption.

#### <a name="fast"></a>Schnelle

Die **/fp: fast** Option erstellt den schnellsten Code in den meisten Fällen durch Lockerung der Regeln für das Optimieren von Gleitkommaoperationen. Dadurch kann der Compiler die Geschwindigkeit von Gleitkommacode optimieren, was allerdings zulasten seiner Genauigkeit und Richtigkeit geht. Wenn **/fp: fast** angegeben wird, der Compiler, typenumwandlungen oder Funktionsaufrufe und zwischenausdrücke möglicherweise nicht ausgeführt werden, möglicherweise nicht ordnungsgemäß am zuweisungsanweisungen runden. Der Compiler ordnet möglicherweise Operationen neu an oder führt ungeachtet der Auswirkung auf Ergebnisse mit endlicher Genauigkeit algebraische Transformationen aus, z. B. durch assoziative und distributive Regeln. Der Compiler kann die Genauigkeit von Operationen und Operanden in die einfache Genauigkeit ändern, anstatt die C++-Typerweiterungsregeln zu befolgen. Floating-point-spezifischen Kontraktion Optimierungen sind immer aktiviert ([Fp_contract](../../preprocessor/fp-contract.md) auf ON festgelegt ist). Gleitkommaausnahmen und FPU Umgebung Zugriff deaktiviert (**/fp: außer-** impliziert und [Fenv_access](../../preprocessor/fenv-access.md) auf OFF festgelegt ist).

**/ fp: fast** kann nicht verwendet werden, mit **/fp: strict** oder **/fp: präzise**. Die letzte in der Befehlszeile angegebene Option wird verwendet. Angeben von sowohl **/fp: fast** und **/fp: außer** generiert einen Compilerfehler.

Angeben von [/Za, / Ze (Spracherweiterungen deaktivieren)](../../build/reference/za-ze-disable-language-extensions.md) (ANSI-Kompatibilität) und **/fp: fast** führen möglicherweise zu unerwartetem Verhalten. Zum Beispiel werden Gleitkommaoperationen mit einfacher Genauigkeit möglicherweise nicht auf einfache Genauigkeit gerundet.

#### <a name="except"></a>Ausnahme:

Die **/fp: außer** Option ermöglicht eine zuverlässige Gleitkommaausnahme-Modell. Ausnahmen werden sofort ausgelöst, wenn sie auftreten. Diese Option ist standardmäßig deaktiviert. Durch Hinzufügen eines Minuszeichens zur Option (**/fp: außer-**) explizit deaktiviert.

#### <a name="strict"></a>strict

Die **/fp: strict** Option ermöglicht das strengste Gleitkommamodell. **/ fp: strict** bewirkt, dass [Fp_contract](../../preprocessor/fp-contract.md) auf OFF festgelegt werden und [Fenv_access](../../preprocessor/fenv-access.md) auf ON festgelegt sein. **/ fp: außer** wird dies angegeben und kann deaktiviert werden, indem Sie ausdrücklich angeben **/fp: außer-**. Bei Verwendung mit **/fp: außer-**, **/fp: strict** strikte Gleitkommasemantik jedoch ohne Beachtung von Ausnahmeereignissen.

## <a name="remarks"></a>Hinweise

Mehrere **/fp** -Optionen können in der gleichen Kompilierung angegeben werden.

Um Gleitkommaverhalten von Funktion zu steuern, finden Sie unter der [Float_control](../../preprocessor/float-control.md) Pragma. Dies überschreibt die **/fp** compilereinstellung. Als gutes Entwicklungsverfahren wird empfohlen, das lokale Gleitkommaverhalten zu speichern und wiederherzustellen:

```cpp
#pragma float_control(precise, on, push)
// Code that uses /fp:precise mode
#pragma float_control(pop)
```

Die meisten der gleitkommaoptimierungen betreffen **/fp: strict**, **/fp: außer** (sowie zugehörige Pragmas) und die `fp_contract` Pragma sind abhängig vom Computer. **/ fp: strict** und **/fp: außer** sind nicht kompatibel mit **"/ CLR"**.

**/ fp: präzise** sollte den meisten gleitkommaanforderungen einer Anwendung beheben. Sie können **/fp: außer** und **/fp: strict**, stehen jedoch ggf. einige Abnahme der Leistung. Wenn die Leistung am wichtigsten ist, erwägen, ob **/fp: fast**.

**/ fp: strict**, **/fp: fast**, und **/fp: präzise** Genauigkeit (Korrektheit) Modi sind. Es kann jeweils nur ein Modus aktiv sein. Wenn beide **/fp: strict** und **/fp: präzise** angegeben sind, wird der Compiler verwendet den Typ, der es zuletzt verarbeitet. Beide **/fp: strict** und **/fp: fast** kann nicht angegeben werden.

Weitere Informationen finden Sie unter [Microsoft Visual C++ Floating Optimierung](floating-point-optimization.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Erweitern Sie die **Konfigurationseigenschaften** > **C/C++-** > **Codegenerierung** Eigenschaftenseite.

1. Ändern der **Gleitkommamodell** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.floatingPointModel%2A>.

## <a name="see-also"></a>Siehe auch

- [Compileroptionen](compiler-options.md)
- [Festlegen von Compileroptionen](setting-compiler-options.md)
- [Microsoft Visual C++ Floating Point-Optimierung](floating-point-optimization.md)