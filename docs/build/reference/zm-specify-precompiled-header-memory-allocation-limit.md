---
title: /Zm (Begrenzung der Speicherzuweisung für vorkompilierten Header festlegen)
ms.date: 11/04/2016
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
ms.openlocfilehash: d0f79ed1b38401abbc65898193f2305bd432bb28
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57419919"
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

In früheren Versionen von Visual C++ verwendete der Compiler eine Reihe von eigenständigen Heaps, die jeweils über eine feste Begrenzung verfügten. Derzeit werden die Heaps bei Bedarf vom Compiler dynamisch bis zu einem Grenzwert für die Heapgesamtgröße vergrößert; nur zum Erstellen vorkompilierter Header ist ein Puffer mit fester Größe erforderlich. Daher die **/Zm** Compiler-Option ist nur selten notwendig.

Wenn der Compiler nicht mehr Heapspeicher verfügbar genügend ist, und gibt die [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) Fehlermeldung bei Verwendung der **/Zm** -Compileroption verwenden, Sie haben möglicherweise zu viel Arbeitsspeicher reserviert. Entfernen Sie ggf. die **/Zm** Option. Wenn der Compiler gibt die [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) Fehlermeldung, die eine zugehörige [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) Nachricht gibt an, der *Faktor* Argument zu verwenden, wenn Sie mit der erneutkompilieren **/Zm** -Compileroption.

Die folgende Tabelle zeigt, wie die *Faktor* Argument wirkt sich auf die Begrenzung der speicherzuweisung aus, wenn Sie davon ausgehen, die Größe des Puffers für den vorkompilierten Header ist 75 MB.

|Wert von *Faktor*|Maximale Speicherbelegung|
|-----------------------|-----------------------------|
|10|7.5 MB|
|100|75 MB|
|200|150 MB|
|1000|750 MB|
|2000|1500 MB|

## <a name="other-ways-to-set-the-memory-allocation-limit"></a>Weitere Möglichkeiten zur Festlegung der maximalen Speicherbelegung

#### <a name="to-set-the-zm-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie die Compileroption "/Zm" in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie im Navigationsbereich **Konfigurationseigenschaften**, **C/C++-**, **Befehlszeile**.

1. Geben Sie die **/Zm** -Compileroption in der **zusätzliche Optionen** Feld.

#### <a name="to-set-the-zm-compiler-option-programmatically"></a>So legen Sie die Compileroption "/Zm" programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
