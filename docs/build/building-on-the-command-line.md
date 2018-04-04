---
title: C/C++-Code in der Befehlszeile erstellen | Microsoft Docs
ms.custom: ''
ms.date: 03/29/2018
ms.technology:
- cpp-tools
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- command-line builds [C++]
- compiling source code [C++], command line
- builds [C++], command-line
- command line [C++], building from
- command line [C++], compilers
ms.assetid: 7ca9daed-a003-4162-842d-908f79058365
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fc4ec1034d4d77542df4a4241ad3ba5c087602ae
ms.sourcegitcommit: 78e5e5cdbafd29e2a6ccf68d4cce215136952907
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2018
---
# <a name="build-cc-code-on-the-command-line"></a>Erstellen von C/C++-Code in der Befehlszeile

Sie können C- und C++-Anwendungen in der Befehlszeile erstellen, indem Sie mithilfe von Tools, die in Visual Studio enthalten sind.

## <a name="how-to-get-the-command-line-tools"></a>Die Befehlszeilentools abrufen

Wenn Sie eine C++-arbeitsauslastungen in der Visual Studio-Installer auswählen, installiert Visual Studio *Plattformtoolset*. Ein Plattformtoolset hat alle C- und C++-Tools für eine bestimmte Visual Studio-Version, einschließlich der C/C++-Compiler, Linker, assemblern, und andere Buildtools sowie die entsprechenden Bibliotheken. Sie können alle diese Tools verwenden, in der Befehlszeile aus, und sie werden auch verwendet intern von der Visual Studio-IDE. Es gibt separate X86 gehostet und X64 gehosteten Compiler und Tools zum Erstellen von Code für X86, x 64, ARM und ARM64 Ziele. Jeder Satz von Tools für eine bestimmte Architektur von Host und das Ziel Build ist im Verzeichnis eigenen gespeichert.

Ordnungsgemäß funktioniert, müssen die Tools mehrere bestimmte Umgebungsvariablen festgelegt werden. Diese werden verwendet, um sie zu dem Pfad hinzuzufügen und festgelegt Datei Bibliotheksdatei und SDK-Verzeichnissen enthalten. Um diese Umgebungsvariablen festgelegt zu erleichtern, das Installationsprogramm erstellt die benutzerdefinierte *Befehlsdateien*, oder Batchdateien, während der Installation. Sie können eine dieser Befehlsdateien in einem Eingabeaufforderungsfenster einen bestimmten Host und Build Zielarchitektur, Windows SDK-Version, Zielplattform und Plattformtoolset festzulegende ausführen. Der Einfachheit halber erstellt das Installationsprogramm auch Tastenkombinationen im Startmenü (oder Startseite für Windows 8.x), die Developer-Eingabeaufforderungsfenster starten, indem diese Befehlsdateien verwenden, damit die erforderlichen Umgebungsvariablen festgelegt und kann verwendet werden.

Die erforderlichen Umgebungsvariablen sind spezifisch für Ihre Installation und der Build-Architektur, die Sie und durch Produktupdates und -Upgrades geändert werden können. Daher empfehlen wir dringend, dass Sie eine der installierten eingabeaufforderungsverknüpfungen oder Befehlsdateien verwenden, statt die Umgebungsvariablen in Windows selbst festzulegen. Weitere Informationen finden Sie unter [Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds](../build/setting-the-path-and-environment-variables-for-command-line-builds.md).

Das Befehlszeilen-Toolsets, Befehlsdateien und Verknüpfungen der Eingabeaufforderung, die installiert werden, hängen von Prozessor Ihres Computers und während der Installation ausgewählten Optionen. Mindestens sind die 32-Bit-X86 gehosteten 32-Bit-X86 systemeigenem Code zu erstellen und Tools cross Tools, die 64-Bit-X64 systemeigenem Code zu erstellen installiert. Wenn Sie 64-Bit-Windows verfügen, werden auch die 64-Bit-X64-gehostete systemeigene 64-Bit-Code zu erstellen und Tools cross Tools, die systemeigenen 32-Bit-Code erstellen installiert. Falls gewünscht die optionalen universelle Windows-Plattform von C++-Tools zu installieren, werden die 32-Bit und 64-Bit-systemeigenen Tools, die ARM-Code zu erstellen auch installiert. Andere arbeitsauslastungen möglicherweise zusätzliche Tools installieren.

