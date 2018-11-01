---
title: /fp (Festlegen des Gleitkommaverhaltens)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.floatingPointModel
- VC.Project.VCCLWCECompilerTool.FloatingPointExceptions
- /fp
- VC.Project.VCCLWCECompilerTool.floatingPointModel
- VC.Project.VCCLCompilerTool.FloatingPointExceptions
helpviewer_keywords:
- -fp compiler option [C++]
- /fp compiler option [C++]
ms.assetid: 10469d6b-e68b-4268-8075-d073f4f5d57e
ms.openlocfilehash: 8b948edba3244eb22089b2ef5b4c8131736e1fb3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452571"
---
# <a name="fp-specify-floating-point-behavior"></a>/fp (Festlegen des Gleitkommaverhaltens)

Gibt das Gleitkommaverhalten in einer Quellcodedatei an.

## <a name="syntax"></a>Syntax

> **/ fp:**[**präzise** | **außer**[**-**] | **schnell** | **strict**]

### <a name="arguments"></a>Argumente

#### <a name="precise"></a>Präzise

Der Standardwert von **/fp** ist **/fp: präzise**.

Die **/fp: präzise** Flag verbessert die Konsistenz von gleitkommatests auf Gleichheit und Ungleichheit durch Deaktivierung von Optimierungen, die die Genauigkeit von gleitkommaberechnungen ändern können. (Für die strikte ANSI-Konformität ist eine bestimmte Genauigkeit erforderlich.) In der Standardeinstellung im Code für X86 80-Bit-Architekturen, X87 Coprozessor gehen, der Compiler verwendet den Coprozessor des registriert, um die Zwischenergebnisse von gleitkommaberechnungen zu speichern. Damit wird die Geschwindigkeit des Programms erhöht und die Größe verringert. Da allerdings die Berechnung mit Gleitkomma-Datentypen durchgeführt wird, die im Speicher mit weniger als 80 Bit dargestellt werden, kann die Verwendung der zusätzlichen Bits für die Genauigkeit (80 Bit minus der Anzahl von Bits in einem kleineren Gleitkommatyp) in längeren Berechnungen jedoch zu inkonsistenten Ergebnissen führen.

Mit **/fp: präzise** auf X86 Prozessoren kann der Compiler führt eine Rundung auf Variablen vom Typ `float` die entsprechende Genauigkeit für Zuweisungen und Typumwandlungen, und wenn Parameter an eine Funktion übergeben werden. Durch diese Rundung wird gewährleistet, dass die Daten keinen höheren Stellenwert als die Kapazität ihres Typs beibehalten. Kompilieren eines Programms mit **/fp: präzise** kann langsamer und größer als 1 ohne kompiliert sein **/fp: präzise**. **/ fp: präzise** systeminterne Funktionen deaktiviert; der standard-Laufzeitbibliothek Routinen dienen. Weitere Informationen finden Sie unter [/Oi (Systeminterne Funktionen erstellen)](../../build/reference/oi-generate-intrinsic-functions.md).

Das folgende Gleitkommaverhalten aktiviert ist, mit **/fp: präzise**:

- Kontraktionen, das bedeutet das Ersetzen mehrerer Operationen durch Verwendung einer zusammengesetzten Operation mit einer einzigen Rundung am Ende.

- Unzulässig sind Ausdruckoptimierungen, die für spezielle Werte (NaN, +unendlich, –unendlich, + 0, – 0) ungültig sind. Die X-X-Optimierungen > 0 = X * 0 = > 0, x-0 = > X, X + 0 = > x und 0: X = > - X sind aus verschiedenen Gründen ungültig. (Siehe IEEE 754 und C99-Standard.)

- Der Compiler verarbeitet Vergleichsoperationen bezüglich NaN ordnungsgemäß. Z. B. X! = X ergibt **"true"** Wenn `x` gleich NaN ist und geordnete Vergleiche mit NaN eine Ausnahme ausgelöst.

- Die Auswertung des Ausdrucks folgt C99 FLT_EVAL_METHOD=2 mit folgender Ausnahme: Beim Programmieren für x86-Prozessoren wird die Genauigkeit "long double" angewendet, da die FPU auf eine Genauigkeit von 53 Bit festgelegt ist.

- Die Multiplikation mit exakt 1,0 wird so umgewandelt, dass nur der andere Faktor verwendet wird. X * y\*1.0 ist in x transformiert\*y. Auf ähnliche Weise X\*1.0\*y in x transformiert\*y.

- Die Division durch exakt 1,0 wird so transformiert, dass nur der Dividend verwendet wird. X * Y/1.0 in x transformiert\*y. Auf ähnliche Weise X / 1.0\*y in x transformiert\*y.

Mithilfe von **/fp: präzise** beim [Fenv_access](../../preprocessor/fenv-access.md) deaktiviert Optimierungen, wie z. B. während der Kompilierung auswertungen von Gleitkommaausdrücken ist. Wenn Sie verwenden, z. B. [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) so ändern Sie den Rundungsmodus des Gleitkommas und der Compiler eine gleitkommaberechnung durchführt, die der angegebenen Rundungsmodus ist nicht aktiviert, es sei denn, `fenv_access`auf ON festgelegt ist.

**/ fp: präzise** ersetzt die **die/op** -Compileroption.

#### <a name="fast"></a>Schnelle

