---
title: /Gs (Stapel-Überprüfungsaufrufe kontrollieren)
ms.date: 10/25/2018
f1_keywords:
- /GS
helpviewer_keywords:
- disabling stack probes
- GS compiler option [C++]
- /GS compiler option [C++]
- stack, stack probes
- stack probes
- -GS compiler option [C++]
- stack checking calls
ms.assetid: 40daed7c-f942-4085-b872-01e12b37729e
ms.openlocfilehash: e31b42c1d9422d44c5f106f40c4a60a38f23425b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62270847"
---
# <a name="gs-control-stack-checking-calls"></a>/Gs (Stapel-Überprüfungsaufrufe kontrollieren)

Steuert den Schwellenwert für die stapelüberprüfungen.

## <a name="syntax"></a>Syntax

> **/Gs**[*size*]

## <a name="arguments"></a>Argumente

*size*<br/>
(Optional) Die Anzahl von Bytes, die von lokalen Variablen belegt werden können, bevor eine Stapelüberprüfung initiiert wird. Darf kein Leerzeichen zwischen **/GS** und *Größe*.

## <a name="remarks"></a>Hinweise

Ein *stapelüberprüfung* ist eine Codesequenz, die der Compiler am Anfang eines Funktionsaufrufs einfügt. Sobald die Stapelüberprüfung initiiert ist, belegt sie im Speicher so viel Platz, wie zum Speichern der lokalen Variablen der Funktion nötig ist. Dies bewirkt, dass das Betriebssystem in zusätzlichen Stapelspeicher zu benötigen, wenn erforderlich, bevor der Rest der Funktion ausgeführt wird, transparent Seite.

Standardmäßig generiert der Compiler Code, der eine Stapelüberprüfung initiiert, wenn für eine Funktion mehr als eine Seite Stapelspeicher erforderlich ist. Dies ist gleichbedeutend mit der Compileroption **/Gs4096** für X86, x 64, ARM, und ARM64-Plattformen. Mit diesem Wert sind eine Anwendung und der Speichermanager von Windows in der Lage, den für den Programmstapel reservierten Arbeitsspeicher zur Laufzeit dynamisch zu erhöhen.

> [!NOTE]
> Der Standardwert von **/Gs4096** ermöglicht, dass der Programmstapel von Anwendungen für Windows zur Laufzeit ordnungsgemäß vergrößert. Wir empfehlen, den Standardwert nur dann zu ändern, wenn Sie genau wissen, warum Sie ihn ändern müssen.

Für einige Programme, beispielsweise virtuelle Gerätetreiber, ist dieser Standardmechanismus zum Vergrößern des Stapels nicht erforderlich. In solchen Fällen stapelüberprüfungen nicht erforderlich sind und Sie können verhindern, dass der Compiler generieren sie durch Festlegen von *Größe* auf einen Wert, der größer als eine Funktion für die lokale Variable Speicherung benötigen.

**/ Gs0** initiiert die stack-Tests für jeden Funktionsaufruf, der Speicher für lokale Variablen erforderlich ist. Das kann sich negativ auf die Leistung auswirken.

Für X64 ausgerichtet ist, wenn die **/GS** Option wird angegeben, ohne eine *Größe* Argument, es ist identisch mit **/Gs0**. Wenn die *Größe* Argument liegt zwischen 1 und 9, D9014-Warnung wird ausgegeben, und der Effekt ist derselbe, als wenn **/Gs0**.

Für X86, ARM, und ARM64-Ziele, die **/GS** option ohne einen *Größe* Argument entspricht dem **/Gs4096**. Wenn die *Größe* Argument liegt zwischen 1 und 9, D9014-Warnung wird ausgegeben, und der Effekt ist derselbe, als wenn **/Gs4096**.

Für alle Ziele ein *Größe* Argument zwischen 10 und 2147485647 legt den Schwellenwert unter den angegebenen Wert fest. Ein *Größe* 2147485648 oder höher Ursachen Schwerwiegender Fehler C1049.

Können Sie stapelüberprüfungen ein- oder ausschalten aktivieren, indem Sie mit der [Check_stack](../../preprocessor/check-stack.md) Richtlinie. **/ GS** und `check_stack` Pragma haben keine Auswirkungen auf standardmäßige C-Bibliotheksroutinen und betreffen nur die Funktionen, die Sie kompilieren.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die **/GS** Compileroption und eine optionale Größe in **zusätzliche Optionen**. Wählen Sie **OK** oder **übernehmen** zum Speichern der Änderungen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