## <a name="developer-command-prompt-shortcuts"></a>Entwickler eingabeaufforderungsverknüpfungen

Die eingabeaufforderungsverknüpfungen werden in einem Ordner hängt von der Version Visual Studio im Startmenü installiert. Hier ist eine Liste der grundlegenden eingabeaufforderungsverknüpfungen und die Build-Architekturen, die sie unterstützen:

- **Developer-Eingabeaufforderung** -richtet die Umgebung für die 32-Bit, X86 systemeigenen Tools verwenden, um die 32-Bit, X86 systemeigenem Code zu erstellen.
- **X86 native Tools-Eingabeaufforderung** -richtet die Umgebung für die 32-Bit, X86 systemeigenen Tools verwenden, um die 32-Bit, X86 systemeigenem Code zu erstellen.
- **X64 native Tools-Eingabeaufforderung** -richtet die Umgebung für die 64-Bit, X64 systemeigenen Tools verwenden, um die 64-Bit, X64 systemeigenem Code zu erstellen.
- **x86_x64 Cross Tools-Eingabeaufforderung** -richtet die Umgebung für die 32-Bit, X86 systemeigenen Tools verwenden, um die 64-Bit, X64 systemeigenem Code zu erstellen.
- **x64_x86 Cross Tools-Eingabeaufforderung** -richtet die Umgebung für die 64-Bit, X64 systemeigenen Tools verwenden, um die 32-Bit, X86 systemeigenem Code zu erstellen.

Die tatsächlichen Start Ordner und Verknüpfung Menünamen variieren abhängig von der Version von Visual Studio, die Sie installiert haben und die Installation des Spitznamens für das, wenn Sie eine festlegen. Z. B., wenn Sie Visual Studio 2017 installiert haben und Sie haben es das angegebene eine Installation Spitzname der *Vorschau*, heißt die Developer-eingabeaufforderungsverknüpfung **Developer-Eingabeaufforderung für VS 2017 (Vorschau)**, in einem Ordner namens **Visual Studio 2017**.

