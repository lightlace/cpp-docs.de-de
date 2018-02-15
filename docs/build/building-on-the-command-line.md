---
title: C/C++-Code in der Befehlszeile erstellen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9f613c20e0cab45a8eaa802c4c7ba0c6ac391357
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="build-cc-code-on-the-command-line"></a>Erstellen von C/C++-Code in der Befehlszeile

Sie können C- und C++-Anwendungen in der Befehlszeile erstellen, in dem Sie die in [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] enthaltenen Tools verwenden.

Bei Auswahl einer C++-arbeitsauslastungen innerhalb der [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] Installer wird ein Toolset, die die C/C++-Compiler, Linker, installiert und andere Buildtools. Diese Tools werden verwendet, durch die [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] IDE, und sie können auch in der Befehlszeile verwendet werden. Es gibt separate X86 gehostet und X64 gehosteten Compiler und Tools zum Erstellen von Code für X86 X64 und ARM-Ziele. Jeder Satz von Tools für eine bestimmte Architektur von Host und das Ziel Build ist im Verzeichnis eigenen gespeichert. Diese Tools ordnungsgemäß funktioniert, erfordern einige bestimmte Umgebungsvariablen, die sie auf den Pfad hinzufügen und festlegen gehören, Datei, Bibliotheksdatei und SDK-Verzeichnissen. Um diese Umgebungsvariablen festgelegt zu erleichtern, erstellt das Installationsprogramm angepasste Befehlsdateien, auch bekannt als Batchdateien, während der Installation. Sie können eine dieser Befehlsdateien in einem Eingabeaufforderungsfenster zum Festlegen von einer bestimmten Build-Architektur ausführen. Der Einfachheit halber erstellt das Installationsprogramm auch Tastenkombinationen im Startmenü (oder Startseite für Windows 8.x), die Developer-Eingabeaufforderungsfenster starten, indem diese Befehlsdateien verwenden, damit die erforderlichen Umgebungsvariablen festgelegt und kann verwendet werden. 

Die erforderlichen Umgebungsvariablen sind spezifisch für Ihre Installation und der Build-Architektur, die Sie und durch Produktupdates und -Upgrades geändert werden können. Daher empfehlen wir dringend, dass Sie eine der installierten eingabeaufforderungsverknüpfungen oder Befehlsdateien verwenden, statt die Umgebungsvariablen in Windows selbst festzulegen. Weitere Informationen finden Sie unter [Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds](../build/setting-the-path-and-environment-variables-for-command-line-builds.md).  

Das Befehlszeilen-Toolsets, Befehlsdateien und Verknüpfungen der Eingabeaufforderung, die installiert werden, hängen von Prozessor Ihres Computers und während der Installation ausgewählten Optionen. Mindestens sind die 32-Bit-X86 gehosteten 32-Bit-X86 systemeigenem Code zu erstellen und Tools cross Tools, die 64-Bit-X64 systemeigenem Code zu erstellen installiert. Wenn Sie 64-Bit-Windows verfügen, werden auch die 64-Bit-X64-gehostete systemeigene 64-Bit-Code zu erstellen und Tools cross Tools, die systemeigenen 32-Bit-Code erstellen installiert. Falls gewünscht die optionalen universelle Windows-Plattform von C++-Tools zu installieren, werden die 32-Bit und 64-Bit-systemeigenen Tools, die ARM-Code zu erstellen auch installiert. Andere arbeitsauslastungen möglicherweise zusätzliche Tools installieren.

<a name="developer_command_prompt_shortcuts"></a>
## <a name="developer-command-prompt-shortcuts"></a>Entwickler eingabeaufforderungsverknüpfungen

Die eingabeaufforderungsverknüpfungen installiert sind, in eine versionsspezifische [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] Ordner im Startmenü. Hier ist eine Liste der grundlegenden eingabeaufforderungsverknüpfungen und die Build-Architekturen, die sie unterstützen:

- **Developer-Eingabeaufforderung** richtet die Umgebung für die 32-Bit, X86 systemeigenen Tools verwenden, um die 32-Bit, X86 systemeigenem Code zu erstellen.  
- **X86 native Tools-Eingabeaufforderung** richtet die Umgebung für die 32-Bit, X86 systemeigenen Tools verwenden, um die 32-Bit, X86 systemeigenem Code zu erstellen.  
- **X64 native Tools-Eingabeaufforderung** richtet die Umgebung für die 64-Bit, X64 systemeigenen Tools verwenden, um die 64-Bit, X64 systemeigenem Code zu erstellen.  
- **x86_x64 Cross Tools-Eingabeaufforderung** richtet die Umgebung für die 32-Bit, X86 systemeigenen Tools verwenden, um die 64-Bit, X64 systemeigenem Code zu erstellen.  
- **x64_x86 Cross Tools-Eingabeaufforderung** richtet die Umgebung für die 64-Bit, X64 systemeigenen Tools verwenden, um die 32-Bit, X86 systemeigenem Code zu erstellen.  

Die tatsächlichen Start Ordner und Verknüpfung Menünamen variieren je nach Version [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] Sie installiert haben, und die Installation der Spitzname, wenn Sie eine festlegen. Z. B. Wenn Sie Visual Studio 2017 installiert haben und sie eine Installation Spitzname 15.3 zugewiesen haben, die Developer-eingabeaufforderungsverknüpfung heißt **Developer-Eingabeaufforderung für VS 2017 (15.3)**, in einem Ordner namens  **Visual Studio-2017**. 

