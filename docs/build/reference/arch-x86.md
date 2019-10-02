---
title: /arch (x86)
ms.date: 10/01/2019
ms.assetid: 9dd5a75d-06e4-4674-aade-33228486078d
ms.openlocfilehash: b1e5501f6edd3eb016395380ff476250c0c388b9
ms.sourcegitcommit: 4517932a67bbf2db16cfb122d3bef57a43696242
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2019
ms.locfileid: "71816316"
---
# <a name="arch-x86"></a>/arch (x86)

Gibt die Architektur für die Codegenerierung auf x86 an. Siehe auch [/arch (x64)](arch-x64.md) und [/arch (Arm)](arch-arm.md).

## <a name="syntax"></a>Syntax

```
/arch:[IA32|SSE|SSE2|AVX|AVX2|AVX512]
```

## <a name="arguments"></a>Argumente

**/Arch: ia32**<br/>
Gibt keine erweiterten Anweisungen an, und gibt außerdem x87 für Gleitkommaberechnungen an.

**/Arch: SSE**<br/>
Aktiviert die Verwendung von SSE-Anweisungen.

**/arch:SSE2**<br/>
Aktiviert die Verwendung von SSE2-Anweisungen. Dies ist die Standard Anweisung auf x86-Plattformen, wenn keine **/arch** -Option angegeben wird.

**/Arch: AVX**<br/>
Aktiviert die Verwendung von Intel Advanced Vector Extensions-Anweisungen.

**/arch:AVX2**<br/>
Aktiviert die Verwendung von Intel Advanced Vector Extensions 2-Anweisungen.

**/Arch: AVX512**<br/>
Aktiviert die Verwendung von Intel Advanced Vector Extensions 512-Anweisungen.

## <a name="remarks"></a>Hinweise

Die **/arch** -Option aktiviert oder deaktiviert die Verwendung bestimmter Anweisungs Satz Erweiterungen, insbesondere bei der Vektor Berechnung, die in Prozessoren von Intel und AMD verfügbar ist. Im allgemeinen unterstützen mehr vor kurzem eingeführte Prozessoren möglicherweise zusätzliche Erweiterungen, die von älteren Prozessoren unterstützt werden. Sie sollten sich jedoch die Dokumentation für einen bestimmten Prozessor ansehen oder die Unterstützung der Anweisungs Satz Erweiterung mithilfe von __ überprüfen. [ CPUID](../../intrinsics/cpuid-cpuidex.md) vor dem Ausführen von Code mithilfe einer Anweisungs Satz Erweiterung.

**/arch** wirkt sich nur auf die Codegenerierung für Native Funktionen aus. Wenn Sie [/CLR](clr-common-language-runtime-compilation.md) für die Kompilierung verwenden, wirkt sich **/arch** nicht auf die Codegenerierung für verwaltete Funktionen aus.

Die **/arch** -Optionen verweisen auf Anweisungs Satz Erweiterungen mit den folgenden Merkmalen:

- **Ia32** ist der ältere 32-Bit-x86-Anweisungs Satz ohne Vektor Vorgänge und die Verwendung von x87 für Gleit Komma Berechnungen.

- **SSE** ermöglicht die Berechnung mit Vektoren mit bis zu vier Gleit Komma Werten mit einfacher Genauigkeit. Entsprechende skalare Gleit Komma Anweisungen wurden ebenfalls hinzugefügt.

- **SSE2** ermöglicht die Berechnung mit 128-Bit-Vektoren von Werten mit einfacher Genauigkeit, doppelter Genauigkeit und 1, 2, 4 oder 8 Byte ganzzahligen Werten. Skalare Anweisungen mit doppelter Genauigkeit wurden ebenfalls hinzugefügt.

- **AVX** hat eine Alternative Anweisungs Codierung für Vektor-und Gleit Komma-skalaranweisungen eingeführt, die Vektoren von 128 Bits oder 256 Bits zulässt und alle Vektor Ergebnisse auf die vollständige Vektor Größe erweitert. (Um die Legacy Kompatibilität zu gewährleisten, behalten die Vektor Anweisungen im SSE-Stil alle Bits über Bit 127.) Die meisten Gleit Komma Operationen werden auf 256 Bits erweitert.

- **AVX2** erweitert die meisten ganzzahligen Vorgänge auf 256-Bit-Vektoren und ermöglicht die Verwendung von "Multiplikations Anweisungen (FMA)"-Anweisungen.

- **AVX512** hat ein weiteres Anweisungs Codierungs Formular eingeführt, das 512-Bit-Vektoren sowie bestimmte andere optionale Features zulässt. Es wurden auch Anweisungen für weitere Vorgänge hinzugefügt.