Wenn Sie installiert haben die [Build-Tools für Visual Studio-2017](https://go.microsoft.com/fwlink/p/?linkid=840931) (auch einschließlich der Visual Studio 2015 Update 3-Compilertoolset), nur architekturspezifischer oder der systemeigenen Sprache Cross tools entwicklereingabeaufforderung Optionen installiert werden. , und nicht die allgemeinen **Entwicklereingabeaufforderung** Verknüpfung.

<a name="developer_command_prompt"></a>
### <a name="to-open-a-developer-command-prompt-window"></a>Um ein Developer-Eingabeaufforderungsfenster zu öffnen.

1. Auf dem Desktop öffnen Sie das Windows **starten** Menü, und klicken Sie dann einen Bildlauf zum Suchen und öffnen Sie den Ordner für Ihre Version von Visual Studio, z. B. **Visual Studio 2017**. In einigen älteren Versionen von Visual Studio, sind die Tastenkombinationen in einen Unterordner namens **Visual Studio-Tools**.

1. Wählen Sie in den Ordner der **Entwicklereingabeaufforderung** für Ihre Version von Visual Studio. Diese Tastenkombination startet ein Developer-Eingabeaufforderungsfenster aus, die die Standard-Build-Architektur von 32-Bit, X86 systemeigenen Tools verwendet, um 32-Bit, X86 systemeigenem Code zu erstellen. Wenn Sie eine nicht standardmäßige Build Architektur bevorzugen, wählen Sie eine der systemeigenen oder Cross tools eingabeaufforderungen an den Host und Ziel-Architektur.

Eine schnellere Möglichkeit, ein Developer-Eingabeaufforderungsfenster zu öffnen ist, geben *entwicklereingabeaufforderung* in der desktop Suchfeld ein, wählen Sie dann das gewünschte Ergebnis.

## <a name="developer-command-files-and-locations"></a>Befehlsdateien für Entwickler und Standorte

Wenn Sie es vorziehen, Architektur Buildumgebung in eine vorhandene Eingabeaufforderungsfenster einzurichten, können Sie eines der (Batch-Befehlsdateien) vom Installationsprogramm erstellt festzulegende erforderliche Umgebung verwenden. Wir empfehlen Ihnen nur hierzu in ein neues Eingabeaufforderungsfenster, und wir empfehlen nicht Sie höhere Switch Umgebungen im gleichen Befehlsfenster. Der Speicherort dieser Dateien hängt von der Version von Visual Studio, die Sie installiert haben, sowie von Speicherort und Benennungskonventionen Auswahlmöglichkeiten, die Sie während der Installation vorgenommen. Für Visual Studio 2017 Standardinstallation auf einem 64-Bit-Computer befinden sich im \Programme Dateien (x86) \Microsoft Visual Studio\2017\\*Edition*, wobei *Edition* möglicherweise-Community Professional, Enterprise, BuildTools oder einen anderen Namen, die Sie angegeben. Ist für Visual Studio 2015 Installationspfad in \Programme (x86) \Microsoft Visual Studio 14.0.

Die primäre Developer-Eingabeaufforderung-Befehlsdatei, VsDevCmd.bat, befindet sich im Unterverzeichnis Common7\Tools des Installationsverzeichnisses. Wenn keine Parameter angegeben werden, dies die Umgebung richtet und den Host und das Ziel-Architektur für die 32-Bit-X86 systemeigenen Tools zu verwenden Build, um 32-Bit-X86 erstellen Code.

Zusätzliche Befehlsdateien stehen zum Einrichten von bestimmten Build-Architekturen, abhängig von der Prozessorarchitektur und der Visual Studio-Arbeitslasten und Optionen, die Sie installiert haben. In Visual Studio 2017 befinden diese sich im Unterverzeichnis VC\Auxiliary\Build des Visual Studio-Installationsverzeichnisses. In Visual Studio 2015 wird diese befinden sich in der VC VC\bin bzw. VC\bin\\*Architekturen* Unterverzeichnisse des Installationsverzeichnisses, wobei *Architekturen* wird zu den systemeigenen oder Cross-Compiler-Optionen. Diese Befehlsdateien Standardparameter festgelegt, und rufen VsDevCmd.bat angegebenen Buildumgebung Architektur einrichten. Eine Standardinstallation kann diese Befehlsdateien umfassen:

|Befehlsdatei|Host- und Ziel-Architekturen|
|---|---|
|**vcvars32.bat**| Verwenden Sie die 32-Bit-X86 systemeigenen-Tools zum Erstellen von 32-Bit-X86 Code.|
|**vcvars64.bat**| Verwenden Sie die 64-Bit-X64 systemeigenen-Tools zum Erstellen von 64-Bit-X64 Code.|
|**vcvarsx86_amd64.bat**| Verwenden Sie 32-Bit-nativen X86 Cross Tools zum Erstellen von 64-Bit-X64 Code.|
|**vcvarsamd64_x86.bat**| Verwenden Sie 64-Bit-nativen X64 Cross Tools zum Erstellen von X86 32-Bit-Code.|
|**vcvarsx86_arm.bat**| Verwenden Sie 32-Bit-nativen X86 Cross Tools, um die ARM-Code zu erstellen.|
|**vcvarsamd64_arm.bat**| Verwenden Sie 64-Bit-nativen X64 Cross Tools, um die ARM-Code zu erstellen.|
|**vcvarsall.bat**| Verwenden Sie Parameter, um den Host und für Zielarchitekturen sowie das SDK und Plattform Auswahlmöglichkeiten anzugeben. Rufen Sie eine Liste der unterstützten Optionen, mit einem **/help** Parameter.|

> [!CAUTION]
> Die vcvarsall.bat-Datei und anderen Visual Studio-Befehlsdateien können von einem Computer zu variieren. Ersetzen Sie eine fehlender oder beschädigte vcvarsall.bat-Datei nicht durch eine Datei von einem anderen Computer. Führen Sie erneut aus der Visual Studio-Installer, um die fehlende Datei zu ersetzen.
>
> Die vcvarsall.bat-Datei ist auch von Version zu Version unterschiedlich. Wenn die aktuelle Version von Visual Studio auf einem Computer, die auch eine frühere Version von Visual Studio verfügt installiert ist, werden nicht ausgeführt "vcvarsall.bat" oder eine andere Visual Studio-Befehlsdatei aus unterschiedlichen Versionen im selben Eingabeaufforderungsfenster.

## <a name="use-the-developer-tools-in-an-existing-command-window"></a>Verwenden Sie die Developer-Tools in einer vorhandenen Befehlsfenster

Die einfachste Möglichkeit, geben Sie eine bestimmten Build-Architektur in einer vorhandenen Befehlsfenster ist die Verwendung die Datei "vcvarsall.bat". "Vcvarsall.bat" können Sie die Umgebungsvariablen so konfigurieren Sie die Befehlszeile für systeminterne Kompilierung für 32-Bit oder 64-Bit- oder Cross-Kompilierung, X86 X64 oder ARM-Prozessoren festzulegen; Microsoft Store, universelle Windows-Plattform oder Windows-Desktop-Plattformen als Ziel; an welche Windows-SDK verwenden; und die Version der Plattform Toolset angeben. Wenn keine Argumente bereitgestellt werden, konfiguriert die vcvarsall.bat die Umgebungsvariablen für die Verwendung des aktuellen systemeigenen 32-Bit-Compilers für X86 Windows-Desktop-Ziele. Allerdings können Sie ihn so konfigurieren Sie alle für das systemeigene und cross Compilertools verwenden. Wenn Sie eine Compilerkonfiguration, die nicht installiert oder ist nicht auf der buildcomputerarchitektur verfügbar angeben, wird eine Fehlermeldung angezeigt.

### <a name="vcvarsall-syntax"></a>Vcvarsall-syntax

> **vcvarsall.bat** [*architecture*] [*platform_type*] [*winsdk_version*] [**-vcvars_ver=**_vcversion_]

*architecture*<br/>
Dieses optionale Argument gibt den Host und Ziel-Architektur verwendet. Wenn *Architektur* nicht angegeben ist, wird die Standard-Buildumgebung verwendet. Diese Argumente werden unterstützt:

|*architecture*|Compiler|Architektur des Host-Computers|Buildausgabearchitektur (Ziel)|
|----------------------------|--------------|----------------------------------|-------------------------------|
|**x86**|x86-32-Bit systemeigen|x86, x64|x86|
|**X86\_amd64** oder **X86\_X64**|Plattformübergreifende X64 auf x86|x86, x64|x64|
|**x86_arm**|ARM auf x86-Cross|x86, x64|ARM|
|**x86_arm64**|ARM64 auf X86 plattformübergreifende|x86, x64|ARM64|
|**AMD64** oder **X64**|X64 64-Bit systemeigen|x64|x64|
|**AMD64\_X86** oder **X64\_X86**|Plattformübergreifende X86 auf x64|x64|x86|
|**AMD64\_Arm** oder **X64\_Arm**|ARM auf X64 plattformübergreifende|x64|ARM|
|**AMD64\_arm64** oder **X64\_arm64**|ARM64 auf X64 plattformübergreifende|x64|ARM64|

*platform_type*<br/>
Diese optionalen Arguments können Sie angeben, **speichern** oder **Uwp** als den Plattformtyp aus. Standardmäßig wird die Umgebung zum Erstellen von Desktop- oder Konsolen-apps festgelegt.

*winsdk_version*<br/>
Gibt optional die Version des Windows SDK zu verwenden. Standardmäßig wird die neueste installierte Windows-SDK verwendet. Das Windows SDK-Version angeben möchten, können Sie eine vollständige Windows 10-SDK Zahl wie z. B. **10.0.10240.0**, oder geben Sie **8.1** zum Verwenden von Windows 8.1 SDK.

*vcversion*<br/>
Gibt optional die Visual Studio-Compilertoolset verwenden. Standardmäßig wird die Umgebung verwenden das aktuelle Visual Studio-2017 Compilertoolset festgelegt. Verwendung **-Vcvars_ver = 14.0** an das Visual Studio 2015-Compilertoolset.

<a name="vcvarsall"></a>
#### <a name="to-set-up-the-build-environment-in-an-existing-command-prompt-window"></a>So richten Sie die Build-Umgebung in eine vorhandene Eingabeaufforderungsfenster ein

1. Verwenden Sie an der Eingabeaufforderung den Befehl CD so ändern Sie in der Visual Studio-Installationsverzeichnisses. Verwenden Sie CD dann erneut auf das Unterverzeichnis ändern, die konfigurationsspezifischen Befehlsdateien enthält. Für Visual Studio 2017 ist dies das VC\Auxiliary\Build-Unterverzeichnis. Verwenden Sie für Visual Studio 2015 die VC-Unterverzeichnis.

1. Geben Sie den Befehl für Ihre bevorzugte Developer-Umgebung. Verwenden Sie z. B. zum ARM-Code für die universelle Windows-Plattform auf einer 64-Bit-Plattform erstellen mithilfe der neuesten Windows-SDK und Visual Studio 2017 RTM-Compilertoolset folgender Befehlszeile:

   `vcvarsall.bat amd64_arm uwp -vcvars_ver=14.10`

## <a name="create-your-own-command-prompt-shortcut"></a>Erstellen Sie eine eigene eingabeaufforderungsverknüpfung

Wenn Sie das Eigenschaftendialogfeld für eine der vorhandenen Verknüpfungen mit der Developer-Eingabeaufforderung öffnen, sehen Sie das Befehlsziel verwendet. Z. B. das Ziel für die **X64 Native Tools-Eingabeaufforderung für VS 2017** Verknüpfung handelt es sich etwa:

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvars64.bat"`

Architekturspezifischer Batchdateien Satz der *Architektur* Parameter, und rufen "vcvarsall.bat". Sie können die gleichen zusätzlichen Optionen auf diese Batchdateien übergeben, wie übergeben Sie zu "vcvarsall.bat", oder Sie können "vcvarsall.bat" einfach direkt aufrufen. Um Parameter für die Verknüpfung zu Ihrem eigenen Befehl anzugeben, fügen sie am Ende des Befehls in doppelte Anführungszeichen hinzu. Beispielsweise um eine Verknüpfung zum ARM-Code für universelle Windows-Plattform auf einer 64-Bit-Plattform zu erstellen, mit der neuesten Windows-SDK und Visual Studio 2017 RTM-Compilertoolset einzurichten, verwenden Sie etwas in dieser Befehlsziel in Ihrer Verknüpfung:

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvarsall.bat amd64_arm uwp -vcvars_ver=14.10"`

Sie müssen den Pfad entsprechend Ihrem Visual Studio-Installationsverzeichnis anpassen.

## <a name="command-line-tools"></a>Befehlszeilentools

Zum Erstellen eines C/C++-Projekts in der Befehlszeile, bietet Visual Studio diese Befehlszeilentools:

[CL](../build/reference/compiling-a-c-cpp-program.md)<br/>
Verwenden Sie den Compiler (cl.exe), um Quellcodedateien in Apps, Bibliotheken und DLLs zu kompilieren und zu verknüpfen.

[Link](../build/reference/linking.md)<br/>
Verwenden Sie den Linker (link.exe), um kompilierte Objektdateien in Apps und DLLs zu verknüpfen.

[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)<br/>
Verwenden von MSBuild (msbuild.exe) zum Erstellen von Visual C++-Projekte und Visual Studio-Projektmappen. Dies entspricht dem Ausführen der **erstellen** Projekt oder **Projektmappe** -Befehl in der Visual Studio-IDE.

[DEVENV](/visualstudio/ide/reference/devenv-command-line-switches)<br/>
Verwenden Sie DEVENV (devenv.exe) kombiniert mit einer Befehlszeilenoption – z. B. **/Build** oder **/Clean**– auszuführenden bestimmte Buildbefehle ohne Visual Studio-IDE anzuzeigen.

[NMAKE](../build/nmake-reference.md)<br/>
Verwenden Sie NMAKE (nmake.exe), um Aufgaben zu automatisieren, die Visual C++-Projekte mithilfe eines herkömmlichen Makefiles zu erstellen.

Wenn Sie in der Befehlszeile erstellen, ist der F1-Befehl nicht für sofortige Hilfe verfügbar. Stattdessen können Sie mithilfe einer Suchmaschine beim Abrufen von Informationen zu Warnungen, Fehlern und Meldungen oder können Sie die offline-Hilfedateien. Verwenden die Suche in [docs.microsoft.com](https://docs.microsoft.com/cpp/), geben Sie die Suchzeichenfolge in das Suchfeld am oberen Rand der Seite.

## <a name="in-this-section"></a>In diesem Abschnitt

In den Artikeln in diesem Abschnitt der Dokumentation erfahren Sie, wie Sie Apps über die Befehlszeile erstellen. Zudem wird beschrieben, wie Sie die Befehlszeilen-Buildumgebung für die Verwendung von 64-Bit-Toolsets und das Abzielen auf x86-, x64- und ARM-Plattformen verwenden. Und es wird gezeigt, wie Sie die Befehlszeilen-Buildtools MSBuild und NMAKE verwenden.

[Exemplarische Vorgehensweise: Kompilieren eines nativen C++-Programms in der Befehlszeile](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)<br/>
Gibt ein Beispiel, das zeigt, wie Sie ein einfaches C++-Programm über die Befehlszeile erstellen und kompilieren.

[Exemplarische Vorgehensweise: Kompilieren eines C-Programms in der Befehlszeile](../build/walkthrough-compile-a-c-program-on-the-command-line.md)<br/>
Beschreibt, wie Sie ein in der Programmiersprache C geschriebenes Programm kompilieren.

[Exemplarische Vorgehensweise: Kompilieren eines C++/CLI-Programms in der Befehlszeile](../build/walkthrough-compiling-a-cpp-cli-program-on-the-command-line.md)<br/>
Beschreibt, wie Sie ein C++-/CLI-Programm erstellen und kompilieren, das .NET Framework verwendet.

[Exemplarische Vorgehensweise: Kompilieren eines C++/-CX-Programms in der Befehlszeile](../build/walkthrough-compiling-a-cpp-cx-program-on-the-command-line.md)<br/>
Beschreibt, wie Sie ein C++-/CX-Programm erstellen und kompilieren, das die Windows Runtime verwendet.

[Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)<br/>
Beschreibt, wie ein Eingabeaufforderungsfenster starten, die über die erforderlichen Umgebungsvariablen für Befehlszeilenbuilds festgelegt, die auf X86, X64,- und ARM-Plattformen mithilfe eines 32-Bit oder 64-Bit-Toolsets verfügt.

[NMAKE-Referenz](../build/nmake-reference.md)<br/>
Enthält Links zu Artikeln, in denen das Microsoft Program Maintenance Utility (NMAKE.EXE) beschrieben wird.

[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)<br/>
Enthält Links zu Artikeln, in denen die Verwendung von MSBuild.EXE dargestellt wird.

## <a name="related-sections"></a>Verwandte Abschnitte

[/MD, /MT, /LD (Laufzeitbibliothek verwenden)](../build/reference/md-mt-ld-use-run-time-library.md)<br/>
Beschreibt die Verwendung dieser Compileroptionen für eine Debug- oder Releaselaufzeitbibliothek.

[C/C++-Compileroptionen](../build/reference/compiler-options.md)<br/>
Enthält Links zu Artikeln, in denen die C- und C++-Compileroptionen sowie CL.exe erläutert werden.

[Linkeroptionen](../build/reference/linker-options.md)<br/>
Enthält Links zu Artikeln, in denen die Linkeroptionen und LINK.EXE dargestellt werden.

[C/C++-Buildtools](../build/reference/c-cpp-build-tools.md)<br/>
Enthält Links zu den C/C++-Buildtools, die in Visual Studio enthalten sind.

## <a name="see-also"></a>Siehe auch

[Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)