---
title: / Qspectre | Microsoft Docs
ms.custom: ''
ms.date: 1/23/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
f1_keywords:
- /Qspectre
helpviewer_keywords:
- /Qspectre
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3d87850ae5413ccf876eb4d4b44b34e34527ef9a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="qspectre"></a>/Qspectre

Gibt die compilergenerierung von Anweisungen, um bestimmte Absorptionsspektrum Variant 1 Sicherheitsrisiken zu minimieren.

## <a name="syntax"></a>Syntax

> **/Qspectre**

## <a name="remarks"></a>Hinweise

Die **/Qspectre** Option veranlasst den Compiler, fügen Sie Anweisungen, um bestimmte mindern [Absorptionsspektrum Sicherheitsrisiken](https://spectreattack.com/spectre.pdf). Diese Sicherheitslücken, aufgerufen *seitenkanalangriffe spekulative Ausführung*, wirken sich auf viele Betriebssysteme und moderne Prozessoren, die Prozessoren von Intel, AMD, einschließlich und ARM.

Die **/Qspectre** Option ist standardmäßig deaktiviert.

In der ersten Version der **/Qspectre** Option funktioniert nur in optimiertem Code. Nehmen Sie Sie sicher, dass der Code mit allen Optionen für die Optimierung kompiliert wird (z. B. [/O2 oder/O1](o1-o2-minimize-size-maximize-speed.md) , aber nicht [/Od](od-disable-debug.md)) um sicherzustellen, dass das Minderung angewendet wird. Auf ähnliche Weise überprüfen jeglicher Code, der verwendet [#pragma optimieren ("Stg", off)](../../preprocessor/optimize.md).

### <a name="applicability"></a>Anwendbarkeit

Wenn der Code arbeitet mit Daten, die eine Vertrauensgrenze gekreuzt wir empfehlen die Verwendung der **/Qspectre** Option zum Erstellen und bereitzustellen, den Code, um dieses Problem so bald wie möglich zu minimieren. Beispiele für Code, der auf Daten ausgeführt wird, die eine Vertrauensgrenze gekreuzt sind Code, der nicht vertrauenswürdigen Eingabe lädt, die Ausführung beeinflussen können, z. B. Code, mit der Remoteprozeduraufruf, aufruft, analysiert nicht vertrauenswürdige Eingaben oder Dateien oder andere lokale prozessübergreifende verwendet Kommunikation (IPC)-Schnittstellen. Standard-Sandkasten Techniken möglicherweise nicht ausreichend. Sie sollten Ihre Sandkästen sorgfältig untersuchen, bevor Sie sich entscheiden, dass der Code keine Vertrauensgrenze durchgestrichen ist.

### <a name="availability"></a>Verfügbarkeit

Die **/Qspectre** Option steht in Visual Studio 2017 Version 15.5.5 und alle Updates für Microsoft Visual C++-Compiler (MSVC), die am oder nach 23 Januar 2018 vorgenommen.

Alle Versionen von Visual Studio 2017 Version 15.5 und alle Vorschauen von Visual Studio Version 15,6 enthalten bereits eine nicht dokumentierte Option **/d2guardspecload**, entspricht das ursprüngliche Verhalten der **/Qspectre**. Sie können **/d2guardspecload** , gelten die gleichen Maßnahmen in den Code in diesen Versionen des Compilers. Aktualisieren Sie den Build mit **/Qspectre** im Compiler, die die Option; unterstützen die **/Qspectre** Option kann außerdem neue Maßnahmen in höheren Versionen des Compilers unterstützen.

### <a name="effect"></a>Effekt

Die **/Qspectre** Option gibt Code zur Abwehr von Specter Variant 1, Grenzen überprüfen umgehen, [CVE-2017-5753](https://nvd.nist.gov/vuln/detail/CVE-2017-5753). Funktionsweise von Einfügung von Anweisungen, die als Barriere Ausführung spekulative Code fungieren. Die spezifischen Anweisungen zum Prozessor Spekulatives zu mindern hängt von den Prozessor und seine Micro-Architektur und möglicherweise in zukünftigen Versionen des Compilers ändern.

Wenn die **/Qspectre** aktiviert ist, versucht der Compiler, um Instanzen zu identifizieren, in denen spekulative Ausführung Grenzen überspringen kann, und fügt die Barriere-Anweisungen. Es ist wichtig zu beachten, dass es Einschränkungen für die Analyse, die ein Compiler ausführen können gibt, um Instanzen von Variant 1 zu identifizieren. Daher besteht keine Garantie, die alle mögliche Instanzen vom Typ Variant 1 unter instrumentiert werden **/Qspectre**.

### <a name="performance-impact"></a>Auswirkungen auf die Leistung

Die Leistungseinbußen **/Qspectre** in mehrere sehr große Codebasen vernachlässigbar sein angezeigt wurde, aber es gibt keine Garantie, Leistung des Codes bei **/Qspectre** bleibt unverändert. Sie sollten den Code, um die Auswirkungen der die Option auf die Leistung zu vergleichen. Wenn Sie wissen, dass das Minderung in einem leistungskritischen Block oder die Schleife nicht erforderlich ist, das Minderung kann selektiv deaktiviert werden mithilfe einer [__declspec(spectre(nomitigation))](../../cpp/spectre.md) Richtlinie. Diese Richtlinie ist nicht verfügbar in Compilern, die ausschließlich unterstützen die **/d2guardspecload** Option.

### <a name="additional-information"></a>Zusätzliche Informationen

Für weitere Details Sie den offiziellen finden [Microsoft Security Advisory ADV180002, Hinweise, spekulative Ausführung Seiten-Kanal Sicherheitsrisiken zu beseitigen](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002). Anleitungen finden Sie auch von Intel, [spekulative Ausführung clientseitigen Kanal Gegenmaßnahmen](https://software.intel.com/sites/default/files/managed/c5/63/336996-Speculative-Execution-Side-Channel-Mitigations.pdf), und ARM "," [Cache Spekulatives dienstseitige-Kanäle](https://developer.arm.com/-/media/Files/pdf/Cache_Speculation_Side-channels.pdf). Eine Windows-spezifische Absorptionsspektrum und überdauern Gegenmaßnahmen Überblick finden Sie unter [verstehen von Auswirkungen auf die Leistung Absorptionsspektrum und überdauern Maßnahmen auf Windows-Systemen](https://cloudblogs.microsoft.com/microsoftsecure/2018/01/09/understanding-the-performance-impact-of-spectre-and-meltdown-mitigations-on-windows-systems/) im Microsoft Secure-Blog. Eine Übersicht über Absorptionsspektrum Sicherheitslücke MSVC Gegenmaßnahmen, finden Sie unter [Absorptionsspektrum Gegenmaßnahmen in MSVC](https://blogs.msdn.microsoft.com/vcblog/2018/01/15/spectre-mitigations-in-msvc./) im Visual C++-Team-Blog.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die **/Qspectre** -Compileroption in der **Zusatzoptionen** Feld. Wählen Sie **OK** um die Änderung zu übernehmen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[/Q-Optionen (Vorgänge auf niedriger Ebene)](../../build/reference/q-options-low-level-operations.md)  
[Compileroptionen](../../build/reference/compiler-options.md)  
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)  
