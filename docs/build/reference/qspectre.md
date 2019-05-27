---
title: /Qspectre
ms.date: 10/12/2018
f1_keywords:
- /Qspectre
helpviewer_keywords:
- /Qspectre
ms.openlocfilehash: e44416a44a9f772c17bc734d26c62ff87be775c8
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837417"
---
# <a name="qspectre"></a>/Qspectre

Gibt die Compilergenerierung von Anweisungen an, um bestimmte mit Spectre-Variante 1 zusammenhängende Sicherheitsrisiken abzumildern.

## <a name="syntax"></a>Syntax

> **/Qspectre**

## <a name="remarks"></a>Anmerkungen

Die Option **/Qspectre** ist in Visual Studio 2017, Version 15.5.5 und höher, und in Visual Studio 2015 Update 3 bis [KB 4338871](https://support.microsoft.com/help/4338871/visual-studio-2015-update-3-spectre-variant-1-toolset-qspectre) verfügbar. Sie bewirkt, dass der Compiler Anweisungen einfügt, um bestimmte [Spectre-Sicherheitsrisiken](https://spectreattack.com/spectre.pdf) zu verringern. Diese Sicherheitsrisiken, die als *spekulative ausführungsseitige Channelangriffe* bezeichnet werden, betreffen viele Betriebssysteme und moderne Prozessoren, einschließlich Prozessoren von Intel, AMD und ARM.

Die Option **/Qspectre** ist standardmäßig deaktiviert.

In ihrer ursprünglichen Version funktionierte die **/Qspectre**-Option nur mit optimiertem Code. In Visual Studio 2017, Version 15.7 und höher, wird die Option **/Qspectre** auf allen Optimierungsebenen unterstützt.

Microsoft Visual C++-Bibliotheken stehen ebenfalls in Versionen mit Spectre-Entschärfung zur Verfügung. Die Spectre-entschärften Bibliotheken für Visual Studio 2017 und höher können im Visual Studio-Installer heruntergeladen werden. Sie befinden sich auf der Registerkarte **Einzelne Komponenten** unter **Compiler, Buildtools und Runtimes** und weisen die Zeichenfolge „Libs for Spectre“ im Namen auf. Sowohl DLLs als auch statische Runtimebibliotheken mit aktivierter Entschärfung sind für eine Teilmenge der Visual C++-Runtimes verfügbar: VC++-Startcode, vcruntime140, msvcp140, concrt140 und vcamp140. Die DLLs werden nur für anwendungslokale Bereitstellung unterstützt; die Inhalte der Visual C++ 2017 und höherer weitervertreibbaren Runtimebibliotheken wurden nicht geändert. Ferner können Sie Spectre-entschärfte Bibliotheken für MFC und ATL installieren, die Sie auf der Registerkarte **Einzelne Komponenten** unter **SDKs, Bibliotheken und Frameworks** finden.

### <a name="applicability"></a>Anwendbarkeit

Wenn Ihr Code mit Daten arbeitet, die eine Vertrauensgrenze überqueren, empfehlen wir, dass Sie die Option **/Qspectre** verwenden, um Ihren Code erneut zu erstellen und bereitzustellen, um dieses Problem so bald wie möglich zu entschärfen. Beispiele für Code, der mit Daten arbeitet, die eine Vertrauensgrenze überqueren, beinhalten Code, der nicht vertrauenswürdige Eingaben lädt, die sich auf die Ausführung auswirken können, beispielsweise Code, der Remoteprozeduraufrufe vornimmt, nicht vertrauenswürdige Eingaben oder Dateien analysiert oder andere lokale Schnittstellen für die Interprozesskommunikation (IPC) verwendet. Standardtechniken wie das Verwenden einer Sandbox sind möglicherweise nicht ausreichend. Sie sollten Ihre Sandboxes sorgfältig untersuchen, bevor Sie zu dem Urteil gelangen, dass Ihr Code keine Vertrauensgrenze überquert.

### <a name="availability"></a>Verfügbarkeit

Die **/Qspectre**-Option ist in Visual Studio 2017, Version 15.5.5, und in allen Updates für Microsoft MSVC-Compiler (MSVC) verfügbar, die am oder nach dem 23. Januar 2018 erstellt wurden. Verwenden Sie den Visual Studio-Installer, um den Compiler zu aktualisieren und um die Spectre-entschärften Bibliotheken als einzelne Komponenten zu installieren. Die **/Qspectre**-Option ist ferner in Visual Studio 2015 Update 3 bis zu einem Patch erhältlich. Weitere Informationen finden Sie in [KB 4338871](https://support.microsoft.com/help/4338871).

Alle Versionen von Visual Studio 2017, Version 15.5, und alle Vorschauversionen von Visual Studio 2017, Version 15.6, enthalten eine nicht dokumentierte Option **/d2guardspecload**, die gleichwertig zu dem anfänglichen Verhalten von **/Qspectre** ist. Sie können **/d2guardspecload** verwenden, um in diesem Versionen des Compilers die gleichen Entschärfungen auf Ihren Code anzuwenden. Aktualisieren Sie Ihren Build für die Verwendung von **/Qspectre** in Compilern, die die Option unterstützen; die **/Qspectre**-Option unterstützt in späteren Versionen des Compilers darüber hinaus möglicherweise neuere Entschärfungen.

### <a name="effect"></a>Effekt

Die **/Qspectre**-Option gibt Code aus, um die Spectre-Variante 1, Bounds Check Bypass, [CVE-2017-5753](https://nvd.nist.gov/vuln/detail/CVE-2017-5753) zu entschärfen. Sie funktioniert durch Einfügen von Anwendungen, die als Sperre der spekulativen Codeausführung fungieren. Die spezifischen Anweisungen zur Entschärfung der Prozessorspekulation hängen vom Prozessor und seiner Mikroarchitektur ab und können sich in kommenden Versionen des Compilers ändern.

Wenn die Option **/Qspectre** aktiviert ist, versucht der Compiler, Instanzen zu identifizieren, in denen die spekulative Ausführung möglicherweise Grenzprüfungen umgeht und fügt die Sperranweisungen ein. Es muss darauf hingewiesen werden, dass die Analyse, die ein Compiler ausführen kann, um Instanzen von Variante 1 zu identifizieren, begrenzt ist. Daher besteht keine Garantie, dass alle möglichen Instanzen von Variante 1 unter **/Qspectre** instrumentiert werden.

### <a name="performance-impact"></a>Auswirkungen auf die Leistung

Die Auswirkungen von **/Qspectre** auf die Leistung haben sich in verschiedenen sehr großen Codebasen als vernachlässigbar erweisen, es gibt aber keine Garantie, dass die Leistung Ihres Codes unter **/Qspectre** unbeeinträchtigt bleibt. Sie sollten Benchmarks Ihres Codes vornehmen, um die Auswirkungen der Option auf die Leistung zu bestimmen. Wenn Sie wissen, dass die Entschärfung in einem leistungskritischen Block oder einer leistungskritischen Schleife nicht erforderlich ist, kann die Entschärfung mithilfe einer [__declspec(spectre(nomitigation))](../../cpp/spectre.md)-Anweisung selektiv deaktiviert werden. Diese Anweisung ist in Compilern, die nur die Option **/d2guardspecload** unterstützen, nicht verfügbar.

### <a name="required-libraries"></a>Erforderliche Bibliotheken

Die Compileroption **/Qspectre** generiert Code, der implizit Versionen der Runtimebibliotheken linkt, die zur Entschärfung von Spectre erstellt wurden. Diese Bibliotheken stellen optionale Komponenten dar, die mithilfe des Visual Studio-Installers installiert werden müssen:

- MSVC-Version *version_numbers* Libs for Spectre \[(x86 und x64) | (ARM) | (ARM64)]
- Visual C++ ATL für \[(x86/x64) | ARM | ARM64] mit Spectre-Entschärfungen
- Visual C++ MFC für \[x86/x64 | ARM | ARM64] mit Spectre-Entschärfungen

Wenn Sie Ihren Code mithilfe von **/Qspectre** erstellen und diese Bibliotheken nicht installiert sind, meldet das Buildsystem **Warnung MSB8038: Die Spectre-Entschärfung ist aktiviert, aber es wurden keine Spectre-entschärften Bibliotheken gefunden**. Wenn bei der Erstellung Ihres MFC- oder ATL-Codes ein Fehler auftritt und der Linker einen Fehler wie **Schwerwiegender Fehler LNK1104: Datei ‚oldnames.lib‘ kann nicht geöffnet werden** ausgibt, können diese fehlenden Bibliotheken die Ursache sein.

### <a name="additional-information"></a>Zusätzliche Informationen

Weitere Details finden Sie in der offiziellen [Microsoft-Sicherheitsempfehlung ADV180002, Anweisungen für die Risikominderung von spekulativen ausführungsseitigen Channelsicherheitsanfälligkeiten](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002). Anweisungen sind außerdem von Intel, [Speculative Execution Side Channel Mitigations](https://software.intel.com/sites/default/files/managed/c5/63/336996-Speculative-Execution-Side-Channel-Mitigations.pdf), und ARM, [Cache Speculation Side-channels](https://developer.arm.com/-/media/Files/pdf/Cache_Speculation_Side-channels.pdf), erhältlich. Eine Windows-spezifische Übersicht der Spectre- und Meltdown-Entschärfungen finden Sie unter [Understanding the performance impact of Spectre and Meltdown mitigations on Windows Systems](https://cloudblogs.microsoft.com/microsoftsecure/2018/01/09/understanding-the-performance-impact-of-spectre-and-meltdown-mitigations-on-windows-systems/) im Microsoft Secure-Blog. Eine Übersicht der durch die MSVC-Entschärfungen angegangenen Spectre-Sicherheitsrisiken finden Sie unter [Spectre mitigations in MSVC](https://blogs.msdn.microsoft.com/vcblog/2018/01/15/spectre-mitigations-in-msvc./) im Visual C++-Teamblog.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md)

1. Klicken Sie auf der Eigenschaftenseite auf **Konfigurationseigenschaften** > **C/C++** > **Befehlszeile**.

1. Geben Sie die Compileroption **/Qspectre** im Feld **Zusätzliche Optionen** ein. Wählen Sie **OK** aus, um die Änderung zu übernehmen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[/Q-Optionen (Vorgänge auf niedriger Ebene)](q-options-low-level-operations.md)<br/>
[MSVC-Compileroptionen](compiler-options.md)<br/>
[Syntax für die MSVC-Compilerbefehlszeile](compiler-command-line-syntax.md)