Die **fast** Option erstellt den schnellsten Code in den meisten Fällen durch Lockerung der Regeln zum Optimieren von Gleitkommaoperationen. Dadurch kann der Compiler die Geschwindigkeit von Gleitkommacode optimieren, was allerdings zulasten seiner Genauigkeit und Richtigkeit geht. Wenn **fast** angegeben wird, der Compiler möglicherweise nicht ordnungsgemäß an zuweisungsanweisungen gerundet, typenumwandlungen oder Funktionsaufrufe und zwischenausdrücke möglicherweise nicht ausgeführt. Der Compiler ordnet möglicherweise Operationen neu an oder führt ungeachtet der Auswirkung auf Ergebnisse mit endlicher Genauigkeit algebraische Transformationen aus, z. B. durch assoziative und distributive Regeln. Der Compiler kann die Genauigkeit von Operationen und Operanden in die einfache Genauigkeit ändern, anstatt die C++-Typerweiterungsregeln zu befolgen. Gleitkomma-point-spezifischen Widerspruch Optimierungen sind immer aktiviert ([Fp_contract](../../preprocessor/fp-contract.md) auf ON festgelegt ist). Gleitkommaausnahmen und Zugriff auf die FPU-Umgebung sind deaktiviert (**/fp: mit Ausnahme von-** wird impliziert und [Fenv_access](../../preprocessor/fenv-access.md) auf OFF festgelegt ist).

**fast** kann nicht verwendet werden, mit **/fp: strict** oder **/fp: präzise**. Die letzte in der Befehlszeile angegebene Option wird verwendet. Festlegung von **fast** und **/fp: mit Ausnahme von** wird ein Compilerfehler generiert.

Angeben von [/Za, / Ze (Spracherweiterungen deaktivieren)](../../build/reference/za-ze-disable-language-extensions.md) (ANSI-Kompatibilität) und **fast** kann unerwartetes Verhalten verursachen. Zum Beispiel werden Gleitkommaoperationen mit einfacher Genauigkeit möglicherweise nicht auf einfache Genauigkeit gerundet.

#### <a name="except"></a>Mit der Ausnahme

Die **/fp: mit Ausnahme von** Option ermöglicht eine zuverlässige Gleitkommaausnahme-Modell. Ausnahmen werden sofort ausgelöst, wenn sie auftreten. Diese Option ist standardmäßig deaktiviert. Durch Hinzufügen eines Minuszeichens zur Option (**/fp: mit Ausnahme von-**) explizit deaktiviert.

#### <a name="strict"></a>strict

Die **/fp: strict** Option ermöglicht das strengste Gleitkommamodell. **/ fp: strict** bewirkt, dass [Fp_contract](../../preprocessor/fp-contract.md) auf OFF und [Fenv_access](../../preprocessor/fenv-access.md) auf ON festgelegt wird. **/ fp: mit Ausnahme von** wird impliziert und kann deaktiviert werden, indem Sie explizit angeben **/fp: mit Ausnahme von-**. Bei Verwendung mit **/fp: mit Ausnahme von-**, **/fp: strict** strikte Gleitkommasemantik erzwungen, aber ohne Beachtung von Ausnahmeereignissen.

## <a name="remarks"></a>Hinweise

Mehrere **/fp** -Optionen können in der gleichen Kompilierung angegeben werden.

Informationen zum Gleitkommaverhalten von Funktion steuern die [Float_control](../../preprocessor/float-control.md) Pragma. Dies überschreibt die **/fp** compilereinstellung. Als gutes Entwicklungsverfahren wird empfohlen, das lokale Gleitkommaverhalten zu speichern und wiederherzustellen:

```cpp
#pragma float_control(precise, on, push)
// Code that uses /fp:precise mode
#pragma float_control(pop)
```

Die meisten der gleitkommaoptimierungen betreffen **/fp: strict**, **/fp: mit Ausnahme von** (sowie zugehörige Pragmas) und die `fp_contract` Pragma sind abhängig vom Computer. **/ fp: strict** und **/fp: mit Ausnahme von** sind nicht kompatibel mit **"/ CLR"**.

**/ fp: präzise** sollten die meisten Gleitkommazahlen Anforderungen einer Anwendung zu beheben. Sie können **/fp: mit Ausnahme von** und **/fp: strict**, kann jedoch zu eine Verringerung der Leistung. Wenn die Leistung am wichtigsten ist, überlegen, ob **fast**.

**/ fp: strict**, **fast**, und **/fp: präzise** sind Modi für Genauigkeit (Korrektheit). Es kann jeweils nur ein Modus aktiv sein. Wenn beide **/fp: strict** und **/fp: präzise** angegeben sind, wird der Compiler verwendet die zuletzt verarbeitet. Beide **/fp: strict** und **fast** kann nicht angegeben werden.

Weitere Informationen finden Sie unter [Microsoft Visual C++ Floating-Point Optimization](floating-point-optimization.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Erweitern Sie die **Konfigurationseigenschaften** > **C/C++-** > **Codegenerierung** Eigenschaftenseite.

1. Ändern der **Gleitkommamodell** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.floatingPointModel%2A>.

## <a name="see-also"></a>Siehe auch

- [Compileroptionen](compiler-options.md)
- [Festlegen von Compileroptionen](setting-compiler-options.md)
- [Microsoft Visual C++-Gleitkommaoptimierung](floating-point-optimization.md)