---
title: Verwenden Sie die Microsoft C++ Toolset, das von der Befehlszeile
description: Verwenden Sie die Microsoft C++ Compiler Toolchain (MSVC) auf der Befehlszeile außerhalb der Visual Studio IDE.
ms.custom: conceptual
ms.date: 06/06/2019
helpviewer_keywords:
- command-line builds [C++]
- compiling source code [C++], command line
- builds [C++], command-line
- command line [C++], building from
- command line [C++], compilers
ms.assetid: 7ca9daed-a003-4162-842d-908f79058365
ms.openlocfilehash: b5e9bf266d79ee86cae84535641a52c7c52be391
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821139"
---
# <a name="use-the-microsoft-c-toolset-from-the-command-line"></a>Verwenden Sie die Microsoft C++ Toolset, das von der Befehlszeile

Sie können mithilfe von Tools, die in Visual Studio enthalten sind, C- und C++-Anwendungen auf der Befehlszeile erstellen. Microsoft C++ (MSVC)-Compilertoolset ist auch als eigenständiges Paket zum Herunterladen der [Visual Studio-downloads](https://visualstudio.microsoft.com/downloads/) Seite. Es ist Teil von der **Build-Tools für Visual Studio** Paket. Sie können auswählen, um nur die Tools herunterzuladen, Sie für müssen C++ Entwicklung.

## <a name="how-to-use-the-command-line-tools"></a>Verwenden der Befehlszeilentools

Wenn Sie eine der C++-Workloads im Visual Studio-Installer auswählen, installiert sie das Visual Studio-*Plattformtoolset*. Ein Plattformtoolset hat alle C und C++ -Tools für eine bestimmte Version von Visual Studio. Die Tools umfassen die C /C++ Compiler, Linker, assemblern und anderen Buildtools und entsprechende Bibliotheken. Sie können diese Tools in der Befehlszeile verwenden. Sie werden von der Visual Studio-IDE auch intern verwendet. Es sind separate X86 gehosteten und X64 gehosteten Compiler und Tools zum Erstellen von code für ein X86, x 64, ARM und ARM64-Ziele. Jeder Satz Tools für eine bestimmte Host- und Zielbuildarchitektur ist in einem eigenen Verzeichnis gespeichert.

Um ordnungsgemäß zu funktionieren, müssen für die Tools verschiedene spezifische Umgebungsvariablen festgelegt werden. Diese Variablen werden zum Hinzufügen, dass die Tools, die auf den Pfad, und um festzulegen, Datei Bibliotheksdatei und SDK-Speicherorte enthalten. Um das Festlegen dieser Umgebungsvariablen zu vereinfachen, erstellt der Installer während der Installation angepasste *Befehlsdateien* oder Batchdateien. Sie können eine dieser Befehlsdateien, um einen bestimmten Host und die Zielarchitektur für Build, die Windows SDK-Version und die Plattformtoolset festzulegen ausführen. Der Einfachheit halber erstellt das Installationsprogramm auch Verknüpfungen in Ihrem Menü "Start". Die Tastenkombinationen für starten Developer-Eingabeaufforderung Windows mithilfe der folgenden Befehlsdateien für bestimmte Kombinationen von Hostserver und-Zielserver an. Diese Tastenkombinationen stellen Sie sicher, dass alle erforderlichen Umgebungsvariablen festgelegt und kann verwendet werden.

Die erforderlichen Umgebungsvariablen sind für die Installation und das der Build-Architektur, die Sie auswählen. Sie können auch durch produktaktualisierungen oder -Upgrades geändert werden. Daher sollten Sie eine installierte Befehl oder die Datei für eingabeaufforderungen, statt die Umgebungsvariablen selbst festzulegen. Weitere Informationen finden Sie unter [Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds](setting-the-path-and-environment-variables-for-command-line-builds.md).

Die Toolsets, Befehlsdateien und Tastenkombinationen, die installiert, hängen von der Prozessor Ihres Computers sowie die Optionen, die Sie während der Installation ausgewählt. Die X86-gehosteten Tools und Cross Tools, mit denen X86- und X64 Code zu erstellen, werden immer installiert. Wenn Sie 64-Bit-Windows haben, werden auch die X64-gehosteten Tools und Cross Tools, mit denen X86- und X64 Code zu erstellen installiert. Bei Auswahl der optionalen C++ Tools für universelle Windows-Plattform, und klicken Sie dann auf die X86- und X64 Tools, die ARM und ARM64-Code erstellt auch installiert. Von anderen Workloads werden möglicherweise zusätzliche Tools installiert.

## <a name="developer_command_prompt_shortcuts"></a>Developer-Eingabeaufforderungsverknüpfungen

Die Eingabeaufforderungsverknüpfungen werden in einem versionsspezifischen Visual Studio-Ordner in Ihrem Startmenü gespeichert. Das Folgende ist eine Liste der grundlegenden Eingabeaufforderungsverknüpfungen und der von ihnen unterstützten Buildarchitekturen:

- **Developer-Eingabeaufforderung**: Legt die Umgebung für die Verwendung von x86-nativen 32-Bit-Tools zum Erstellen von x86-nativem 32-Bit-Code fest.
- **x86 Native Tools-Eingabeaufforderung**: Legt die Umgebung für die Verwendung von x86-nativen 32-Bit-Tools zum Erstellen von x86-nativem 32-Bit-Code fest.
- **x64 Native Tools-Eingabeaufforderung**: Legt die Umgebung für die Verwendung von x64-nativen 64-Bit-Tools zum Erstellen von x64-nativem 64-Bit-Code fest.
- **x86_x64 Cross Tools-Eingabeaufforderung**: Legt die Umgebung für die Verwendung von x86-nativen 32-Bit-Tools zum Erstellen von x64-nativem 64-Bit-Code fest.
- **x64_x86 Cross Tools-Eingabeaufforderung**: Legt die Umgebung für die Verwendung von x64-nativen 64-Bit-Tools zum Erstellen von x86-nativem 32-Bit-Code fest.

::: moniker range=">= vs-2019"

Die im Menü "Start" die Namen für Ordner und die Tastenkombination variieren je nach der installierten Version von Visual Studio. Wenn Sie eine festlegen, sie richten sich ebenfalls nach der Installation **Spitzname**. Nehmen wir beispielsweise an Installation von Visual Studio-2019, und Sie ihm einen Spitznamen von *neueste*. Die Developer-eingabeaufforderungsverknüpfung heißt **Entwicklereingabeaufforderung für VS 2019 (aktuellste Version)** , in einem Ordner namens **Visual Studio-2019**.

::: moniker-end
::: moniker range="= vs-2017"

Die im Menü "Start" die Namen für Ordner und die Tastenkombination variieren je nach der installierten Version von Visual Studio. Wenn Sie eine festlegen, sie richten sich ebenfalls nach der Installation **Spitzname**. Nehmen wir beispielsweise an Sie Visual Studio 2017 installiert, und Sie ihm einen Spitznamen von *neueste*. Die Developer-eingabeaufforderungsverknüpfung heißt **Developer-Eingabeaufforderung für Visual Studio 2017 (aktuellste Version)** , in einem Ordner namens **Visual Studio 2017**.

::: moniker-end
::: moniker range="< vs-2017"

Die im Menü "Start" die Namen für Ordner und die Tastenkombination variieren je nach der installierten Version von Visual Studio. Nehmen wir beispielsweise an, dass Sie Visual Studio 2015 installiert. Die Developer-eingabeaufforderungsverknüpfung heißt **Developer-Eingabeaufforderung für VS 2015**.

::: moniker-end

## <a name="developer_command_prompt"></a> So öffnen Sie ein Developer-Eingabeaufforderungsfenster

1. Öffnen Sie auf dem Desktop das Windows-**Startmenü**, und scrollen Sie dann nach unten, um den Ordner für Ihre Visual Studio-Version zu finden und zu öffnen, beispielsweise **Visual Studio 2019**.

1. Wählen Sie im Ordner die **Developer-Eingabeaufforderung** für Ihre Version von Visual Studio aus. Diese Verknüpfung startet ein Developer-Eingabeaufforderungsfenster, das die Standardbuildarchitektur mit x86-nativen 32-Bit-Tools zum Erstellen von x86-nativem 32-Bit-Code verwendet. Falls Sie eine andere als die Standardbuildarchitektur vorziehen, wählen Sie eine der Eingabeaufforderungen mit nativen oder kreuzkompatiblen Tools aus, um die Host- und die Zielarchitektur anzugeben.

Geben Sie für eine noch schnellere Möglichkeit, Developer-Eingabeaufforderung zu öffnen, *Developer-Eingabeaufforderung* im Feld Suche auf Desktopcomputern. Wählen Sie dann das gewünschte Ergebnis.

## <a name="developer_command_file_locations"></a> Speicherorte von Developer-Befehlsdateien

Wenn Sie die Buildumgebung in ein vorhandenes Fenster der Eingabeaufforderung festlegen möchten, können Sie eine der Befehlsdateien vom Installationsprogramm erstellte. Es wird empfohlen, dass Sie die Umgebung in einem neuen Fenster der Eingabeaufforderung festlegen. Nicht empfohlen höhere Switch-Umgebungen im gleichen Befehlsfenster.

::: moniker range=">= vs-2019"

Speicherort der Befehl hängt ab, auf die Version von Visual Studio, die Sie installiert haben, und klicken Sie auf Optionen, die Sie während der Installation vorgenommen. Für Visual Studio-2019, der der Speicherort der Standardinstallation auf einem 64-Bit-System ist \\Programmdateien (x86)\\Microsoft Visual Studio\\2019\\*Edition*. *Edition* möglicherweise Community, Professional, Enterprise, BuildTools oder einen anderen Kontonamen, die Sie angegeben haben.

::: moniker-end
::: moniker range="= vs-2017"

Speicherort der Befehl hängt ab, auf die Version von Visual Studio, die Sie installiert haben, und klicken Sie auf Optionen, die Sie während der Installation vorgenommen. Für Visual Studio 2017, der der Speicherort der Standardinstallation auf einem 64-Bit-System ist \\Programmdateien (x86)\\Microsoft Visual Studio\\2017\\*Edition*. *Edition* möglicherweise Community, Professional, Enterprise, BuildTools oder einen anderen Kontonamen, die Sie angegeben haben.

::: moniker-end
::: moniker range="< vs-2017"

Speicherort der Befehl hängt davon ab, die Visual Studio-Version und das Installationsverzeichnis. Für Visual Studio 2015, der der Installationspfad lautet \\Programmdateien (x86)\\Microsoft 14.0 für Visual Studio.

::: moniker-end

Die primäre Developer-Eingabeaufforderung Befehlsdatei VsDevCmd.bat, befindet sich in der Common7\\Tools-Unterverzeichnis. Wenn keine Parameter angegeben werden, richtet es die Umgebung für die Native X86 Tools zu verwenden, um 32-Bit-X86 erstellen Code.

::: moniker range=">= vs-2017"

Weitere Befehlsdateien sind zum Einrichten von bestimmten Build-Architekturen verfügbar. Die verfügbaren Befehlsdateien hängen davon ab, die Visual Studio-arbeitsauslastungen und den Optionen, die Sie installiert haben. In Visual Studio 2017 und Visual Studio-2019, Sie finden sie in der VC\\zusätzliche\\Unterverzeichnis erstellen.

::: moniker-end
::: moniker range="< vs-2017"

Weitere Befehlsdateien sind zum Einrichten von bestimmten Build-Architekturen verfügbar. Die verfügbaren Befehlsdateien hängen davon ab, die Visual Studio-arbeitsauslastungen und den Optionen, die Sie installiert haben. In Visual Studio 2015 können sie in der VC, VC befinden\\Bin oder VC\\Bin\\*Architektur* Unterverzeichnissen, in denen *Architektur* ist eine der systemeigenen oder Cross-Compiler-Optionen.

::: moniker-end

Diese Befehlsdateien legen Standardparameter fest und rufen „VsDevCmd.bat“ auf, um die angegebene Buildarchitekturumgebung einzurichten. Eine typische Installation kann etwa diese Befehlsdateien enthalten:

|Befehlsdatei|Host- und Zielarchitekturen|
|---|---|
|**vcvars32.bat**| Die x86-nativen 32-Bit-Tools werden zum Erstellen von 32-Bit-x86-Code verwendet.|
|**vcvars64.bat**| Die x64-nativen 64-Bit-Tools werden zum Erstellen von 64-Bit-x64-Code verwendet.|
|**vcvarsx86_amd64.bat**| Die x86-nativen 32-Bit kreuzkompatiblen Tools werden zum Erstellen von 64-Bit-x64-Code verwendet.|
|**vcvarsamd64_x86.bat**| Die x64-nativen 64-Bit kreuzkompatiblen Tools werden zum Erstellen von 32-Bit-x86-Code verwendet.|
|**vcvarsx86_arm.bat**| Die x86-nativen 32-Bit kreuzkompatiblen Tools werden zum Erstellen ARM-Code verwendet.|
|**vcvarsamd64_arm.bat**| Die x64-nativen 64-Bit kreuzkompatiblen Tools werden zum Erstellen ARM-Code verwendet.|
|**vcvarsall.bat**| Verwenden Sie Parameter, um die Hostserver und-Zielserver Architekturen, die Windows-SDK und Plattformoptionen anzugeben. Um eine Liste der unterstützten Optionen anzuzeigen, rufen Sie diesen Befehl mit dem Parameter **/help** auf.|

> [!CAUTION]
> Die vcvarsall.bat-Datei und andere Visual Studio-Befehlsdateien können sich von Computer zu Computer unterscheiden. Ersetzen Sie eine fehlender oder beschädigte vcvarsall.bat-Datei nicht durch eine Datei von einem anderen Computer. Führen Sie den Visual Studio-Installer erneut aus, um die fehlende Datei zu ersetzen.
>
> Die vcvarsall.bat-Datei ist auch von Version zu Version unterschiedlich. Falls die aktuelle Version von Visual Studio auf einem Computer installiert ist, der außerdem über eine frühere Version von Visual Studio verfügt, sollten Sie nicht „vcvarsall.bat“ oder eine andere Visual Studio-Befehlsdatei aus einer anderen Version im selben Eingabeaufforderungsfenster ausführen.

## <a name="use-the-developer-tools-in-an-existing-command-window"></a>Verwenden der Entwicklertools in einem vorhandenen Befehlsfenster

Die einfachste Möglichkeit, eine bestimmte Buildarchitektur in einem vorhandenen Befehlsfenster anzugeben, ist die Verwendung der Datei „vcvarsall.bat“. Verwenden Sie "vcvarsall.bat", um die Umgebungsvariablen so konfigurieren Sie die Befehlszeile für die systeminterne Kompilierung für 32-Bit oder 64-Bit festgelegt. Argumente können Sie angeben, um X86, x 64, ARM, die Cross-Kompilierung oder ARM64-Prozessoren. Sie können Microsoft Store, universelle Windows-Plattform oder Windows-Desktop-Plattformen abzielen. Sie können sogar Geben Sie die Windows SDK verwenden, und wählen Sie die Plattform Toolset-Version.

Bei der ohne Argumente verwendet werden, konfiguriert vcvarsall.bat die Umgebungsvariablen, um die aktuellen X86 Native-Compiler für 32-Bit-Windows-Desktop-Ziele zu verwenden. Sie können die Argumente zum Konfigurieren der Umgebung zur Verwendung eines der systemeigenen oder cross Compilertools hinzufügen. "vcvarsall.bat" wird eine Fehlermeldung angezeigt, wenn Sie eine Konfiguration angeben, die nicht installiert ist oder auf Ihrem Computer verfügbar.

### <a name="vcvarsall-syntax"></a>vcvarsall-Syntax

> **vcvarsall.bat** [*architecture*] [*platform_type*] [*winsdk_version*] [ **-vcvars_ver=** _vcversion_]

*architecture*<br/>
Dieses optionale Argument gibt die zu verwendende Host- und Zielarchitektur an. Wenn *Architektur* nicht angegeben ist, wird die Standard-Buildumgebung verwendet. Diese Argumente werden unterstützt:

|*architecture*|Compiler|Hostcomputerarchitektur|Buildausgabearchitektur (Zielarchitektur)|
|----------------------------|--------------|----------------------------------|-------------------------------|
|**x86**|x86-32-Bit systemeigen|x86, x64|x86|
|**x86\_amd64** oder **x86\_x64**|x64 kreuzkompatibel auf x86|x86, x64|x64|
|**x86_arm**|ARM auf x86-Cross|x86, x64|ARM|
|**x86_arm64**|ARM64 kreuzkompatibel auf x86|x86, x64|ARM64|
|**amd64** oder **x64**|x64 64-Bit nativ|x64|x64|
|**amd64\_x86** oder **x64\_x86**|x86 kreuzkompatibel auf x64|x64|x86|
|**amd64\_arm** oder **x64\_arm**|ARM kreuzkompatibel auf x64|x64|ARM|
|**amd64\_arm64** oder **x64\_arm64**|ARM64 kreuzkompatibel auf x64|x64|ARM64|

*platform_type*<br/>
Dieses optionale Argument ermöglicht Ihnen die Angabe von **store** oder **uwp** als Plattformtyp. Standardmäßig ist die Umgebung auf das Erstellen von Desktop- oder Konsolen-Apps festgelegt.

*winsdk_version*<br/>
Gibt optional die Version des zu verwendenden Windows SDK an. Standardmäßig wird das neueste installierte Windows SDK verwendet. Um die Windows SDK-Version anzugeben, können Sie eine vollständige Windows 10 SDK-Nummer, wie etwa **10.0.10240.0**, verwenden oder **8.1** angeben, wenn Sie das Windows 8.1 SDK verwenden möchten.

*vcversion*<br/>
Gibt optional das zu verwendende Visual Studio-Compilertoolset an. Standardmäßig ist die Umgebung auf die Verwendung des aktuellen Visual Studio-Compilertoolsets festgelegt.

::: moniker range=">= vs-2019"

Verwendung **-Vcvars_ver = 14.2 x .yyyyy** an eine bestimmte Version des Visual Studio-2019 Compiler-Toolsets.

Verwendung **-Vcvars_ver = 14.16** die neueste Version von Visual Studio 2017-Compiler-Toolset an.

::: moniker-end
::: moniker range="= vs-2017"

Verwendung **-Vcvars_ver = 14.16** die neueste Version von Visual Studio 2017-Compiler-Toolset an.

Verwendung **-Vcvars_ver = 14.1 x .yyyyy** an eine bestimmte Version von Visual Studio 2017-Compiler-Toolset.

::: moniker-end

Verwendung **-Vcvars_ver = 14.0** an das Visual Studio 2015-Compilertoolset.

<a name="vcvarsall"></a>
#### <a name="to-set-up-the-build-environment-in-an-existing-command-prompt-window"></a>Einrichten der Buildumgebung in einem vorhandenen Eingabeaufforderungsfenster

1. Verwenden Sie an der Eingabeaufforderung den CD-Befehl, um in das Visual Studio-Installationsverzeichnis zu wechseln. Verwenden Sie dann erneut CD, um in das Unterverzeichnis zu wechseln, das die konfigurationsspezifischen Befehlsdateien enthält. Verwenden Sie für Visual Studio-2019 und Visual Studio 2017 die *VC\\zusätzliche\\erstellen* Unterverzeichnis. Verwenden Sie für Visual Studio 2015 die *VC* Unterverzeichnis.

1. Geben Sie den Befehl für Ihre bevorzugte Entwicklerumgebung ein. Verwenden Sie zum Erstellen von ARM-Code für UWP auf einer 64-Bit-Plattform, mit der neuesten Windows SDK und Visual Studio-Compilertoolset, z. B. folgender Befehlszeile:

   `vcvarsall.bat amd64_arm uwp`

## <a name="create-your-own-command-prompt-shortcut"></a>Erstellen einer eigenen Eingabeaufforderungsverknüpfung

::: moniker range=">= vs-2019"

Öffnen Sie das Dialogfeld Eigenschaften für eine Developer-eingabeaufforderungsverknüpfung, die das Ziel des Befehls verwendet, finden Sie unter. Beispielsweise ist das Ziel für die Verknüpfung **x64 Native Tools-Eingabeaufforderung für VS 2019** ähnlich wie dies hier:

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvars64.bat"`

::: moniker-end
::: moniker range="= vs-2017"

Öffnen Sie das Dialogfeld Eigenschaften für eine Developer-eingabeaufforderungsverknüpfung, die das Ziel des Befehls verwendet, finden Sie unter. Z. B. das Ziel für die **X64 Native Tools-Eingabeaufforderung für Visual Studio 2017** Verknüpfung ist etwas Ähnliches wie in:

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvars64.bat"`

::: moniker-end
::: moniker range="< vs-2017"

Öffnen Sie das Dialogfeld Eigenschaften für eine Developer-eingabeaufforderungsverknüpfung, die das Ziel des Befehls verwendet, finden Sie unter. Z. B. das Ziel für die **VS2015 X64 Native Tools-Eingabeaufforderung** Verknüpfung ist etwas Ähnliches wie in:

`%comspec% /k ""C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\vcvarsall.bat"" amd64`

::: moniker-end

Die architekturspezifischen Batchdateien legen den *architecture*-Parameter fest und rufen „vcvarsall.bat“ auf. Sie können die gleichen Optionen an diese Batchdateien übergeben, übergeben Sie zu "vcvarsall.bat" aus, oder rufen Sie einfach "vcvarsall.bat" direkt. Um Parameter für Ihre eigene Befehlsverknüpfung anzugeben, fügen Sie sie am Ende des Befehls in doppelten Anführungszeichen hinzu. Hier ist z. B. eine Verknüpfung zum Erstellen von ARM-Code für UWP auf einer 64-Bit-Plattform, die das aktuelle Windows SDK verwenden. Um eine frühere Compiler-Toolset zu verwenden, geben Sie die Versionsnummer. Verwenden Sie in Ihrer Verknüpfung etwas in der Art dieses Befehlsziels:

::: moniker range=">= vs-2019"

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvarsall.bat amd64_arm uwp -vcvars_ver=14.16"`

::: moniker-end
::: moniker range="= vs-2017"

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\VC\Auxiliary\Build\vcvarsall.bat amd64_arm uwp -vcvars_ver=14.0"`

::: moniker-end
::: moniker range="< vs-2017"

`%comspec% /k ""C:\Program Files (x86)\Microsoft Visual Studio 14.0\VC\vcvarsall.bat"" amd64 -vcvars_ver=12.0`

::: moniker-end

Passen Sie den Pfad entsprechend Ihrem Visual Studio-Installationsverzeichnis. Die vcvarsall.bat-Datei enthält zusätzliche Informationen über bestimmte Versionsnummern.

## <a name="command-line-tools"></a>Befehlszeilentools

Erstellen ein C /C++ Projekt an einer Eingabeaufforderung, Visual Studio bietet diese Befehlszeilentools:

[CL](reference/compiling-a-c-cpp-program.md)<br/>
Verwenden Sie den Compiler (cl.exe), um Quellcodedateien in Apps, Bibliotheken und DLLs zu kompilieren und zu verknüpfen.

[Link](reference/linking.md)<br/>
Verwenden Sie den Linker (link.exe), um kompilierte Objektdateien in Apps und DLLs zu verknüpfen.

[MSBuild](msbuild-visual-cpp.md)<br/>
Verwenden Sie MSBuild (msbuild.exe) und eine Projektdatei (.vcxproj), um einen Build zu konfigurieren und das Toolset indirekt aufzurufen. Dies ist äquivalent zum Ausführen der **erstellen** Projekt oder **Projektmappe** Befehl in der Visual Studio-IDE. Ausführen von MSBuild über die Befehlszeile ist ein erweitertes Szenario, und nicht allgemein empfohlen.

[DEVENV](/visualstudio/ide/reference/devenv-command-line-switches)<br/>
Verwenden Sie DEVENV (devenv.exe) in Kombination mit einer Befehlszeilenoption wie z. B. **/Build** oder **/Clean** auszuführende bestimmte Buildbefehle ohne Visual Studio-IDE anzuzeigen. Im Allgemeinen wird DEVENV bevorzugt MSBuild direkt, da lassen Sie Visual Studio, die die Komplexität von MSBuild zu behandeln.

[NMAKE](reference/nmake-reference.md)<br/>
Verwenden Sie NMAKE (nmake.exe) unter Windows, um C++-Projekte auf der Grundlage eines traditionellen Makefiles zu erstellen.

Wenn Sie in der Befehlszeile erstellen, nicht der F1-Befehl sofort Hilfe. Stattdessen können Sie eine Suchmaschine verwenden, um Informationen über Warnungen, Fehler und Meldungen abzurufen, oder Sie können die Offline-Hilfedateien verwenden. Verwenden die Suche in [docs.microsoft.com](https://docs.microsoft.com/cpp/), verwenden Sie das Suchfeld am oberen Rand der Seite.

## <a name="in-this-section"></a>In diesem Abschnitt

Dieser Artikel veranschaulicht, wie zum Erstellen von apps in der Befehlszeile angegeben und beschrieben, wie Sie die Befehlszeilen-Buildumgebung anpassen. Einige zeigen, wie verwenden die 64-Bit-Toolsets und X86, x 64, ARM, Ziel und ARM64-Plattformen. Zudem werden die Verwendung des Befehlszeilen-Buildtools MSBuild und NMAKE beschrieben.

[Exemplarische Vorgehensweise: Kompilieren eines nativen C++-Programms in der Befehlszeile](walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)<br/>
Bietet ein Beispiel, das zeigt, wie zum Erstellen und Kompilieren einer C++ -Programms in der Befehlszeile aus.

[Exemplarische Vorgehensweise: Compile a C Program on the Command Line (Exemplarische Vorgehensweise: Kompilieren eines C-Programms in der Befehlszeile)](walkthrough-compile-a-c-program-on-the-command-line.md)<br/>
Beschreibt, wie Sie ein in der Programmiersprache C geschriebenes Programm kompilieren.

[Exemplarische Vorgehensweise: Kompilieren eines C++- bzw. CLI-Programms in der Befehlszeile](walkthrough-compiling-a-cpp-cli-program-on-the-command-line.md)<br/>
Beschreibt, wie Sie ein C++-/CLI-Programm erstellen und kompilieren, das .NET Framework verwendet.

[Exemplarische Vorgehensweise: Kompilieren eines C++- bzw.-CX-Programms in der Befehlszeile](walkthrough-compiling-a-cpp-cx-program-on-the-command-line.md)<br/>
Beschreibt, wie Sie ein C++-/CX-Programm erstellen und kompilieren, das die Windows Runtime verwendet.

[Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds](setting-the-path-and-environment-variables-for-command-line-builds.md)<br/>
Festlegen von Umgebungsvariablen für eine 32-Bit oder 64-Bit-Toolset für X86, X64, ARM, verwenden und ARM64-Plattformen.

[NMAKE-Referenz](reference/nmake-reference.md)<br/>
Enthält Links zu Artikeln, in denen das Microsoft Program Maintenance Utility (NMAKE.EXE) beschrieben wird.

[MSBuild on the Command Line – C++ (C++: MSBuild in der Befehlszeile)](msbuild-visual-cpp.md)<br/>
Enthält Links zu Artikeln, in denen die Verwendung von msbuild.exe auf der Befehlszeile dargestellt wird.

## <a name="related-sections"></a>Verwandte Abschnitte

[/MD, /MT, /LD (Laufzeitbibliothek verwenden)](reference/md-mt-ld-use-run-time-library.md)<br/>
Beschreibt die Verwendung dieser Compileroptionen für eine Debug- oder Releaselaufzeitbibliothek.

[C/C++-Compileroptionen](reference/compiler-options.md)<br/>
Enthält Links zu Artikeln, in denen die C- und C++-Compileroptionen sowie CL.exe erläutert werden.

[MSVC-Linkeroptionen](reference/linker-options.md)<br/>
Enthält Links zu Artikeln, in denen die Linkeroptionen und LINK.EXE dargestellt werden.

[Zusätzliche MSVC-Buildtools](reference/c-cpp-build-tools.md)<br/>
Enthält Links zu den C-/C++-Buildtools, die in Visual Studio enthalten sind.

## <a name="see-also"></a>Siehe auch

[Projekte und Buildsysteme](projects-and-build-systems-cpp.md)
