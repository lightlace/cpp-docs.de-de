---
title: / Qspectre | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/12/2018
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
ms.openlocfilehash: 0baba6503d1d5b4e382347f4f4d9680b11f954ce
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2018
ms.locfileid: "49328518"
---
# <a name="qspectre"></a>/Qspectre

Gibt an, der compilergenerierung von Anweisungen, um bestimmte Spectre-Variante 1-Sicherheitsrisiken zu verringern.

## <a name="syntax"></a>Syntax

> **/Qspectre**

## <a name="remarks"></a>Hinweise

Die **"/ qspectre"** Option ist in Visual Studio 2017 Version 15.5.5 verfügbar und höher, und klicken Sie in Visual Studio 2015 Update 3 über [KB 4338871](https://support.microsoft.com/help/4338871/visual-studio-2015-update-3-spectre-variant-1-toolset-qspectre). Veranlasst den Compiler zum Einfügen von Anweisungen, um bestimmte verringern [Spectre-Sicherheitsrisiken](https://spectreattack.com/spectre.pdf). Diese Sicherheitsrisiken namens *seitenkanalangriffe mit spekulativer Ausführung*, wirken sich auf viele Betriebssysteme und modernen Prozessoren, einschließlich der Prozessoren von Intel, AMD und ARM.

Die **"/ qspectre"** Option ist standardmäßig deaktiviert.

In der ersten Version der **"/ qspectre"** Option funktioniert nur in optimiertem Code. In Visual Studio 2017 Version 15.7 und höher die **"/ qspectre"** Option auf allen optimierungsebenen unterstützt wird. 

Microsoft Visual C++-Bibliotheken sind auch in Versionen mit Spectre-Entschärfung verfügbar. Die auch mit Spectre-Bibliotheken für Visual Studio 2017 können im Visual Studio-Installer heruntergeladen werden. Sie befinden sich die **Einzelkomponenten** Registerkarte **Compiler, Buildtools und Laufzeiten**, und "Bibliotheken für Spectre" im Namen haben. Sowohl DLL-als auch statische Runtime-Bibliotheken mit der Lösung, die aktiviert sind für einen Teil der Visual C++-Laufzeiten verfügbar: VC++-Startcode, vcruntime140, msvcp140, concrt140 und vcamp140. Die DLLs werden nur für die lokalen Bereitstellung unterstützt. der Inhalt des Visual C++ 2017 Common Language Runtime-Bibliotheken Redistributable wurden nicht geändert. Sie können Bibliotheken mit Spectre-verringert auch installieren, für MFC- und ATL, finden Sie in der **Einzelkomponenten** Registerkarte **SDKs, Bibliotheken und Frameworks**.

### <a name="applicability"></a>Anwendbarkeit

Wenn Ihr Code ausgeführt wird, auf Daten, die eine Vertrauensgrenze gekreuzt empfehlen wir die Verwendung der **"/ qspectre"** Option neu erstellen und Bereitstellen von Ihren Code, um dieses Problem so schnell wie möglich zu beheben. Beispiele für Code, der für Daten ausgeführt wird, die eine Vertrauensgrenze gekreuzt sind Code, der nicht vertrauenswürdige Eingaben lädt, die Ausführung beeinflussen können, z. B. Code, mit der Remoteprozeduraufruf, aufruft, analysiert wird, nicht vertrauenswürdige Eingaben oder Dateien oder andere lokale prozessübergreifende verwendet Kommunikation (IPC)-Schnittstellen. Standard-Sandkasten-Verfahren möglicherweise nicht ausreichend. Sie sollten Ihre Sandkästen sorgfältig untersuchen, bevor Sie sich entscheiden, dass Ihr Code eine Vertrauensgrenze nicht überschreiten, ist.

### <a name="availability"></a>Verfügbarkeit

Die **"/ qspectre"** Option ist verfügbar in Visual Studio 2017 Version 15.5.5 und alle Updates für Microsoft Visual C++-Compiler (MSVC) vorgenommen werden, am oder nach dem 23. Januar 2018. Verwenden Sie Visual Studio-Installer, um den Compiler zu aktualisieren und die Bibliotheken mit Spectre-verringert als einzelne Komponenten zu installieren. Die **"/ qspectre"** Option steht auch in Visual Studio 2015 Update 3 über einen Patch. Weitere Informationen finden Sie unter [KB 4338871](https://support.microsoft.com/help/4338871).

Alle Versionen von Visual Studio 2017 Version 15.5 und alle Preview-Versionen von Visual Studio 2017 Version 15.6 enthalten eine nicht dokumentierte Option, **/d2guardspecload**, entspricht das ursprüngliche Verhalten der **"/ qspectre"**. Sie können **/d2guardspecload** auf die gleichen Schutzmaßnahmen auf den Code in diesen Versionen des Compilers anwenden. Aktualisieren Sie Ihren Build mit **"/ qspectre"** im Compiler, die die Option; unterstützen die **"/ qspectre"** Option kann auch neue Lösungen unterstützen, in höheren Versionen des Compilers.

### <a name="effect"></a>Effekt

Die **"/ qspectre"** Option gibt Code an Schreckgespenst Variant-Wert 1, Grenzen, überprüfen Sie umgehen, verringern [CVE-2017-5753](https://nvd.nist.gov/vuln/detail/CVE-2017-5753). Dies funktioniert durch Einfügen von Anweisungen, die als Grenze Ausführung spekulative Code dienen. Folgen Sie den Anweisungen zum Verringern der Prozessor Spekulatives verwendet hängen von den Prozessor und die Micro-Architektur, und können in zukünftigen Versionen des Compilers ändern.

Wenn die **"/ qspectre"** aktiviert ist, versucht der Compiler zur Identifikation von Instanzen, in denen spekulativer Ausführung Grenzen überspringen kann, und fügt die Barriere-Anweisungen. Es ist wichtig zu beachten, dass es Grenzen für die Analyse, die ein Compiler ausführen können gibt, um die Identifikation von Instanzen des Variant-Wert 1. Daher besteht keine Garantie, die alle mögliche Instanzen vom Typ Variant 1 unter instrumentiert werden **"/ qspectre"**.

### <a name="performance-impact"></a>Auswirkungen auf die Leistung

Auswirkungen auf die Leistung **"/ qspectre"** in verschiedene sehr große Codebasen vernachlässigbar sein angezeigt wurde, aber es gibt keine Garantie, die Leistung Ihres Codes unter **"/ qspectre"** bleibt unverändert. Sie sollten-benchmark, Ihren Code, um die Auswirkungen der Option auf die Leistung zu testen. Wenn Sie wissen, dass die Lösung nicht in einem leistungskritischen Block oder eine Schleife erforderlich ist, die Lösung kann selektiv deaktiviert werden mithilfe einer [__declspec(spectre(nomitigation))](../../cpp/spectre.md) Richtlinie. Diese Richtlinie ist nicht verfügbar in Compilern, die nur unterstützen die **/d2guardspecload** Option.

### <a name="required-libraries"></a>Erforderlichen Bibliotheken

Die **"/ qspectre"** -Compileroption generiert Code, der implizit Versionen der Common Language Runtime-Bibliotheken verknüpft, die zum Bereitstellen von Spectre-entschärfungen erstellt wurden. Diese Bibliotheken sind optionale Komponenten, die mithilfe von Visual Studio-Installer installiert werden müssen:

- VC++ 2017, Version *Version_numbers* Bibliotheken, für Spectre \[(X86- und X64) | (ARM) | (ARM64)]
- Visual C++ ATL für \[(X86/X64) | ARM | ARM64] mit Spectre-Entschärfungen
- Visual C++ MFC für \[X86/X64 | ARM | ARM64] mit Spectre-Entschärfungen

Wenn Sie Ihren Code mit erstellen **"/ qspectre"** und diese Bibliotheken sind nicht installiert ist, die Erstellen von Systemberichten **Warnung MSB8038: Spectre-Entschärfung ist aktiviert, aber Entschärften Bibliotheken wurden nicht gefunden**. Wenn MFC- oder ATL-Code nicht erstellt werden, und der Linker einen Fehler, z. B. meldet **Schwerwiegender Fehler LNK1104: Datei "oldnames.lib" kann nicht geöffnet werden**, diese fehlenden Bibliotheken können die Ursache sein.

### <a name="additional-information"></a>Zusätzliche Informationen

Weitere Informationen finden Sie den offiziellen [Microsoft Security Advisory ADV180002, Anleitungen zum Verringern von Sicherheitsrisiken in seitenkanalangriffe mit spekulativer Ausführung](https://portal.msrc.microsoft.com/en-US/security-guidance/advisory/ADV180002). Anleitungen finden Sie auch von Intel, [spekulative Ausführung Seite Kanal Entschärfungen](https://software.intel.com/sites/default/files/managed/c5/63/336996-Speculative-Execution-Side-Channel-Mitigations.pdf), und ARM, [Cache Spekulatives dienstseitige-Kanäle](https://developer.arm.com/-/media/Files/pdf/Cache_Speculation_Side-channels.pdf). Eine Übersicht der Windows-spezifische Spectre und Meltdown Lösungen, finden Sie [verstehen der Leistungseinbußen bei Spectre und Meltdown Maßnahmen auf Windows-Systemen](https://cloudblogs.microsoft.com/microsoftsecure/2018/01/09/understanding-the-performance-impact-of-spectre-and-meltdown-mitigations-on-windows-systems/) Blog des Microsoft Secure. Einen Überblick über die Spectre-Sicherheitsrisiko behoben, indem die MSVC-Lösungen, finden Sie unter [Spectre-entschärfungen in MSVC](https://blogs.msdn.microsoft.com/vcblog/2018/01/15/spectre-mitigations-in-msvc./) im Visual C++-Teamblog.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die **"/ qspectre"** -Compileroption in der **zusätzliche Optionen** Feld. Wählen Sie **OK** um die Änderung zu übernehmen.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[/Q-Optionen (Vorgänge auf niedriger Ebene)](../../build/reference/q-options-low-level-operations.md)<br/>
[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)
