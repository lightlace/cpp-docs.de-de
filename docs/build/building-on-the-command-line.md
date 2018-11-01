---
title: Erstellen von C/C++-Code in der Befehlszeile
ms.custom: conceptual
ms.date: 06/21/2018
helpviewer_keywords:
- command-line builds [C++]
- compiling source code [C++], command line
- builds [C++], command-line
- command line [C++], building from
- command line [C++], compilers
ms.assetid: 7ca9daed-a003-4162-842d-908f79058365
ms.openlocfilehash: bc5080ff14cf8629c98077bf1e3e39e4b824b48b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452038"
---
# <a name="build-cc-code-on-the-command-line"></a>Erstellen von C/C++-Code in der Befehlszeile

Sie können C- und C++-Anwendungen in der Befehlszeile erstellen, mithilfe von Tools, die in Visual Studio enthalten sind.

## <a name="how-to-get-the-command-line-tools"></a>Wie Sie die Befehlszeilentools abrufen

Bei der Auswahl eines C++-Workloads in Visual Studio-Installer installiert die Visual Studio *Plattformtoolset*. Ein Plattformtoolset verfügt über alle C- und C++-Tools für eine bestimmte Visual Studio-Version, einschließlich der C/C++-Compiler, Linker, assemblern, und andere Buildtools sowie die entsprechenden Bibliotheken. Sie können diese Tools verwenden, in der Befehlszeile aus, und sie werden auch verwendet intern von der Visual Studio-IDE. Es gibt separate X86 gehosteten und X64 gehosteten Compiler und Tools zum Erstellen von Code für X86, x 64, ARM und ARM64-Ziele. Jeder Satz von Tools für eine bestimmte Architektur für Hostserver und-Zielserver Build wird in einem eigenen Verzeichnis gespeichert.

Ordnungsgemäß funktioniert, müssen die Tools verschiedene bestimmte Umgebungsvariablen festgelegt werden. Diese werden verwendet, um sie dem Pfad hinzugefügt und festzulegen sind-Datei, Bibliotheksdatei und SDK-Speicherorte. Um einfacher auf diese Umgebungsvariablen festlegen können, das Installationsprogramm erstellt angepasste *Befehlsdateien*, oder eine Gruppe von Dateien während der Installation. Sie können eine der folgenden Befehlsdateien ausführen, in einem Eingabeaufforderungsfenster aus, um einen bestimmten Host und Build Zielarchitektur, Windows SDK-Version, als Zielplattform und Plattformtoolset festzulegen. Der Einfachheit halber erstellt das Installationsprogramm auch Verknüpfungen in Ihrem Menü "Start" (oder die Startseite für Windows 8.x), die Developer-Eingabeaufforderung Windows starten Sie mithilfe dieser Befehlsdateien, damit die erforderlichen Umgebungsvariablen festgelegt und kann verwendet werden.

Die erforderlichen Umgebungsvariablen sind für die Installation und das Build-Architektur, die Sie und durch Produktupdates und -Upgrades geändert werden können. Aus diesem Grund wird dringend empfohlen, dass Sie eine der installierten eingabeaufforderungsverknüpfungen oder Befehlsdateien verwenden, statt die Umgebungsvariablen in Windows selbst festzulegen. Weitere Informationen finden Sie unter [Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds](../build/setting-the-path-and-environment-variables-for-command-line-builds.md).

Das Befehlszeilen-Toolsets, Befehlsdateien und Verknüpfungen der Eingabeaufforderung, die installiert werden, hängen von der Prozessor Ihres Computers und während der Installation ausgewählten Optionen. Mindestens werden die 32-Bit-X86-gehosteten Tools, die 32-Bit-X86 nativen Code zu erstellen und plattformübergreifende Tools, die 64-Bit-X64 nativen Code zu erstellen, installiert. Wenn Sie 64-Bit-Windows haben, werden die 64-Bit-X64-gehosteten Tools, die systemeigenen 64-Bit-Code zu erstellen und plattformübergreifende Tools, die systemeigenen 32-Bit-Code erstellt auch installiert werden. Wenn Sie die optionale C++ Universal Windows Platform-Tools installieren möchten, werden die 32-Bit- und 64-Bit systemeigenen Tools, die ARM-Code erstellt auch installiert werden. Andere Workloads können zusätzliche Tools installieren.

## <a name="developer-command-prompt-shortcuts"></a>Verknüpfungen der Developer-Eingabeaufforderung

