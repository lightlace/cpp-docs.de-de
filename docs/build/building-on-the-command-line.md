---
title: Verwenden des MSVC-Toolsets auf der Befehlszeile – Visual Studio
description: Verwenden Sie die Microsoft C++ Compiler Toolchain (MSVC) auf der Befehlszeile außerhalb der Visual Studio IDE.
ms.custom: conceptual
ms.date: 05/16/2019
helpviewer_keywords:
- command-line builds [C++]
- compiling source code [C++], command line
- builds [C++], command-line
- command line [C++], building from
- command line [C++], compilers
ms.assetid: 7ca9daed-a003-4162-842d-908f79058365
ms.openlocfilehash: 97626455ace0d3ad47b9011594e82c144d7ea27d
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837117"
---
# <a name="use-the-msvc-toolset-from-the-command-line"></a>Verwenden des MSVC-Toolsets auf der Befehlszeile

Sie können mithilfe von Tools, die in Visual Studio enthalten sind, C- und C++-Anwendungen auf der Befehlszeile erstellen. Sie können das Compilertoolset aber auch als eigenständiges Paket von der Seite [Visual Studio-Downloads](https://visualstudio.microsoft.com/downloads/) herunterladen. Es ist Teil des Pakets **Buildtools für Visual Studio**; Sie können sich entscheiden, nur die für die C++-Entwicklung benötigten Tools herunterzuladen.

## <a name="how-to-use-the-command-line-tools"></a>Verwenden der Befehlszeilentools

Wenn Sie eine der C++-Workloads im Visual Studio-Installer auswählen, installiert sie das Visual Studio-*Plattformtoolset*. Ein Plattformtoolset weist alle C- und C++-Tools für eine bestimmte Visual Studio-Version auf, einschließlich der C/C++-Compiler, -Linker, -Assembler und sonstigen Buildtools sowie die entsprechenden Bibliotheken. Sie können alle diese Tools auf der Befehlszeile verwenden, und sie werden auch intern von der Visual Studio-IDE verwendet. Es gibt separate Compiler und Tools für das Hosten auf x86- und x64-Architekturen, um Code für x86-, x64-, ARM- und ARM64-Zielumgebungen zu erstellen. Jeder Satz Tools für eine bestimmte Host- und Zielbuildarchitektur ist in einem eigenen Verzeichnis gespeichert.

Welche Compilertoolsets installiert werden, hängt vom Prozessor Ihres Computers und den während der Installation aktivierten Optionen ab. Als Mindestausstattung werden die auf x86 gehosteten 32-Bit-Tools zur Erstellung von x86-nativem 32-Bit-Code sowie die kreuzkompatiblen Tools zur Erstellung von x64-nativem 64-Bit-Code installiert. Wenn Sie über 64-Bit-Windows verfügen, werden außerdem die auf x64 gehosteten 64-Bit-Tools zur Erstellung von nativem 64-Bit-Code und kreuzkompatible Tools zur Erstellung von nativem 32-Bit-Code installiert. Wenn Sie sich zur Installation der optionalen C++-Tools für die Universelle Windows-Plattform entschließen, werden die nativen 32-Bit- und 64-Bit-Tools zur Erstellung von ARM-Code ebenfalls installiert. Von anderen Workloads werden möglicherweise zusätzliche Tools installiert.

## <a name="environment-variables-and-developer-command-prompts"></a>Umgebungsvariablen und Developer-Eingabeaufforderungen

Um ordnungsgemäß zu funktionieren, müssen für die Tools verschiedene spezifische Umgebungsvariablen festgelegt werden. Diese werden verwendet, um sie dem Pfad hinzuzufügen und die Speicherorte von Includedateien, Bibliotheksdateien und SDKs festzulegen. Um das Festlegen dieser Umgebungsvariablen zu vereinfachen, erstellt der Installer während der Installation angepasste *Befehlsdateien* oder Batchdateien. Sie können eine dieser Befehlsdateien in einem Eingabeaufforderungsfenster ausführen, um eine bestimmte Host- und Zielbuildarchitektur, eine Windows SDK-Version, eine Zielplattform und ein Plattformtoolset festzulegen. Der Einfachheit halber erstellt der Installer darüber hinaus Verknüpfungen in Ihrem Startmenü, die Developer-Eingabeaufforderungsfenster mithilfe dieser Befehlsdateien starten, so dass alle erforderlichen Umgebungsvariablen festgelegt und zur Verwendung bereit sind.

Die erforderlichen Umgebungsvariablen sind für Ihre Installation und für die von Ihnen gewählte Buildarchitektur spezifisch und können sich bei Updates oder Upgrades des Produkts ändern. Daher empfehlen wir dringend, eine der installierten Eingabeaufforderungsverknüpfungen oder Befehlsdateien zu verwenden, statt die Umgebungsvariablen in Windows selbst festzulegen. Weitere Informationen finden Sie unter [Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds](setting-the-path-and-environment-variables-for-command-line-builds.md).

## <a name="developer_command_prompt_shortcuts"></a>Developer-Eingabeaufforderungsverknüpfungen

Die Eingabeaufforderungsverknüpfungen werden in einem versionsspezifischen Visual Studio-Ordner in Ihrem Startmenü gespeichert. Das Folgende ist eine Liste der grundlegenden Eingabeaufforderungsverknüpfungen und der von ihnen unterstützten Buildarchitekturen:

- **Developer-Eingabeaufforderung**: Legt die Umgebung für die Verwendung von x86-nativen 32-Bit-Tools zum Erstellen von x86-nativem 32-Bit-Code fest.
- **x86 Native Tools-Eingabeaufforderung**: Legt die Umgebung für die Verwendung von x86-nativen 32-Bit-Tools zum Erstellen von x86-nativem 32-Bit-Code fest.
- **x64 Native Tools-Eingabeaufforderung**: Legt die Umgebung für die Verwendung von x64-nativen 64-Bit-Tools zum Erstellen von x64-nativem 64-Bit-Code fest.
- **x86_x64 Cross Tools-Eingabeaufforderung**: Legt die Umgebung für die Verwendung von x86-nativen 32-Bit-Tools zum Erstellen von x64-nativem 64-Bit-Code fest.
- **x64_x86 Cross Tools-Eingabeaufforderung**: Legt die Umgebung für die Verwendung von x64-nativen 64-Bit-Tools zum Erstellen von x86-nativem 32-Bit-Code fest.

Die tatsächlichen Namen von Startmenüordner und Verknüpfungen können je nach der installierten Visual Studio-Version und dem Spitznamen der Installation abweichen, sollten Sie einen festlegen. Wenn Sie beispielsweise Visual Studio 2019 installiert und der Installation den Spitznamen *Vorschau* gegeben haben, lautet die Verknüpfung für die Developer-Eingabeaufforderung **Developer-Eingabeaufforderung für VS 2019** und befindet sich in einem Ordner mit dem Namen **Visual Studio 2019**.

## <a name="developer_command_prompt"></a> So öffnen Sie ein Developer-Eingabeaufforderungsfenster

1. Öffnen Sie auf dem Desktop das Windows-**Startmenü**, und scrollen Sie dann nach unten, um den Ordner für Ihre Visual Studio-Version zu finden und zu öffnen, beispielsweise **Visual Studio 2019**. In einigen früheren Versionen von Visual Studio befinden sich die Verknüpfungen in einem Unterordner namens **Visual Studio-Tools**.

1. Wählen Sie im Ordner die **Developer-Eingabeaufforderung** für Ihre Version von Visual Studio aus. Diese Verknüpfung startet ein Developer-Eingabeaufforderungsfenster, das die Standardbuildarchitektur mit x86-nativen 32-Bit-Tools zum Erstellen von x86-nativem 32-Bit-Code verwendet. Falls Sie eine andere als die Standardbuildarchitektur vorziehen, wählen Sie eine der Eingabeaufforderungen mit nativen oder kreuzkompatiblen Tools aus, um die Host- und die Zielarchitektur anzugeben.

Sogar noch schneller lässt sich ein Developer-Eingabeaufforderungsfenster öffnen, wenn Sie *Developer-Eingabeaufforderung* in das Suchfeld auf dem Desktop eingeben und dann das gewünschte Ergebnis auswählen.

## <a name="developer_command_file_locations"></a> Speicherorte von Developer-Befehlsdateien

Wenn Sie es vorziehen, die Buildarchitektur in einem vorhandenen Eingabeaufforderungsfenster festzulegen, können Sie eine der Befehlsdateien (Batchdateien), die vom Installer erstellt wurden, zum Festlegen der erforderlichen Umgebung verwenden. Wir empfehlen dieses Vorgehen nur in einem neuen Eingabeaufforderungsfenster. Sie sollten die Umgebung nicht später in einem vorhandenen Eingabeaufforderungsfenster wechseln. Der Speicherort dieser Datei hängt von der installierten Version von Visual Studio und von Ihren Entscheidungen zu Speicherort und Benennung während der Installation ab. Für Visual Studio 2019 ist der typische Installationsspeicherort auf einem 64-Bit-Computer in „\Programme (x86)\Microsoft Visual Studio\2019\*Edition*“, wobei es sich bei *Edition* um Community, Professional, Enterprise, BuildTools oder einen anderen von Ihnen angegebenen Namen handeln kann. Der Speicherort von Visual Studio 2017 ist ähnlich. Für Visual Studio 2015 ist der typische Installationsspeicherort in „\Programme (x86)\Microsoft Visual Studio 14.0“.

Die primäre Befehlsdatei der Developer-Eingabeaufforderung, „VsDevCmd.bat“, befindet sich im Unterverzeichnis „Common7\Tools“ des Installationsverzeichnisses. Wenn keine Parameter angegeben werden, legt dies die Umgebung und die Host- und Zielbuildarchitektur auf die Verwendung der x86-nativen 32-Bit-Tools zum Erstellen von 32-Bit-x86-Code fest.

Es stehen weitere Befehlsdateien zur Verfügung, um bestimmte Buildarchitekturen einzurichten, abhängig von Ihrer Prozessorarchitektur und den installierten Visual Studio-Workloads und -Optionen. In Visual Studio 2017 und Visual Studio 2019 befinden sich diese im Unterverzeichnis „VC\Auxiliary\Build“ des Visual Studio-Installationsverzeichnisses. In Visual Studio 2015 finden Sie die Dateien in den „VC“, „VC\bin“ oder „VC\bin\\*architectures*“ des Installationsverzeichnisses, wobei *architectures* für eine der nativen oder kreuzkompatiblen Compileroptionen steht. Diese Befehlsdateien legen Standardparameter fest und rufen „VsDevCmd.bat“ auf, um die angegebene Buildarchitekturumgebung einzurichten. Eine typische Installation kann etwa diese Befehlsdateien enthalten:

|Befehlsdatei|Host- und Zielarchitekturen|
|---|---|
|**vcvars32.bat**| Die x86-nativen 32-Bit-Tools werden zum Erstellen von 32-Bit-x86-Code verwendet.|
|**vcvars64.bat**| Die x64-nativen 64-Bit-Tools werden zum Erstellen von 64-Bit-x64-Code verwendet.|
|**vcvarsx86_amd64.bat**| Die x86-nativen 32-Bit kreuzkompatiblen Tools werden zum Erstellen von 64-Bit-x64-Code verwendet.|
|**vcvarsamd64_x86.bat**| Die x64-nativen 64-Bit kreuzkompatiblen Tools werden zum Erstellen von 32-Bit-x86-Code verwendet.|
|**vcvarsx86_arm.bat**| Die x86-nativen 32-Bit kreuzkompatiblen Tools werden zum Erstellen ARM-Code verwendet.|
|**vcvarsamd64_arm.bat**| Die x64-nativen 64-Bit kreuzkompatiblen Tools werden zum Erstellen ARM-Code verwendet.|
|**vcvarsall.bat**| Verwenden Sie Parameter zum Angeben der Host- und Zielarchitekturen sowie der Optionen für SDK und Plattform. Um eine Liste der unterstützten Optionen anzuzeigen, rufen Sie diesen Befehl mit dem Parameter **/help** auf.|

> [!CAUTION]
> Die vcvarsall.bat-Datei und andere Visual Studio-Befehlsdateien können sich von Computer zu Computer unterscheiden. Ersetzen Sie eine fehlender oder beschädigte vcvarsall.bat-Datei nicht durch eine Datei von einem anderen Computer. Führen Sie den Visual Studio-Installer erneut aus, um die fehlende Datei zu ersetzen.
>
> Die vcvarsall.bat-Datei ist auch von Version zu Version unterschiedlich. Falls die aktuelle Version von Visual Studio auf einem Computer installiert ist, der außerdem über eine frühere Version von Visual Studio verfügt, sollten Sie nicht „vcvarsall.bat“ oder eine andere Visual Studio-Befehlsdatei aus einer anderen Version im selben Eingabeaufforderungsfenster ausführen.

## <a name="use-the-developer-tools-in-an-existing-command-window"></a>Verwenden der Entwicklertools in einem vorhandenen Befehlsfenster

Die einfachste Möglichkeit, eine bestimmte Buildarchitektur in einem vorhandenen Befehlsfenster anzugeben, ist die Verwendung der Datei „vcvarsall.bat“. Sie können „vcvarsall.bat“ zum Festlegen von Umgebungsvariablen zum Konfigurieren der Befehlszeile für native 32-Bit- oder 64-Bit-Kompilierung oder für Kreuzkompilierung für x86-, x64- oder ARM-Prozessoren verwenden; um die Zielplattformen Microsoft Store, Universelle Windows-Plattform oder Windows Desktop-Plattform festzulegen; um anzugeben, welches Windows SDK verwendet werden soll; und um die Plattformtoolsetversion anzugeben. Wenn keine Argumente bereitgestellt werden, konfiguriert die „vcvarsall.bat“ die Umgebungsvariablen für die Verwendung des aktuellen nativen 32-Bit-Compilers für x86-Windows Desktop-Ziele. Sie können damit aber auch alle anderen nativen oder kreuzkompatiblen Compilertools konfigurieren. Wenn Sie eine Compilerkonfiguration angeben, die nicht installiert oder nicht auf der Buildcomputerarchitektur verfügbar ist, wird eine Fehlermeldung angezeigt.

### <a name="vcvarsall-syntax"></a>vcvarsall-Syntax

> **vcvarsall.bat** [*architecture*] [*platform_type*] [*winsdk_version*] [ **-vcvars_ver=**_vcversion_]

*architecture*<br/>
Dieses optionale Argument gibt die zu verwendende Host- und Zielarchitektur an. Wenn *architecture* nicht angegeben wird, wird die Standardbuildumgebung verwendet. Diese Argumente werden unterstützt:

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
Gibt optional das zu verwendende Visual Studio-Compilertoolset an. Standardmäßig ist die Umgebung auf die Verwendung des aktuellen Visual Studio-Compilertoolsets festgelegt. Verwenden Sie **-vcvars_ver=14.0**, um das Visual Studio 2015-Compilertoolset, oder **-vcvars_ver=15.0**, um das Visual Studio 2017-Compilertoolset anzugeben.

<a name="vcvarsall"></a>
#### <a name="to-set-up-the-build-environment-in-an-existing-command-prompt-window"></a>Einrichten der Buildumgebung in einem vorhandenen Eingabeaufforderungsfenster

1. Verwenden Sie an der Eingabeaufforderung den CD-Befehl, um in das Visual Studio-Installationsverzeichnis zu wechseln. Verwenden Sie dann erneut CD, um in das Unterverzeichnis zu wechseln, das die konfigurationsspezifischen Befehlsdateien enthält. Für Visual Studio 2017 und Visual Studio 2019 ist dies das Unterverzeichnis „VC\Auxiliary\Build“. Verwenden Sie für Visual Studio 2015 das Unterverzeichnis „VC“.

1. Geben Sie den Befehl für Ihre bevorzugte Entwicklerumgebung ein. Um beispielsweise ARM-Code für UWP auf einer 64-Bit-Plattform mithilfe des aktuellen Windows SDK und des Visual Studio 2019-Compilertoolsets zu erstellen, verwenden Sie diese Befehlszeile:

   `vcvarsall.bat amd64_arm uwp`

## <a name="create-your-own-command-prompt-shortcut"></a>Erstellen einer eigenen Eingabeaufforderungsverknüpfung

Wenn Sie das Dialogfeld „Eigenschaften“ für eine der vorhandenen Developer-Eingabeaufforderungsverknüpfungen öffnen, können Sie das verwendete Befehlsziel sehen. Beispielsweise ist das Ziel für die Verknüpfung **x64 Native Tools-Eingabeaufforderung für VS 2019** ähnlich wie dies hier:

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvars64.bat"`

Die architekturspezifischen Batchdateien legen den *architecture*-Parameter fest und rufen „vcvarsall.bat“ auf. Sie können diesen Batchdateien die gleichen zusätzlichen Optionen übergeben, die Sie an „vcvarsall.bat“ übergeben würden, oder Sie können „vcvarsall.bat“ einfach direkt aufrufen. Um Parameter für Ihre eigene Befehlsverknüpfung anzugeben, fügen Sie sie am Ende des Befehls in doppelten Anführungszeichen hinzu. Um beispielsweise eine Verknüpfung zum Erstellen von ARM-Code für UWP auf einer 64-Bit-Plattform mithilfe des neuesten Windows SDK und eines Compilertoolsets, das früher als die aktuelle Version ist, einzurichten, müssen Sie die Versionsnummer angeben. Verwenden Sie in Ihrer Verknüpfung etwas in der Art dieses Befehlsziels:

`%comspec% /k "C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\VC\Auxiliary\Build\vcvarsall.bat amd64_arm uwp -vcvars_ver=15.0"`

Sie müssen den Pfad anpassen, damit er Ihr Visual Studio-Installationsverzeichnis angibt. Die vcvarsall.bat-Datei enthält zusätzliche Informationen über bestimmte Versionsnummern.

## <a name="command-line-tools"></a>Befehlszeilentools

Zum Erstellen eines C-/C++-Projekts an der Befehlszeile bietet Visual Studio die folgenden Befehlszeilentools:

[CL](reference/compiling-a-c-cpp-program.md)<br/>
Verwenden Sie den Compiler (cl.exe), um Quellcodedateien in Apps, Bibliotheken und DLLs zu kompilieren und zu verknüpfen.

[Link](reference/linking.md)<br/>
Verwenden Sie den Linker (link.exe), um kompilierte Objektdateien in Apps und DLLs zu verknüpfen.

[MSBuild](msbuild-visual-cpp.md)<br/>
Verwenden Sie MSBuild (msbuild.exe) und eine Projektdatei (.vcxproj), um einen Build zu konfigurieren und das Toolset indirekt aufzurufen. Dies entspricht dem Ausführen des Befehls **Build** für Projekte oder **Projektmappe erstellen** in der Visual Studio-IDE. Das Ausführen von MSBuild auf der Befehlszeile ist ein fortgeschrittenes Szenario und wird allgemein nicht empfohlen.

[DEVENV](/visualstudio/ide/reference/devenv-command-line-switches)<br/>
Verwenden Sie DEVENV (devenv.exe) in Kombination mit einem Befehlszeilenschalter, zum Beispiel **/Build** oder **/Clean**, um bestimmte Buildbefehle auszuführen, ohne die Visual Studio-IDE anzuzeigen. Im Allgemeinen ist dies der direkten Verwendung von MSBuild vorzuziehen, da Sie Visual Studio die Komplexität von MSBuild überlassen können.

[NMAKE](reference/nmake-reference.md)<br/>
Verwenden Sie NMAKE (nmake.exe) unter Windows, um C++-Projekte auf der Grundlage eines traditionellen Makefiles zu erstellen.

Wenn Sie Builds an der Befehlszeile ausführen, ist der F1-Befehl für Soforthilfe nicht verfügbar. Stattdessen können Sie eine Suchmaschine verwenden, um Informationen über Warnungen, Fehler und Meldungen abzurufen, oder Sie können die Offline-Hilfedateien verwenden. Um die Suche in [docs.microsoft.com](https://docs.microsoft.com/cpp/) zu verwenden, geben Sie Ihre Suchzeichenfolge in das Suchfeld oben auf der Seite ein.

## <a name="in-this-section"></a>In diesem Abschnitt

In den Artikeln in diesem Abschnitt der Dokumentation erfahren Sie, wie Sie Apps über die Befehlszeile erstellen. Zudem wird beschrieben, wie Sie die Befehlszeilen-Buildumgebung für die Verwendung von 64-Bit-Toolsets und das Abzielen auf x86-, x64- und ARM-Plattformen verwenden. Und es wird gezeigt, wie Sie die Befehlszeilen-Buildtools MSBuild und NMAKE verwenden.

[Exemplarische Vorgehensweise: Kompilieren eines nativen C++-Programms in der Befehlszeile](walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)<br/>
Gibt ein Beispiel, das zeigt, wie Sie ein einfaches C++-Programm über die Befehlszeile erstellen und kompilieren.

[Exemplarische Vorgehensweise: Compile a C Program on the Command Line (Exemplarische Vorgehensweise: Kompilieren eines C-Programms in der Befehlszeile)](walkthrough-compile-a-c-program-on-the-command-line.md)<br/>
Beschreibt, wie Sie ein in der Programmiersprache C geschriebenes Programm kompilieren.

[Exemplarische Vorgehensweise: Kompilieren eines C++- bzw. CLI-Programms in der Befehlszeile](walkthrough-compiling-a-cpp-cli-program-on-the-command-line.md)<br/>
Beschreibt, wie Sie ein C++-/CLI-Programm erstellen und kompilieren, das .NET Framework verwendet.

[Exemplarische Vorgehensweise: Kompilieren eines C++- bzw.-CX-Programms in der Befehlszeile](walkthrough-compiling-a-cpp-cx-program-on-the-command-line.md)<br/>
Beschreibt, wie Sie ein C++-/CX-Programm erstellen und kompilieren, das die Windows Runtime verwendet.

[Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds](setting-the-path-and-environment-variables-for-command-line-builds.md)<br/>
Beschreibt, wie Sie ein Befehlseingabeaufforderungsfenster starten, in dem die erforderlichen Umgebungsvariablen für Befehlszeilenbuilds festgelegt sind, die auf x86-, x64- und ARM-Plattformen abzielen und für die ein 32-Bit- oder 64-Bit-Toolset verwendet wird.

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