Der Optimierer wählt, wann und wie Vektor Anweisungen verwendet werden, je nachdem, welche **/arch** angegeben ist. Skalare Gleit Komma Berechnungen werden mit SSE-oder AVX-Anweisungen ausgeführt, wenn Sie verfügbar sind. Einige Aufruf Konventionen geben an, dass Gleit Komma Argumente für den x87-Stapel übergeben werden. Daher kann der Code eine Mischung aus x87-und SSE/AVX-Anweisungen für Gleit Komma Berechnungen verwenden. Ganzzahlige Vektor Anweisungen können auch für einige 64-Bit-ganz Zahl Operationen verwendet werden, wenn diese verfügbar sind.

Zusätzlich zu den Vektor-und Gleit Komma-skalaranweisungen kann jede **/arch** -Option auch die Verwendung anderer nicht Vektor Anweisungen ermöglichen, die dieser Option zugeordnet sind. Ein Beispiel hierfür ist die cmovcc-Anweisungs Familie, die zuerst auf den Intel Pentium Pro-Prozessoren aufgetreten ist. Da SSE-Anweisungen mit dem nachfolgenden Intel Pentium III-Prozessor eingeführt wurden, können cmovcc-Anweisungen generiert werden, außer wenn **/arch: ia32** angegeben wird.

Gleit Komma Operationen werden normalerweise in x87-Code auf doppelte Genauigkeit (64 Bit) gerundet, Sie können jedoch `_controlfp` verwenden, um das FP-Steuerwort zu ändern, einschließlich der Festlegung des Genauigkeits Steuer Elements auf Erweiterte Genauigkeit (80 Bit) oder mit einfacher Genauigkeit (32 Bit). Weitere Informationen finden Sie unter [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md). SSE und AVX verfügen über separate Anweisungen mit einfacher Genauigkeit und doppelter Genauigkeit für jeden Vorgang, sodass es keine Entsprechung für SSE/AVX-Code gibt. Dadurch kann geändert werden, wie Ergebnisse gerundet werden, wenn das Ergebnis einer Gleit Komma Operation direkt in der weiteren Berechnung verwendet wird, anstatt es einer Benutzervariablen zuzuweisen. Nehmen wir einmal die folgende Situation:

```cpp
r = f1 * f2 + d;  // Different results are possible on SSE/SSE2.
```

Mit expliziter Zuweisung:

```cpp
t = f1 * f2;   // Do f1 * f2, round to the type of t.
r = t + d;     // This should produce the same overall result
               // whether x87 stack is used or SSE/SSE2 is used.
```

**/arch** und [/QIfist](qifist-suppress-ftol.md) können nicht für dieselbe kompiand verwendet werden. Die Option **/QIfist** ändert das Rundungs Verhalten der Gleit Komma Konvertierung in eine ganzzahlige Konvertierung. Das Standardverhalten besteht darin, den Wert TRUNCATE (Round to Zero) zu verwenden, während die **/QIfist** -Option die Verwendung des Rundungs Modus der Gleit Komma Umgebung angibt. Da dadurch das Verhalten aller Gleit Komma-zu-ganzzahligen Konvertierungen geändert wird, ist dieses Flag als veraltet markiert. Beim Kompilieren für SSE oder AVX können Sie einen Gleit Komma Wert auf eine ganze Zahl umrunden, indem Sie den Rundungs Modus für die Gleit Komma Umgebung mithilfe einer systeminternen Funktions Sequenz verwenden:

```cpp
int convert_float_to_int(float x) {
    return _mm_cvtss_si32(_mm_set_ss(x));
}

int convert_double_to_int(double x) {
    return _mm_cvtsd_si32(_mm_set_sd(x));
}
```

Die Makros "`_M_IX86_FP`", "`__AVX__`", "`__AVX2__`", "`__AVX512F__`", "`__AVX512CD__`", "`__AVX512BW__`", "`__AVX512DQ__`" und "`__AVX512VL__`" geben an, welche **/arch** -Compileroption Weitere Informationen finden Sie unter [Predefined Macros](../../preprocessor/predefined-macros.md). Die **/arch: AVX2** -Option und das `__AVX2__`-Makro wurden in Visual Studio 2013 Update 2, Version 12.0.34567.1 eingeführt, eingeführt. Eingeschränkte Unterstützung für **/arch: AVX512** wurde in Visual Studio 2017 hinzugefügt und in Visual Studio 2019 erweitert.

### <a name="to-set-this-compiler-option-for-avx-avx2-avx512-ia32-sse-or-sse2-in-visual-studio"></a>So legen Sie diese Compileroption für AVX, AVX2, AVX512, ia32, SSE oder SSE2 in Visual Studio fest

1. Öffnen Sie das Dialogfeld **Eigenschaften Seiten** für das Projekt. Weitere Informationen finden Sie unter [Festlegen des Compilers und der Buildeigenschaften](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurations Eigenschaften** **C/C++**  Folder aus.

1. Wählen Sie die Eigenschaften Seite **Code Generierung** aus.

1. Ändern Sie die Eigenschaft **erweiterten Anweisungs Satz aktivieren** .

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.

## <a name="see-also"></a>Siehe auch

[/arch (Mindestanforderungen an die CPU-Architektur)](arch-minimum-cpu-architecture.md)<br/>
[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