Die Verknüpfungen der Eingabeaufforderung werden in einem hängt von der Version Visual Studio-Ordner in Ihrem Menü "Start" installiert. Hier ist eine Liste der grundlegenden eingabeaufforderungsverknüpfungen und die Build-Architekturen, die sie unterstützen:

- **Developer-Eingabeaufforderung** -richtet die Umgebung für die 32-Bit, X86 Native Tools verwenden, um die 32-Bit, X86 Native Code zu erstellen.
- **X86 native Tools-Eingabeaufforderung** -richtet die Umgebung für die 32-Bit, X86 Native Tools verwenden, um die 32-Bit, X86 Native Code zu erstellen.
- **X64 native Tools-Eingabeaufforderung** -richtet die Umgebung für die 64-Bit, X64 Native Tools verwenden, um die 64-Bit, X64 Native Code zu erstellen.
- **x86_x64 Cross Tools-Eingabeaufforderung** -richtet die Umgebung für die 32-Bit, X86 Native Tools verwenden, um die 64-Bit, X64 Native Code zu erstellen.
- **x64_x86 Cross Tools-Eingabeaufforderung** -richtet die Umgebung für die 64-Bit, X64 Native Tools verwenden, um die 32-Bit, X86 Native Code zu erstellen.

Die tatsächlichen Start Ordner und die Tastenkombination Menünamen variieren je nach der Version von Visual Studio, die Sie installiert haben und die Installation Spitznamen, wenn Sie eine Eigenschaft festgelegt. Beispiel: Wenn Sie Visual Studio 2017 installiert haben, und Sie haben da sie eine Spitzname der Installation von *Vorschau*, den Namen der Developer-eingabeaufforderungsverknüpfung **Developer-Eingabeaufforderung für Visual Studio 2017 (Vorschauversion)**, in einem Ordner namens **Visual Studio 2017**.

