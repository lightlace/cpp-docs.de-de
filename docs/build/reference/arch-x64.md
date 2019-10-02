---
title: /arch (x64)
ms.date: 10/01/2019
ms.assetid: ecda22bf-5bed-43f4-99fb-88aedd83d9d8
ms.openlocfilehash: 0ade6d9f744339ebaf38981d81334340b56080cb
ms.sourcegitcommit: 4517932a67bbf2db16cfb122d3bef57a43696242
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2019
ms.locfileid: "71816225"
---
# <a name="arch-x64"></a>/arch (x64)

Gibt die Architektur für die Codegenerierung auf x64 an. Siehe auch [/arch (x86)](arch-x86.md) und [/arch (Arm)](arch-arm.md).

## <a name="syntax"></a>Syntax

```
/arch:[AVX|AVX2|AVX512]
```

## <a name="arguments"></a>Argumente

**/Arch: AVX**<br/>
Aktiviert die Verwendung von Intel Advanced Vector Extensions-Anweisungen.

**/arch:AVX2**<br/>
Aktiviert die Verwendung von Intel Advanced Vector Extensions 2-Anweisungen.

**/Arch: AVX512**<br/>
Aktiviert die Verwendung von Intel Advanced Vector Extensions 512-Anweisungen.

## <a name="remarks"></a>Hinweise

Die Option **/arch** aktiviert die Verwendung bestimmter Anweisungs Satz Erweiterungen, insbesondere für die Vektor Berechnung, die in Prozessoren von Intel und AMD verfügbar ist. Im allgemeinen unterstützen mehr vor kurzem eingeführte Prozessoren möglicherweise zusätzliche Erweiterungen, die von älteren Prozessoren unterstützt werden. Sie sollten sich jedoch die Dokumentation für einen bestimmten Prozessor ansehen oder die Unterstützung der Anweisungs Satz Erweiterung mithilfe von __ überprüfen. [ CPUID](../../intrinsics/cpuid-cpuidex.md) vor dem Ausführen von Code mithilfe einer Anweisungs Satz Erweiterung.

**/arch** wirkt sich nur auf die Codegenerierung für Native Funktionen aus. Wenn Sie [/CLR](clr-common-language-runtime-compilation.md) für die Kompilierung verwenden, wirkt sich **/arch** nicht auf die Codegenerierung für verwaltete Funktionen aus.

Die Prozessor Erweiterungen haben die folgenden Merkmale:

- Im Standardmodus werden SSE2-Anweisungen für skalare Gleit Komma-und Vektor Berechnungen verwendet. Diese Anweisungen ermöglichen die Berechnung mit 128-Bit-Vektoren von Werten mit einfacher Genauigkeit, doppelter Genauigkeit und 1, 2, 4 oder 8 Byte ganzzahlige Werte sowie skalare Gleit Komma Werte mit einfacher Genauigkeit und doppelter Genauigkeit.

- **AVX** hat eine Alternative Anweisungs Codierung für Vektor-und Gleit Komma-skalaranweisungen eingeführt, die Vektoren von 128 Bits oder 256 Bits zulässt und alle Vektor Ergebnisse auf die vollständige Vektor Größe erweitert. (Um die Legacy Kompatibilität zu gewährleisten, behalten die Vektor Anweisungen im SSE-Stil alle Bits über Bit 127.) Die meisten Gleit Komma Operationen werden auf 256 Bits erweitert.

- **AVX2** erweitert die meisten ganzzahligen Vorgänge auf 256-Bit-Vektoren und ermöglicht die Verwendung von-FMA-Anweisungen (Multiplikation und hinzufügen).

- **AVX-512** hat ein weiteres Anweisungs Codierungs Formular eingeführt, das 512-Bit-Vektoren sowie bestimmte andere optionale Features zulässt. Es wurden auch Anweisungen für weitere Vorgänge hinzugefügt.

Jede **/arch** -Option kann auch die Verwendung anderer nicht Vektor Anweisungen ermöglichen, die dieser Option zugeordnet sind. Ein Beispiel hierfür ist die Verwendung bestimmter BMI-Anweisungen, wenn **/arch: AVX2** angegeben wird.

Das Präprozessorsymbol "`__AVX__`" wird definiert, wenn die Compileroption **/arch: AVX**, **/arch: AVX2** oder **/arch: AVX512** angegeben wird. Das Präprozessorsymbol "`__AVX2__`" wird definiert, wenn die Compileroption " **/arch: AVX2** " oder " **/arch: AVX512** " angegeben wird. Die Präprozessorsymbole `__AVX512F__`, `__AVX512CD__`, `__AVX512BW__`, `__AVX512DQ__` und `__AVX512VL__` werden definiert, wenn die **/arch: AVX512** -Compileroption angegeben wird. Weitere Informationen finden Sie unter [Predefined Macros](../../preprocessor/predefined-macros.md). Die Option **/arch: AVX2** wurde in Visual Studio 2013 Update 2, Version 12.0.34567.1 eingeführt, eingeführt. Eingeschränkte Unterstützung für **/arch: AVX512** wurde in Visual Studio 2017 hinzugefügt und in Visual Studio 2019 erweitert.

### <a name="to-set-the-archavx-archavx2-or-archavx512-compiler-option-in-visual-studio"></a>So legen Sie die/Arch: AVX,/Arch: AVX2 oder/Arch: AVX512-Compileroption in Visual Studio fest

1. Öffnen Sie das Dialogfeld **Eigenschaften Seiten** für das Projekt. Weitere Informationen finden Sie unter [Festlegen des Compilers und der Buildeigenschaften](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurations Eigenschaften** **C/C++**  Folder aus.

1. Wählen Sie die Eigenschaften Seite **Code Generierung** aus.

1. Wählen Sie im Dropdown Feld **erweiterten Anweisungs Satz aktivieren** die Option **Erweiterte Vektor Erweiterungen (/Arch: AVX)** , **Erweiterte Vektor Erweiterungen 2 (/Arch: AVX2)** oder **Erweiterte Vektor Erweiterungen 512 (/Arch: AVX512)** aus.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.

## <a name="see-also"></a>Siehe auch

[/arch (Mindestanforderungen an die CPU-Architektur)](arch-minimum-cpu-architecture.md)<br/>
[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
