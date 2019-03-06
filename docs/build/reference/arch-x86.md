---
title: /arch (x86)
ms.date: 11/04/2016
ms.assetid: 9dd5a75d-06e4-4674-aade-33228486078d
ms.openlocfilehash: e2aba6dc18db621710b5293f9f970fa5f453b8a9
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57421806"
---
# <a name="arch-x86"></a>/arch (x86)

Gibt die Architektur für die Codegenerierung auf x86 an. Siehe auch [/arch (x64)](../../build/reference/arch-x64.md) und [/arch (ARM)](../../build/reference/arch-arm.md).

## <a name="syntax"></a>Syntax

```
/arch:[IA32|SSE|SSE2|AVX|AVX2]
```

## <a name="arguments"></a>Argumente

**/arch:IA32**<br/>
Gibt keine erweiterten Anweisungen an, und gibt außerdem x87 für Gleitkommaberechnungen an.

**/arch:SSE**<br/>
Aktiviert die Verwendung von SSE-Anweisungen.

**/arch:SSE2**<br/>
Aktiviert die Verwendung von SSE2-Anweisungen. Dies ist die standardanweisung auf X86 Plattformen, wenn keine **/arch** angegeben wird.

**/arch:AVX**<br/>
Aktiviert die Verwendung von Intel Advanced Vector Extensions-Anweisungen.

**/arch:AVX2**<br/>
Aktiviert die Verwendung von Intel Advanced Vector Extensions 2-Anweisungen.

## <a name="remarks"></a>Hinweise

Die SSE- und SSE2-Anweisungen werden in verschiedenen Intel- und AMD-Prozessoren verwendet. Die AVX-Anweisungen gibt es bei Intel Sandy Bridge- und AMD Bulldozer-Prozessoren. AVX2-Anweisungen werden von Intel Haswell- und Broadwell-Prozessoren sowie AMD Excavator-basierten Prozessoren unterstützt.

Die `_M_IX86_FP`, `__AVX__` und `__AVX2__` Makros angeben, die Sie ggf. **/arch** -Compileroption verwendet wurde. Weitere Informationen finden Sie unter [Predefined Macros](../../preprocessor/predefined-macros.md). Die **/arch: avx2** Option und `__AVX2__` Makro in Visual Studio 2013 Update 2 Version 12.0.34567.1 eingeführt wurden.

Der Abfrageoptimierer entscheidet, wann und wie die SSE- und SSE2-Anweisungen verwenden, wenn **/arch** angegeben ist. Er verwendet SSE- und SSE2-Anweisungen für einige skalare Gleitkommaberechnungen, und zwar in Fällen, in denen die Verwendung der SSE/SSE2-Anweisungen und -Register Leistungsvorteile gegenüber dem x87-Gleitkomma-Registerstapel bietet. Dies bedeutet, dass im Code für Gleitkommaberechnungen tatsächlich eine Kombination aus x87 und SSE/SSE2 verwendet werden kann. Darüber hinaus mit **SSE2**, SSE2-Anweisungen für einige 64-Bit-Ganzzahloperationen verwendet werden können.

Neben den SSE- und SSE2-Anweisungen verwendet der Compiler weitere Anweisungen, die in den jeweiligen Prozessorrevisionen mit SSE- und SSE2-Unterstützung verfügbar sind. Die CMOV-Anweisung, die zuerst in der Pentium Pro-Revision der Intel-Prozessoren verwendet wurde, ist ein Beispiel hierfür.

Da der Compiler generiert X86, die SSE2-Anweisungen verwendet standardmäßig code, müssen Sie angeben **/arch:IA32** zum Deaktivieren der Generierung von SSE- und SSE2-Anweisungen für X86 Prozessoren.

**/ arch** nur wirkt sich auf die codegenerierung für systemeigene Funktionen Codes. Bei Verwendung von ["/ CLR"](../../build/reference/clr-common-language-runtime-compilation.md) kompiliert werden, **/arch** hat keine Auswirkungen auf die codegenerierung für verwaltete Funktionen.

**/ arch** und [/QIfist](../../build/reference/qifist-suppress-ftol.md) kann nicht in derselben Kompiliereinheit verwendet werden. Insbesondere wenn Sie das FP-Steuerwort nicht mithilfe von `_controlfp` ändern, legt der Laufzeitstartcode das x87 FPU-Steuerwort-Genauigkeitskontrollfeld auf 53 Bits fest. Daher verwendet jeder Vorgang vom Typ "float" und "double" in einem Ausdruck einen 53-Bit-Signifikanden und einen 15-Bit-Exponenten. Alle SSE-Operationen mit einfacher Genauigkeit verwenden jedoch 24-Bit-Signifikanden und einen 8-Bit-Exponenten, und SSE2-Operationen mit doppelter Genauigkeit verwenden 53-Bit-Signifikanden und einen 11-Bit-Exponenten. Weitere Informationen finden Sie unter [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md). Diese Unterschiede können in einer Ausdrucksbaumstruktur auftreten. Dies gilt jedoch nicht, wenn nach jedem untergeordneten Ausdruck eine Benutzerzuordnung stattfindet. Nehmen wir einmal die folgende Situation:

```cpp
r = f1 * f2 + d;  // Different results are possible on SSE/SSE2.
```

Vergleichen Sie:

```cpp
t = f1 * f2;   // Do f1 * f2, round to the type of t.
r = t + d;     // This should produce the same overall result
               // whether x87 stack is used or SSE/SSE2 is used.
```

### <a name="to-set-this-compiler-option-for-avx-avx2-ia32-sse-or-sse2-in-visual-studio"></a>So legen Sie diese Compileroption für AVX, AVX2, IA32, SSE oder SSE2 in Visual Studio fest

1. Öffnen der **Eigenschaftenseiten** im Dialogfeld für das Projekt. Weitere Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften**, **C/C++-** Ordner.

1. Wählen Sie die **Codegenerierung** Eigenschaftenseite.

1. Ändern der **Erweitertes Anweisungsset aktivieren** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.

## <a name="see-also"></a>Siehe auch

[/arch (Mindestanforderungen an die CPU-Architektur)](../../build/reference/arch-minimum-cpu-architecture.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