Wenn Sie installiert haben die [Build-Tools für Visual Studio 2017](https://go.microsoft.com/fwlink/p/?linkid=875721) (wozu auch gehört das Compiler-Toolset von Visual Studio 2015 Update 3), nur architekturspezifische oder der systemeigenen Cross tools-Developer-Eingabeaufforderung Optionen installiert sind , und nicht den allgemeinen **Developer-Eingabeaufforderung** Verknüpfung.

<a name="developer_command_prompt"></a>
### <a name="to-open-a-developer-command-prompt-window"></a>Um ein Developer-Eingabeaufforderungsfenster zu öffnen.

1. Öffnen Sie auf dem Desktop der Windows **starten** Menü, und scrollen Sie zum Suchen und öffnen Sie den Ordner für Ihre Version von Visual Studio, z. B. **Visual Studio 2017**. In einigen früheren Versionen von Visual Studio können die Tastenkombinationen, die in einem Unterordner namens sind **Visual Studio-Tools**.

1. Wählen Sie in den Ordner, der **Developer-Eingabeaufforderung** für Ihre Version von Visual Studio. Diese Verknüpfung startet ein Developer-Eingabeaufforderungsfenster aus, die die Standard-Build-Architektur von 32-Bit, X86 Native Tools verwendet, um 32-Bit, X86 Native Code zu erstellen. Falls eine nicht standardmäßige Build-Architektur gewünscht, wählen Sie eine der systemeigenen oder Cross tools-eingabeaufforderungen an den Host und eine Zielarchitektur.

Geben eine noch schnellere Möglichkeit, ein Developer-Eingabeaufforderungsfenster zu öffnen ist *Developer-Eingabeaufforderung* in das Suchfeld den desktop, wählen Sie dann das gewünschte Ergebnis.

## <a name="developer-command-files-and-locations"></a>Speicherorte und Developer-Befehlsdateien

Wenn Sie die Build-Architektur-Umgebung in ein vorhandenes Fenster der Eingabeaufforderung festlegen möchten, können eine der Befehlsdateien (Batchdateien) vom Installationsprogramm erstellte Sie die erforderliche Umgebung festlegen. Wir empfehlen Ihnen nur hierzu ein Eingabeaufforderungsfenster, und wir empfehlen nicht Sie höhere Switch-Umgebungen im gleichen Befehlsfenster. Der Speicherort dieser Dateien hängt von der Version von Visual Studio, die Sie installiert haben, und auf Speicherort und Benennungskonventionen Optionen, die Sie während der Installation vorgenommen. Für Visual Studio 2017, Standardinstallation auf einem 64-Bit-Computer befinden sich im \Programme Dateien (x86) \Microsoft Visual Studio\2017\\*Edition*, wobei *Edition* möglicherweise-Community Professional, Enterprise, BuildTools oder einen anderen Namen, die Sie angegeben haben. Für Visual Studio 2015 ist der Speicherort der Standardinstallation in \Programme (x86) \Microsoft Visual Studio-14.0.

Die primäre Developer-Eingabeaufforderung Befehlsdatei VsDevCmd.bat, befindet sich im Unterverzeichnis "Common7\Tools" des Installationsverzeichnisses. Wenn keine Parameter angegeben werden, dadurch die Umgebung wird aus, und der Hostserver und-Zielserver-Architektur für die 32-Bit-X86 Native Tools zu verwenden erstellen, um 32-Bit-X86 erstellen Code.

Zusätzliche Befehlsdateien stehen zum Einrichten von bestimmten Build-Architekturen, abhängig von Ihrer Prozessorarchitektur und der Visual Studio-arbeitsauslastungen und Optionen, die Sie installiert haben. In Visual Studio 2017 befinden dieser im Unterverzeichnis "VC\Auxiliary\Build" des Visual Studio-Installationsverzeichnisses. In Visual Studio 2015, diese befinden sich in der VC VC\bin oder VC\bin\\*Architekturen* Unterverzeichnisse des Installationsverzeichnisses, wobei *Architekturen* ist eine der systemeigenen oder Cross-Compiler-Optionen. Diese Befehlsdateien Standardparameter festgelegt, und rufen VsDevCmd.bat, um den angegebenen Build-Architektur-Umgebung einzurichten. Eine typische Installation kann diese Befehlsdateien enthalten:

|Befehlsdatei|Hostserver und-Zielserver Architekturen|
|---|---|
|**vcvars32.bat**| Verwenden Sie die 32-Bit-X86 Native-Tools zum Erstellen von 32-Bit-X86 Code.|
|**vcvars64.bat**| Verwenden Sie die 64-Bit-X64 Native-Tools zum Erstellen von 64-Bit-X64 Code.|
|**vcvarsx86_amd64.bat**| Verwenden Sie die 32-Bit-X86 Native Cross Tools zum Erstellen von 64-Bit-X64 Code.|
|**vcvarsamd64_x86.bat**| Verwenden Sie die 64-Bit-X64 Native Cross Tools zum Erstellen von 32-Bit-X86 Code.|
|**vcvarsx86_arm.bat**| Verwenden Sie die 32-Bit-X86 Native Cross Tools, um die ARM-Code zu erstellen.|
|**vcvarsamd64_arm.bat**| Verwenden Sie die 64-Bit-X64 Native Cross Tools, um die ARM-Code zu erstellen.|
|**vcvarsall.bat**| Verwenden Sie Parameter, um den Host und für Zielarchitekturen sowie das SDK und von der Plattform Auswahlmöglichkeiten anzugeben. Rufen Sie eine Liste der unterstützten Optionen, mit einem **/help** Parameter.|

> [!CAUTION]
> Die vcvarsall.bat-Datei und andere Visual Studio-Befehl-Dateien können von Computer zu Computer variieren. Ersetzen Sie eine fehlender oder beschädigte vcvarsall.bat-Datei nicht durch eine Datei von einem anderen Computer. Wiederholen Sie den Visual Studio-Installer, um die fehlende Datei zu ersetzen.
>
> Die vcvarsall.bat-Datei ist auch von Version zu Version unterschiedlich. Wenn die aktuelle Version von Visual Studio auf einem Computer, die auch eine frühere Version von Visual Studio ist installiert ist, werden nicht ausgeführt "vcvarsall.bat" oder eine andere Visual Studio-Befehlsdatei aus unterschiedlichen Versionen im selben Eingabeaufforderungsfenster.

## <a name="use-the-developer-tools-in-an-existing-command-window"></a>Verwenden Sie die Developer Tools in ein vorhandenes Befehlsfenster

Verwenden Sie die vcvarsall.bat-Datei ist die einfachste Möglichkeit, eine bestimmten Build-Architektur in ein vorhandenes Befehlsfenster angeben werden. "Vcvarsall.bat" können Sie die Umgebungsvariablen so konfigurieren Sie die Befehlszeile für systeminterne Kompilierung für 32-Bit oder 64-Bit- oder Cross-Kompilierung, X86 X64 oder ARM-Prozessoren festzulegen; Microsoft Store, universelle Windows-Plattform oder Windows-Desktop-Plattformen als Ziel; an der Windows SDK verwenden; und die plattformtoolsetversion angeben. Wenn keine Argumente bereitgestellt werden, konfiguriert die vcvarsall.bat die Umgebungsvariablen für die Verwendung von des aktuellen systemeigenen 32-Bit-Compilers für X86 Windows-Desktop-Ziele. Allerdings können Sie es so konfigurieren Sie eine der systemeigenen oder cross Compilertools verwenden. Wenn Sie eine Compilerkonfiguration angeben, die nicht installiert oder ist nicht auf der buildcomputerarchitektur verfügbar ist, wird eine Fehlermeldung angezeigt.

### <a name="vcvarsall-syntax"></a>Vcvarsall-syntax

> **"vcvarsall.bat"** [*Architektur*] [*Platform_type*] [*Winsdk_version*] [**-Vcvars_ver =** _Vcversion_]

*Architektur*<br/>
Dieses optionale Argument gibt an, dem Hostserver und-Zielserver Architektur verwendet wird. Wenn *Architektur* nicht angegeben ist, wird die Standard-Buildumgebung verwendet. Diese Argumente werden unterstützt:

|*Architektur*|Compiler|Architektur des Host-Computers|Buildausgabearchitektur (Ziel)|
|----------------------------|--------------|----------------------------------|-------------------------------|
|**x86**|x86-32-Bit systemeigen|x86, x64|x86|
|**X86\_amd64** oder **X86\_X64**|Plattformübergreifende X64 auf x86|x86, x64|x64|
|**x86_arm**|ARM auf x86-Cross|x86, x64|ARM|
|**x86_arm64**|ARM64 auf X86 plattformübergreifende|x86, x64|ARM64|
|**AMD64** oder **X64**|X64 64-Bit systemeigen|x64|x64|
|**AMD64\_X86** oder **X64\_X86**|X86 auf X64 cross|x64|x86|
|**AMD64\_Arm** oder **X64\_Arm**|ARM auf X64 plattformübergreifende|x64|ARM|
|**AMD64\_arm64** oder **X64\_arm64**|ARM64 auf X64 plattformübergreifende|x64|ARM64|

*platform_type*<br/>
Diese optionalen Arguments können Sie angeben, **speichern** oder **Uwp** als den Plattformtyp aus. Standardmäßig wird die Umgebung festgelegt, um Desktop- oder Konsolen-apps zu erstellen.

*winsdk_version*<br/>
Gibt optional die Version des Windows SDK verwenden. Standardmäßig wird das neueste installierte Windows-SDK verwendet. Um die Windows SDK-Version anzugeben, können Sie eine vollständige Windows 10 SDK Zahl wie z. B. **10.0.10240.0**, oder geben Sie **8.1** mit dem Windows 8.1 SDK.

*vcversion*<br/>
Gibt optional die Visual Studio-Compiler-Toolset verwendet. Standardmäßig wird die Umgebung festgelegt, mit dem aktuellen Visual Studio 2017-Compilertoolset. Verwendung **-Vcvars_ver = 14.0** an das Visual Studio 2015-Compilertoolset.

<a name="vcvarsall"></a>
#### <a name="to-set-up-the-build-environment-in-an-existing-command-prompt-window"></a>Zum Einrichten der Buildumgebung in ein vorhandenes Fenster der Eingabeaufforderung

1. Verwenden Sie an der Eingabeaufforderung des Befehls CD, um zum Installationsverzeichnis von Visual Studio zu ändern. Verwenden Sie CD dann erneut so ändern in das Unterverzeichnis, das die konfigurationsspezifischen-Befehl enthält. Für Visual Studio 2017 handelt es sich um die VC\Auxiliary\Build-Unterverzeichnis. Verwenden Sie für Visual Studio 2015 die VC-Unterverzeichnis.

1. Geben Sie den Befehl für Ihre bevorzugte entwicklerumgebung. Verwenden Sie z. B. zum ARM-Code für UWP auf einer 64-Bit-Plattform erstellen mithilfe der neuesten Windows SDK und das Visual Studio 2017 RTM-Compilertoolset, diese Befehlszeile ein:

   `vcvarsall.bat amd64_arm uwp -vcvars_ver=14.10`

## <a name="create-your-own-command-prompt-shortcut"></a>Erstellen Sie eigene eingabeaufforderungsverknüpfung

Wenn Sie das Dialogfeld Eigenschaften für eines der vorhandenen Verknüpfungen der Developer-Eingabeaufforderung öffnen, sehen Sie das Ziel des Befehls verwendet. Z. B. das Ziel für die **X64 Native Tools-Eingabeaufforderung für Visual Studio 2017** Verknüpfung ist etwas Ähnliches wie in:

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvars64.bat"`

Der Batch-Architektur-spezifische Dateien Satz der *Architektur* -Parameter, und rufen "vcvarsall.bat". Sie können die gleichen zusätzlichen Optionen auf diese Batchdateien übergeben, übergeben Sie zu "vcvarsall.bat" aus, oder rufen Sie einfach "vcvarsall.bat" direkt. Um Parameter für Ihre eigenen Tastenkombination Befehl anzugeben, fügen sie am Ende des Befehls in doppelte Anführungszeichen hinzu. Z. B. um eine Verknüpfung für ARM-Code für UWP auf einer 64-Bit-Plattform zu erstellen, mit der neuesten Windows SDK und das Visual Studio 2017 RTM-Compilertoolset einzurichten, verwenden Sie etwa das Ziel dieses Befehls in Ihrer Verknüpfung:

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvarsall.bat amd64_arm uwp -vcvars_ver=14.10"`

Sie müssen den Pfad entsprechend Ihrem Visual Studio-Installationsverzeichnis anpassen.

## <a name="command-line-tools"></a>Befehlszeilentools

Zum Erstellen eines C/C++-Projekts in der Befehlszeile, bietet Visual Studio mit diesen Befehlszeilentools:

[CL](../build/reference/compiling-a-c-cpp-program.md)<br/>
Verwenden Sie den Compiler (cl.exe), um Quellcodedateien in Apps, Bibliotheken und DLLs zu kompilieren und zu verknüpfen.

[Link](../build/reference/linking.md)<br/>
Verwenden Sie den Linker (link.exe), um kompilierte Objektdateien in Apps und DLLs zu verknüpfen.

[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)<br/>
Verwenden Sie MSBuild (msbuild.exe), um Visual C++-Projekte und Visual Studio-Lösungen zu erstellen. Dies entspricht dem Ausführen der **erstellen** Projekt oder **Projektmappe** Befehl in der Visual Studio-IDE.

[DEVENV](/visualstudio/ide/reference/devenv-command-line-switches)<br/>
Verwenden Sie DEVENV (devenv.exe) in Kombination mit einer Befehlszeilenoption – z. B. **/Build** oder **/Clean**– ausführen bestimmte Buildbefehle ohne Visual Studio-IDE anzuzeigen.

[NMAKE:](../build/nmake-reference.md)<br/>
Verwenden Sie NMAKE (nmake.exe), um Aufgaben zu automatisieren, die Visual C++-Projekte mithilfe eines herkömmlichen Makefiles zu erstellen.

Wenn Sie in der Befehlszeile erstellen, ist der F1-Befehl nicht sofort Hilfe verfügbar. Stattdessen können Sie eine Such-Engine zum Abrufen von Informationen zu Warnungen, Fehlern und Meldungen, oder können Sie die Hilfedateien für die offline. Verwenden die Suche in [docs.microsoft.com](https://docs.microsoft.com/cpp/), geben Sie die Suchzeichenfolge in das Suchfeld am oberen Rand der Seite.

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
Beschreibt, wie Sie ein Eingabeaufforderungsfenster zu starten, in dem die erforderlichen Umgebungsvariablen für Befehlszeilenbuilds festgelegt, die auf X86, X64, und ARM Plattformen mithilfe eines 32-Bit oder 64-Bit-Toolsets.

[NMAKE-Referenz](../build/nmake-reference.md)<br/>
Enthält Links zu Artikeln, in denen das Microsoft Program Maintenance Utility (NMAKE.EXE) beschrieben wird.

[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)<br/>
Enthält Links zu Artikeln, in denen die Verwendung von MSBuild.EXE dargestellt wird.

## <a name="related-sections"></a>Verwandte Abschnitte

[/MD, /MT, /LD (Laufzeitbibliothek verwenden)](../build/reference/md-mt-ld-use-run-time-library.md)<br/>
Beschreibt die Verwendung dieser Compileroptionen für eine Debug- oder Releaselaufzeitbibliothek.

[C/C++-Compiler-Optionen](../build/reference/compiler-options.md)<br/>
Enthält Links zu Artikeln, in denen die C- und C++-Compileroptionen sowie CL.exe erläutert werden.

[Linkeroptionen](../build/reference/linker-options.md)<br/>
Enthält Links zu Artikeln, in denen die Linkeroptionen und LINK.EXE dargestellt werden.

[C/C++-Buildtools](../build/reference/c-cpp-build-tools.md)<br/>
Enthält Links zu den C/C++-Buildtools, die in Visual Studio enthalten sind.

## <a name="see-also"></a>Siehe auch

[Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)