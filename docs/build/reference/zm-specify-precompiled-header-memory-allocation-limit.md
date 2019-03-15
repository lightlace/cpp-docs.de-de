---
title: /Zm (Begrenzung der Speicherzuweisung für vorkompilierten Header festlegen)
ms.date: 03/08/2019
f1_keywords:
- /zm
helpviewer_keywords:
- PCH files, memory allocation limit
- Zm compiler option [C++]
- /Zm compiler option [C++]
- precompiled header files, memory allocation limit
- Specify Precompiled Header Memory Allocation Limit compiler option
- cl.exe compiler, memory allocation limit
- .pch files, memory allocation limit
- memory allocation, Memory Allocation Limit compiler option
- -Zm compiler option [C++]
ms.assetid: 94c77d5e-6672-46a7-92e0-3f69e277727d
ms.openlocfilehash: 09df8e1ee9a97289e29e1191e8c1585580435b79
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807896"
---
# <a name="zm-specify-precompiled-header-memory-allocation-limit"></a>/Zm (Begrenzung der Speicherzuweisung für vorkompilierten Header festlegen)

Bestimmt den Arbeitsspeicher, den der Compiler für die Erstellung von vorkompilierten Headern belegt.

## <a name="syntax"></a>Syntax

```
/Zmfactor
```

## <a name="arguments"></a>Argumente

*factor*<br/>
Ein Skalierungsfaktor zur Bestimmung des Arbeitsspeichers, den der Compiler für die Erstellung vorkompilierter Header verwendet.

Die *Faktor* Argument ist ein Prozentsatz der Standardgröße eines Compiler definierten Arbeitspuffers. Der Standardwert von *Faktor* ist 100 (Prozent), aber Sie können angeben, größere oder kleinere Mengen.

## <a name="remarks"></a>Hinweise

In Versionen vor Visual Studio 2015 der C++-Compiler verwendet die Reihe von eigenständigen Heaps, und jede wurde eine feste Begrenzung. Derzeit der Compiler dynamisch die Heaps bei Bedarf bis zu eine Beschränkung für die Heapgesamtgröße vergrößert, und ermöglicht der vorkompilierten Headerdatei mehrere Adressbereiche enthalten sollen. Daher die **/Zm** Compiler-Option ist nur selten notwendig.

Wenn der Compiler nicht mehr Heapspeicher verfügbar genügend ist, und gibt die [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) Fehlermeldung bei Verwendung der **/Zm** -Compileroption verwenden, Sie haben möglicherweise zu viel Arbeitsspeicher reserviert. Entfernen Sie ggf. die **/Zm** Option.

Wenn der Compiler gibt die [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) Fehlermeldung, die eine zugehörige [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) Nachricht gibt an, der *Faktor* Argument zu verwenden, wenn Sie mit der erneutkompilieren **/Zm** -Compileroption. Diese Meldung dient nur erheblich, wenn ein vorkompilierter Header verwendet `#pragma hdrstop`. In anderen Fällen ist es ein vermeidbare Fehler aufgrund von Problemen der Windows virtuellen Speichers Druck und die Empfehlung, verwenden die **/Zm** Option ignoriert werden sollen. Erwägen Sie stattdessen die Anzahl der parallelen Prozessen reduziert, bei Verwendung der **maxcpucount** Option aus, um MSBUILD. EXE-Datei in Verbindung mit der **/MP** Option aus, um CL. EXE-DATEI. Weitere Informationen finden Sie unter [Probleme für vorkompilierte Header (PCH) und Empfehlungen](https://devblogs.microsoft.com/cppblog/precompiled-header-pch-issues-and-recommendations/).

Die folgende Tabelle zeigt, wie die *Faktor* Argument wirkt sich auf die Begrenzung der speicherzuweisung aus, wenn Sie davon ausgehen, die Größe des Puffers für den vorkompilierten Header ist 75 MB.

|Wert von *Faktor*|Maximale Speicherbelegung|
|-----------------------|-----------------------------|
|10|7.5 MB|
|100|75 MB|
|200|150 MB|
|1000|750 MB|
|2000|1500 MB|

## <a name="other-ways-to-set-the-memory-allocation-limit"></a>Weitere Möglichkeiten zur Festlegung der maximalen Speicherbelegung

### <a name="to-set-the-zm-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie die Compileroption "/Zm" in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie im Navigationsbereich **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile**.

1. Geben Sie die **/Zm** -Compileroption in der **zusätzliche Optionen** Feld.

### <a name="to-set-the-zm-compiler-option-programmatically"></a>So legen Sie die Compileroption "/Zm" programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compiler-Optionen](compiler-options.md)<br/>
[MSVC-Compiler-Befehlszeilensyntax](compiler-command-line-syntax.md)