Wenn Sie installiert haben die [Build-Tools für Visual Studio-2017](https://go.microsoft.com/fwlink/p/?linkid=840931) oder [Visual C++ 2015-Buildtools](http://landinghub.visualstudio.com/visual-cpp-build-tools) Edition nur möglicherweise bestimmte systemeigen oder Cross tools Eingabeaufforderungsoptionen für Entwickler. 

<a name="developer_command_prompt"></a>
## <a name="to-open-a-developer-command-prompt-window"></a>Um ein Developer-Eingabeaufforderungsfenster zu öffnen.  
  
1.  Auf dem Desktop öffnen Sie das Windows **starten** Menü, und klicken Sie dann einen Bildlauf zum Suchen und öffnen Sie den Ordner für Ihre Version von Visual Studio, z. B. **Visual Studio 2017**. In einigen älteren Versionen von Visual Studio, sind die Tastenkombinationen in einen Unterordner namens **Visual Studio-Tools**.  
  
2.  Wählen Sie in den Ordner der **Entwicklereingabeaufforderung** für Ihre Version von Visual Studio. Diese Tastenkombination startet ein Developer-Eingabeaufforderungsfenster aus, die die Standard-Build-Architektur von 32-Bit, X86 systemeigenen Tools verwendet, um 32-Bit, X86 systemeigenem Code zu erstellen. Wenn Sie eine nicht standardmäßige Build Architektur bevorzugen, wählen Sie eine der systemeigenen oder Cross tools eingabeaufforderungen an den Host und Ziel-Architektur. 

Eine schnellere Möglichkeit, ein Developer-Eingabeaufforderungsfenster zu öffnen ist, geben *entwicklereingabeaufforderung* in der desktop Suchfeld ein, wählen Sie dann das gewünschte Ergebnis.

<a name="developer_command_files"></a>
## <a name="developer-command-files-and-locations"></a>Befehlsdateien für Entwickler und Standorte

Wenn Sie im Eingabeaufforderungsfenster vorhandenen Architektur Buildumgebung festlegen möchten, können Sie eine der Befehlsdateien, die vom Installationsprogramm erstellt werden. Der Speicherort dieser Dateien hängt von der Version des [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] Sie installiert haben und auf den Speicherort, und benennen die Optionen, die Sie während der Installation vorgenommen. Für Visual Studio 2017 Standardinstallation auf einem 64-Bit-Computer befinden sich im \Programme Dateien (x86) \Microsoft Visual Studio\2017\\*Edition*, wobei *Edition* möglicherweise-Community Professional, Enterprise, BuildTools oder einen anderen Namen, die Sie angegeben. Ist für Visual Studio 2015 Installationspfad in \Programme (x86) \Microsoft Visual Studio 14.0. 

Die primäre Developer-Eingabeaufforderung-Befehlsdatei, VsDevCmd.bat, befindet sich im Unterverzeichnis Common7\Tools des Installationsverzeichnisses. Wenn keine Parameter angegeben sind, wird hiermit die Umgebung und Build-Architektur, die 32-Bit-X86 systemeigenen Tools, mit der 32-Bit-X86 erstellen Code.

Zusätzliche Befehlsdateien stehen zum Einrichten von bestimmten Build-Architekturen, abhängig von der Prozessorarchitektur und der [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] Arbeitslasten und Optionen, die Sie installiert haben. In Visual Studio 2017 diese befinden sich im Unterverzeichnis VC\Auxiliary\Build der [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] -Installationsverzeichnis. In Visual Studio 2015 wird diese befinden sich in der VC VC\bin bzw. VC\bin\\*Architekturen* Unterverzeichnisse des Installationsverzeichnisses, wobei *Architekturen* ist eine der systemeigenen oder cross Compileroptionen. Diese Befehlsdateien Festlegen von Parametern und rufen VsDevCmd.bat angegebenen Buildumgebung Architektur einrichten. Eine Standardinstallation kann diese Befehlsdateien umfassen:

- **vcvars32.bat** verwenden Sie die 32-Bit-X86 systemeigenen-Tools zum Erstellen von 32-Bit-X86 Code.  
- **vcvars64.bat** verwenden die 64-Bit-X64 systemeigenen Tools zum Erstellen von 64-Bit-X64 Code.  
- **vcvarsx86_amd64.bat** verwenden Sie 32-Bit-nativen X86 Cross Tools zum Erstellen von 64-Bit-X64 Code.  
- **vcvarsamd64_x86.bat** verwenden Sie 64-Bit-nativen X64 Cross Tools zum Erstellen von X86 32-Bit-Code.  
- **vcvarsx86_arm.bat** mit 32-Bit-nativen X86 Cross Tools der um ARM-Code zu erstellen.  
- **vcvarsamd64_arm.bat** mit 64-Bit-nativen X64 Cross Tools der um ARM-Code zu erstellen.  
- **"vcvarsall.bat"** mit Parametern geben Sie den Host und für Zielarchitekturen sowie das SDK und Plattform Auswahlmöglichkeiten an. Rufen Sie mithilfe einer `/help` -Parameter für eine Liste mit Optionen.  

> [!CAUTION]
>  Die vcvarsall.bat-Datei und andere Befehlsdateien können von einem Computer zu variieren. Ersetzen Sie eine fehlender oder beschädigte vcvarsall.bat-Datei nicht durch eine Datei von einem anderen Computer. Führen Sie erneut die [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] Installer, um die fehlende Datei zu ersetzen.  
>   
> Die vcvarsall.bat-Datei ist auch von Version zu Version unterschiedlich. Wenn die aktuelle Version von Visual C++ auf einem Computer, die auch eine frühere Version von Visual C++ verfügt installiert ist, werden nicht ausgeführt "vcvarsall.bat" oder eine andere Befehlsdatei aus unterschiedlichen Versionen im selben Eingabeaufforderungsfenster.  
 
Die einfachste Möglichkeit, geben Sie eine bestimmten Build-Architektur in einer vorhandenen Befehlsfenster ist die Verwendung die Datei "vcvarsall.bat". "Vcvarsall.bat" können Sie die Umgebungsvariablen so konfigurieren Sie die Befehlszeile für systeminterne Kompilierung für 32-Bit oder 64-Bit- oder Cross-Kompilierung, X86 X64 oder ARM-Prozessoren festzulegen; Microsoft Store, universelle Windows-Plattform oder Windows-Desktop-Plattformen als Ziel; an welche Windows-SDK verwenden; und die Version der Plattform Toolset angeben. Wenn keine Argumente bereitgestellt werden, konfiguriert die vcvarsall.bat die Umgebungsvariablen für die Verwendung des aktuellen systemeigenen 32-Bit-Compilers für X86 Windows-Desktop-Ziele. Allerdings können Sie ihn so konfigurieren Sie alle für das systemeigene und cross Compilertools verwenden. Wenn Sie eine Compilerkonfiguration, die nicht installiert oder ist nicht auf der buildcomputerarchitektur verfügbar angeben, wird eine Fehlermeldung angezeigt. Diese Tabelle zeigt die Architektur, die unterstützt Argumente:  
  
|Vcvarsall.bat-Architektur-argument|Compiler|Architektur des Host-Computers|Buildausgabearchitektur|  
|----------------------------|--------------|----------------------------------|-------------------------------|  
|x86|x86-32-Bit systemeigen|x86, x64|x86|  
|X86\_amd64 oder X86\_X64|Plattformübergreifende X64 auf x86|x86, x64|x64|  
|x86_arm|ARM auf x86-Cross|x86, x64|ARM|  
|AMD64- oder x64|X64 64-Bit systemeigen|x64|x64|  
|AMD64\_X86 oder X64\_X86|Plattformübergreifende X86 auf x64|x64|x86|  
|AMD64\_ARM- oder eine X64\_Arm|ARM auf X64 plattformübergreifende|x64|ARM|  
  
Können Sie die **speichern** oder **Uwp** Optionen aus, um den Plattformtyp aus, oder keines von beiden zum Angeben einer desktop-app angeben. Sie können das Windows SDK-Version angeben möchten, verwenden Sie eine vollständige Windows 10-SDK-Zahl, z. B. 10.0.10240.0 oder 8.1, um das Windows 8.1-SDK verwenden, geben. Verwenden Sie an das Visual Studio 2015-Compilertoolset 14.0; Standardmäßig ist die Umgebung der Visual Studio-2017 Compilertoolset Verwendung festgelegt.

<a name="vcvarsall"></a>
## <a name="to-set-up-the-build-environment-in-an-existing-command-prompt-window"></a>So richten Sie die Build-Umgebung in eine vorhandene Eingabeaufforderungsfenster ein  
  
1.  Verwenden Sie an der Eingabeaufforderung den Befehl CD so ändern Sie in der Visual Studio-Installationsverzeichnisses. Verwenden Sie CD dann erneut auf das Unterverzeichnis ändern, die konfigurationsspezifischen Befehlsdateien enthält. Für Visual Studio 2017 ist dies das VC\Auxiliary\Build-Unterverzeichnis. Verwenden Sie für Visual Studio 2015 die VC-Unterverzeichnis.  
  
1.  Geben Sie zum Konfigurieren dieses Eingabeaufforderungsfenster aus, um die 32-Bit-Tools verwenden, um das Erstellen von Code für X86 Plattformen, an der Eingabeaufforderung aus:  
  
     `vcvarsall`  

1.  Geben Sie zum Konfigurieren dieses Eingabeaufforderungsfenster aus, um die 32-Bit-Tools verwenden, um das Erstellen von Code für X64 Plattformen, an der Eingabeaufforderung aus:  
  
     `vcvarsall x86_amd64`  
  
1.  Geben Sie zum Konfigurieren dieses Eingabeaufforderungsfenster aus, um die 32-Bit-Tools verwenden, um das Erstellen von Code für ARM-Plattformen, an der Eingabeaufforderung Folgendes ein:  
  
     `vcvarsall x86_arm`  
  
1.  Geben Sie zum Konfigurieren dieses Eingabeaufforderungsfenster aus, um die 64-Bit-Tools verwenden, um das Erstellen von Code für X64 Plattformen, an der Eingabeaufforderung aus:  
  
     `vcvarsall amd64`  
  
1.  Geben Sie zum Konfigurieren dieses Eingabeaufforderungsfenster aus, um die 64-Bit-Tools verwenden, um das Erstellen von Code für X86 Plattformen, an der Eingabeaufforderung aus:  
  
     `vcvarsall amd64_x86`  
  
1.  Geben Sie zum Konfigurieren dieses Eingabeaufforderungsfenster aus, um die 64-Bit-Tools verwenden, um das Erstellen von Code für ARM-Plattformen, an der Eingabeaufforderung Folgendes ein:  
  
     `vcvarsall amd64_arm`  

Die Befehlsdatei legt die erforderlichen Umgebungsvariablen für Pfade auf den Build-Tools, Bibliotheken und Header fest. Dieses Eingabeaufforderungsfenster können jetzt den Befehlszeilencompiler und Tools ausgeführt werden.  
  
Bei Verwendung von [DEVENV](/visualstudio/ide/reference/devenv-command-line-switches) für Befehlszeilenbuilds von vcvarsall.bat oder andere Befehlsdateien eingerichtete Umgebung hat keinen Einfluss auf Ihre Builds aus, es sei denn, Sie auch angeben, dass die **/useenv** Option.  

## <a name="command-line-tools"></a>Befehlszeilentools
  
Zum Erstellen eines C/C++-Projekts in der Befehlszeile angegeben, können Sie diese Visual C++-Befehlszeilentools verwenden:  
  
[CL](../build/reference/compiling-a-c-cpp-program.md)  
Verwenden Sie den Compiler (cl.exe), um Quellcodedateien in Apps, Bibliotheken und DLLs zu kompilieren und zu verknüpfen.  
  
[Link](../build/reference/linking.md)  
Verwenden Sie den Linker (link.exe), um kompilierte Objektdateien in Apps und DLLs zu verknüpfen.  
  
[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)  
Verwenden von MSBuild (msbuild.exe) zum Erstellen von Visual C++-Projekten und [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] Lösungen. Dies entspricht dem Ausführen der **erstellen** Projekt oder **Projektmappe** -Befehl in der [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] IDE.  
  
[DEVENV](/visualstudio/ide/reference/devenv-command-line-switches)  
Verwenden Sie DEVENV (devenv.exe) kombiniert mit einer Befehlszeilenoption – z. B. **/Build** oder **/Clean**– auszuführenden bestimmte Buildbefehle ohne Anzeige der [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] IDE.  
  
[NMAKE](../build/nmake-reference.md)  
Verwenden Sie NMAKE (nmake.exe), um Aufgaben zu automatisieren, die Visual C++-Projekte mithilfe eines herkömmlichen Makefiles zu erstellen.  
  
Wenn Sie in der Befehlszeile erstellen, erhalten Sie Informationen zu Warnungen, Fehlern und Meldungen. Starten Sie [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] und wählen Sie dann auf der Menüleiste **Hilfe**, **Suche**.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

In den Artikeln in diesem Abschnitt der Dokumentation erfahren Sie, wie Sie Apps über die Befehlszeile erstellen. Zudem wird beschrieben, wie Sie die Befehlszeilen-Buildumgebung für die Verwendung von 64-Bit-Toolsets und das Abzielen auf x86-, x64- und ARM-Plattformen verwenden. Und es wird gezeigt, wie Sie die Befehlszeilen-Buildtools MSBuild und NMAKE verwenden.  
  
[Exemplarische Vorgehensweise: Kompilieren eines nativen C++-Programms in der Befehlszeile](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md)  
Gibt ein Beispiel, das zeigt, wie Sie ein einfaches C++-Programm über die Befehlszeile erstellen und kompilieren.  
  
[Exemplarische Vorgehensweise: Kompilieren eines C-Programms in der Befehlszeile](../build/walkthrough-compile-a-c-program-on-the-command-line.md)  
Beschreibt, wie Sie ein in der Programmiersprache C geschriebenes Programm kompilieren.  
  
[Exemplarische Vorgehensweise: Kompilieren eines C++/CLI-Programms in der Befehlszeile](../build/walkthrough-compiling-a-cpp-cli-program-on-the-command-line.md)  
Beschreibt, wie Sie ein C++-/CLI-Programm erstellen und kompilieren, das .NET Framework verwendet.  
  
[Exemplarische Vorgehensweise: Kompilieren eines C++/-CX-Programms in der Befehlszeile](../build/walkthrough-compiling-a-cpp-cx-program-on-the-command-line.md)  
Beschreibt, wie Sie ein C++-/CX-Programm erstellen und kompilieren, das die Windows Runtime verwendet.  
  
[Festlegen der Pfad- und Umgebungsvariablen für Befehlszeilenbuilds](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)  
Beschreibt, wie ein Eingabeaufforderungsfenster starten, die über die erforderlichen Umgebungsvariablen für Befehlszeilenbuilds festgelegt, die auf X86, X64,- und ARM-Plattformen mithilfe eines 32-Bit oder 64-Bit-Toolsets verfügt.  
  
[NMAKE-Referenz](../build/nmake-reference.md)  
Enthält Links zu Artikeln, in denen das Microsoft Program Maintenance Utility (NMAKE.EXE) beschrieben wird.  
  
[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)  
Enthält Links zu Artikeln, in denen die Verwendung von MSBuild.EXE dargestellt wird.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

[/MD, /MT, /LD (Laufzeitbibliothek verwenden)](../build/reference/md-mt-ld-use-run-time-library.md)  
Beschreibt die Verwendung dieser Compileroptionen für eine Debug- oder Releaselaufzeitbibliothek.  
  
[C/C++-Compileroptionen](../build/reference/compiler-options.md)  
Enthält Links zu Artikeln, in denen die C- und C++-Compileroptionen sowie CL.exe erläutert werden.  
  
[Linkeroptionen](../build/reference/linker-options.md)  
Enthält Links zu Artikeln, in denen die Linkeroptionen und LINK.EXE dargestellt werden.  
  
[C/C++-Buildtools](../build/reference/c-cpp-build-tools.md)  
Enthält Links zu den C-/C++-Buildtools, die in [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] enthalten sind.  
  
## <a name="see-also"></a>Siehe auch  

[Erstellen von C/C++-Programmen](../build/building-c-cpp-programs.md)