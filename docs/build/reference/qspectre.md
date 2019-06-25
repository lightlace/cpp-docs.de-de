---
title: /Qspectre
ms.date: 10/12/2018
f1_keywords:
- /Qspectre
helpviewer_keywords:
- /Qspectre
ms.openlocfilehash: e0d3af50015b77af297cbee22f439cd17d803de9
ms.sourcegitcommit: 6cf0c67acce633b07ff31b56cebd5de3218fd733
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2019
ms.locfileid: "67344152"
---
# <a name="qspectre"></a>/Qspectre

Gibt die Compilergenerierung von Anweisungen an, um bestimmte mit Spectre-Variante 1 zusammenhängende Sicherheitsrisiken abzumildern.

## <a name="syntax"></a>Syntax

> **/Qspectre**

## <a name="remarks"></a>Hinweise

Die Option **/Qspectre** ist in Visual Studio 2017, Version 15.5.5 und höher, und in Visual Studio 2015 Update 3 bis [KB 4338871](https://support.microsoft.com/help/4338871/visual-studio-2015-update-3-spectre-variant-1-toolset-qspectre) verfügbar. Sie bewirkt, dass der Compiler Anweisungen einfügt, um bestimmte [Spectre-Sicherheitsrisiken](https://spectreattack.com/spectre.pdf) zu verringern. Diese Sicherheitsrisiken heißen *seitenkanalangriffe mit spekulativer Ausführung*. Sie Auswirkungen auf vielen Betriebssystemen und modernen Prozessoren, einschließlich Prozessoren von Intel, AMD und ARM.

Die Option **/Qspectre** ist standardmäßig deaktiviert.

In ihrer ursprünglichen Version funktionierte die **/Qspectre**-Option nur mit optimiertem Code. In Visual Studio 2017, Version 15.7 und höher, wird die Option **/Qspectre** auf allen Optimierungsebenen unterstützt.

Microsoft Visual C++-Bibliotheken stehen ebenfalls in Versionen mit Spectre-Entschärfung zur Verfügung. Die Spectre-entschärften Bibliotheken für Visual Studio 2017 und höher können im Visual Studio-Installer heruntergeladen werden. Finden sie der **Einzelkomponenten** Registerkarte **Compiler, Buildtools und Laufzeiten**, und "Bibliotheken für Spectre" im Namen haben. Sowohl DLLs als auch statische Runtimebibliotheken mit aktivierter Entschärfung sind für eine Teilmenge der Visual C++-Runtimes verfügbar: VC++-Startcode, vcruntime140, msvcp140, concrt140 und vcamp140. Die DLLs sind nur für die lokalen Bereitstellung unterstützt. Der Inhalt des visuellen Elements C++ 2017 und höher Runtime-Bibliotheken Redistributable noch nicht geändert.

Sie können auch mit Spectre-Bibliotheken für MFC und ATL auch installieren. Finden sie der **Einzelkomponenten** Registerkarte **SDKs, Bibliotheken und Frameworks**.

### <a name="applicability"></a>Anwendbarkeit

Wenn Ihr Code ausgeführt wird, auf Daten, die eine Vertrauensgrenze gekreuzt werden soll, und es wird empfohlen, die **"/ qspectre"** Option neu erstellen und Bereitstellen von Ihren Code, um dieses Problem so schnell wie möglich zu beheben. Ein Beispiel solcher Code ist Code, der nicht vertrauenswürdige Eingaben lädt, die Ausführung beeinflussen können. Code, der Remoteprozeduraufruf ist z. B. aufruft, analysiert wird, nicht vertrauenswürdige Eingaben oder Dateien oder anderen Schnittstellen des lokalen prozessübergreifenden Kommunikation (IPC) verwendet. Standardtechniken wie das Verwenden einer Sandbox sind möglicherweise nicht ausreichend. Untersuchen Sie Ihre Sandkästen sorgfältig, bevor Sie entscheiden, dass Ihr Code eine Vertrauensgrenze plattformübergreifende nicht.

### <a name="availability"></a>Verfügbarkeit

Die **"/ qspectre"** Option ist verfügbar in Visual Studio 2017 Version 15.5.5 und alle Updates an Microsoft C++ Compiler (MSVC) vorgenommen werden, am oder nach dem 23. Januar 2018. Verwenden Sie den Visual Studio-Installer, um den Compiler zu aktualisieren und um die Spectre-entschärften Bibliotheken als einzelne Komponenten zu installieren. Die **/Qspectre**-Option ist ferner in Visual Studio 2015 Update 3 bis zu einem Patch erhältlich. Weitere Informationen finden Sie in [KB 4338871](https://support.microsoft.com/help/4338871).

Alle Versionen von Visual Studio 2017 Version 15.5 und alle Preview-Versionen von Visual Studio 2017 Version 15.6. nicht dokumentierte Option einschließen **/d2guardspecload**. Dies entspricht das ursprüngliche Verhalten der **"/ qspectre"** . Sie können **/d2guardspecload** verwenden, um in diesem Versionen des Compilers die gleichen Entschärfungen auf Ihren Code anzuwenden. Es wird empfohlen, Sie aktualisieren Ihre zu verwendenden Build **"/ qspectre"** im Compiler, die die Option unterstützen. Die **"/ qspectre"** Option kann auch neue Lösungen unterstützen, in höheren Versionen des Compilers.

### <a name="effect"></a>Effekt

Die **/Qspectre**-Option gibt Code aus, um die Spectre-Variante 1, Bounds Check Bypass, [CVE-2017-5753](https://nvd.nist.gov/vuln/detail/CVE-2017-5753) zu entschärfen. Sie funktioniert durch Einfügen von Anwendungen, die als Sperre der spekulativen Codeausführung fungieren. Die spezifischen Anweisungen zur Entschärfung der Prozessorspekulation hängen vom Prozessor und seiner Mikroarchitektur ab und können sich in kommenden Versionen des Compilers ändern.

Wenn Sie aktivieren die **"/ qspectre"** Option versucht der Compiler zur Identifikation von Instanzen, in denen spekulativer Ausführung Grenzen Überprüfungen umgehen kann. Das ist, in denen die Barriere Anweisungen eingefügt. Es ist wichtig, um die Grenzwerte für die Analyse bewusst sein, die ein Compiler tun kann, um die Identifikation von Instanzen des Variant-Wert 1. Daher besteht keine Garantie, die alle mögliche Instanzen vom Typ Variant 1 unter instrumentiert werden **"/ qspectre"** .

### <a name="performance-impact"></a>Auswirkungen auf die Leistung

Auswirkungen auf die Leistung **"/ qspectre"** so in mehrere beträchtliche Codebasen vernachlässigbar sein. Es gibt jedoch keine Garantie, die Leistung Ihres Codes unter **"/ qspectre"** bleibt unverändert. Sie sollten Benchmarks Ihres Codes vornehmen, um die Auswirkungen der Option auf die Leistung zu bestimmen. Wenn Sie wissen, dass die Lösung in einem leistungskritischen Block oder eine Schleife keine Voraussetzungen sind, können Sie die Lösung selektiv deaktivieren, durch Verwendung von einem [__declspec(spectre(nomitigation))](../../cpp/spectre.md) Richtlinie. Diese Richtlinie nicht verfügbar in Compilern, die nur unterstützen die **/d2guardspecload** Option.

### <a name="required-libraries"></a>Erforderliche Bibliotheken

Die **"/ qspectre"** -Compileroption generiert Code, der implizit Versionen der Common Language Runtime-Bibliotheken erstellt, um die Spectre-entschärfungen bieten verknüpft. Diese Bibliotheken stellen optionale Komponenten dar, die mithilfe des Visual Studio-Installers installiert werden müssen:

- MSVC-Version *version_numbers* Libs for Spectre \[(x86 und x64) | (ARM) | (ARM64)]
- Visual C++ ATL für \[(x86/x64) | ARM | ARM64] mit Spectre-Entschärfungen
- Visual C++ MFC für \[x86/x64 | ARM | ARM64] mit Spectre-Entschärfungen

Wenn Sie Ihren Code mit erstellen **"/ qspectre"** und diese Bibliotheken sind nicht installiert ist, die Erstellen von Systemberichten **Warnung MSB8038: Die Spectre-Entschärfung ist aktiviert, aber es wurden keine Spectre-entschärften Bibliotheken gefunden**. Wenn MFC- oder ATL-Code nicht erstellt werden, und der Linker einen Fehler, z. B. meldet **Schwerwiegender Fehler LNK1104: Datei "oldnames.lib" kann nicht geöffnet werden**, diese fehlenden Bibliotheken können die Ursache sein.

### <a name="additional-information"></a>Zusätzliche Informationen

Weitere Informationen finden Sie in der offiziellen [Microsoft Security Advisory ADV180002, Anleitungen zum Verringern von Sicherheitsrisiken in seitenkanalangriffe mit spekulativer Ausführung](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002). Anweisungen sind außerdem von Intel, [Speculative Execution Side Channel Mitigations](https://software.intel.com/sites/default/files/managed/c5/63/336996-Speculative-Execution-Side-Channel-Mitigations.pdf), und ARM, [Cache Speculation Side-channels](https://developer.arm.com/-/media/Files/pdf/Cache_Speculation_Side-channels.pdf), erhältlich. Eine Übersicht der Windows-spezifische Spectre und Meltdown Lösungen, finden Sie [verstehen der Leistungseinbußen bei Spectre und Meltdown Maßnahmen auf Windows-Systemen](https://www.microsoft.com/security/blog/2018/01/09/understanding-the-performance-impact-of-spectre-and-meltdown-mitigations-on-windows-systems/). Einen Überblick über die Spectre Anfälligkeiten MSVC Schutzmaßnahmen, finden Sie unter [Spectre-entschärfungen in MSVC](https://devblogs.microsoft.com/cppblog/spectre-mitigations-in-msvc./) auf die C++ -Teamblog.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Klicken Sie auf der Eigenschaftenseite auf **Konfigurationseigenschaften** > **C/C++**  > **Befehlszeile**.

1. Geben Sie die Compileroption **/Qspectre** im Feld **Zusätzliche Optionen** ein. Wählen Sie **OK** aus, um die Änderung zu übernehmen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[/Q-Optionen (Vorgänge auf niedriger Ebene)](q-options-low-level-operations.md)<br/>
[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
