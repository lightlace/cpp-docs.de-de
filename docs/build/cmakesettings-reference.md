---
title: CMakeSettings.json-Schemareferenz
ms.date: 03/05/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: 893bc5c8efe3fdae80a4a0de8204d391baa63d07
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62195380"
---
# <a name="cmakesettingsjson-schema-reference"></a>CMakeSettings.json-Schemareferenz

Die **"cmakesettings.JSON"**"-Datei enthält Informationen, der angibt, wie Visual Studio mit CMake zum Erstellen eines Projekts für eine bestimmte Plattform interagieren soll. Verwenden Sie diese Datei, um Informationen wie Umgebungsvariablen oder Argumente für die „cmake.exe“-Umgebung zu speichern.

## <a name="environments"></a>Umgebungen

Das `environments`-Array enthält eine Liste von `items` vom Typ `object`, die eine „Umgebung“ definieren. Eine Umgebung kann zur Anwendung einer Gruppe von Variablen auf eine `configuration` verwendet werden. Jedes Element im `environments`-Array besteht aus Folgendem:

- `namespace`: Benennt die Umgebung, sodass durch die Form `namespace.variable` über eine Konfiguration auf deren Variablen verwiesen werden kann. Das Standardumgebungsobjekt wird `env` genannt und mit bestimmten Systemumgebungsvariablen aufgefüllt, darunter `%USERPROFILE%`.
- `environment`: Identifiziert diese Gruppe von Variablen eindeutig. Ermöglicht der Gruppe, später in einem `inheritEnvironments`-Eintrag geerbt zu werden.
- `groupPriority`: Eine ganze Zahl, die bei der Auswertung die Priorität dieser Variablen angibt. Elemente mit höherer Nummer werden zuerst ausgewertet.
- `inheritEnvironments`: Ein Array von Werten, die die Gruppe von Umgebungen angeben, die von dieser Gruppe geerbt werden. Es können jede benutzerdefinierte Umgebung oder diese vordefinierten Umgebungen verwendet werden:
 
  - linux_arm: Hiermit wird ARM Linux als Remotezielversion festgelegt.
  - linux_x64: Hiermit wird x64 Linux als Remotezielversion festgelegt.
  - linux_x86: Hiermit wird x86 Linux als Remotezielversion festgelegt.
  - msvc_arm: Hiermit wird ARM Windows mit dem MSVC-Compiler als Zielversion festgelegt.
  - msvc_arm_x64: Hiermit wird ARM Windows mit dem 64-Bit-MSVC-Compiler als Zielversion festgelegt.
  - msvc_arm64: Hiermit wird ARM64 Windows mit dem MSVC-Compiler als Zielversion festgelegt.
  - msvc_arm64_x64: Hiermit wird ARM64 Windows mit dem 64-Bit-MSVC-Compiler als Zielversion festgelegt.
  - msvc_x64: Hiermit wird x64 Windows mit dem MSVC-Compiler als Zielversion festgelegt.
  - msvc_x64_x64: Hiermit wird x64 Windows mit dem 64-Bit-MSVC-Compiler als Zielversion festgelegt.
  - msvc_x86: Hiermit wird x86 Windows mit dem MSVC-Compiler als Zielversion festgelegt.
  - msvc_x86_x64: Hiermit wird x86 Windows mit dem 64-Bit-MSVC-Compiler als Zielversion festgelegt.

## <a name="configurations"></a>Konfigurationen

Das `configurations`-Array besteht aus Objekten, die CMake-Konfigurationen darstellen, die für die Datei „CMakeLists.txt“ im gleichen Ordner gelten. Sie können diese Objekte verwenden, um mehrere Buildkonfigurationen zu definieren und in der IDE einfach zwischen ihnen zu wechseln. 

Eine `configuration` verfügt über die folgenden Eigenschaften:
- `name`: Benennt die Konfiguration.
- `description`: Beschreibung dieser Konfiguration, die in Menüs angezeigt wird.
- `generator`: Gibt an, welcher CMake-Generator für diese Konfiguration verwendet werden soll. Folgende stehen zur Auswahl:

  - Visual Studio 15 2017
  - Visual Studio 15 2017 Win64
  - Visual Studio 15 2017 ARM
  - Visual Studio 14 2015
  - Visual Studio 14 2015 Win64
  - Visual Studio 14 2015 ARM
  - Unix Makefiles
  - Ninja

- `configurationType`: Gibt die Buildtypkonfiguration für den ausgewählten Generator an. Folgende stehen zur Auswahl:
 
  - Debug
  - Freigabe
  - MinSizeRel
  - RelWithDebInfo
 
- `inheritEnvironments`: Gibt mindestens eine Umgebung an, von der diese Konfiguration abhängt. Dabei kann es sich um jede benutzerdefinierte Umgebung oder eine der vordefinierten Umgebungen handeln.
- `buildRoot`: Gibt das Verzeichnis an, in dem CMake Buildskripts für den ausgewählten Generator erstellt. Unterstützte Makros sind `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `installRoot`: Gibt das Verzeichnis an, in dem CMake Installationsziele für den ausgewählten Generator erstellt. Unterstützte Makros sind `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `cmakeCommandArgs`: Gibt zusätzliche Befehlszeilenoptionen an, die beim Aufruf zum Generieren des Caches an CMake übergeben werden.
- `cmakeToolchain`: Gibt die Toolkettendatei an. Diese wird über „-DCMAKE_TOOLCHAIN_FILE“ an CMake übergeben.
- `buildCommandArgs`: Gibt native Buildoptionen an, die nach „--build --“ an CMake übergeben werden.
- `ctestCommandArgs`: Gibt zusätzliche Befehlszeilenoptionen an, die beim Ausführen der Tests an CTest übergeben werden.
- `codeAnalysisRuleset`: Gibt den Regelsatz an, der beim Ausführen der Codeanalyse verwendet werden soll. Dies kann ein vollständiger Pfad oder der Dateiname einer Regelsatzdatei sein, die von Visual Studio installiert wird.
- `intelliSenseMode`: Gibt den Modus zum Berechnen von IntelliSense-Informationen an. Folgende stehen zur Auswahl:
 
  - windows-msvc-x86
  - windows-msvc-x64
  - windows-msvc-arm
  - windows-msvc-arm64
  - android-clang-x86
  - android-clang-x64
  - android-clang-arm
  - android-clang-arm64
  - ios-clang-x86
  - ios-clang-x64
  - ios-clang-arm
  - ios-clang-arm64
  - windows-clang-x86
  - windows-clang-x64
  - windows-clang-arm
  - windows-clang-arm64
  - linux-gcc-x86
  - linux-gcc-x64
  - linux-gcc-arm

- `cacheRoot`: Gibt den Pfad zu einem CMake-Cache an. Dieses Verzeichnis sollte eine vorhandene „CMakeCache.txt“-Datei enthalten.
- `remoteMachineName`: Gibt den Namen des Linux-Remotecomputers an, auf dem CMake, Builds und der Debugger gehostet werden. Verwenden Sie den Verbindungs-Manager zum Hinzufügen neuer Linux-Computer. Unterstützte Makros sind `${defaultRemoteMachineName}`.
- `remoteCopySourcesOutputVerbosity`: Gibt den Ausführlichkeitsgrad des Quellkopiervorgangs zum Remotecomputer an. Zur Auswahl stehen „Normal“ (Regulär), „Verbose“ (Ausführlich) und „Diagnostic“ (Diagnostisch).
- `remoteCopySourcesConcurrentCopies`: Gibt die Anzahl gleichzeitiger Kopien an, die während der Synchronisierung der Quellen zum Remotecomputer verwendet werden.
- `remoteCopySourcesMethod`: Gibt die Methode zum Kopieren von Dateien auf den Remotecomputer an. Zur Auswahl stehen „rsync“ und „sftp“.
- `remoteCMakeListsRoot`: Gibt das Verzeichnis auf dem Remotecomputer an, das das CMake-Projekt enthält. Unterstützte Makros sind `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `remoteBuildRoot`: Gibt das Verzeichnis auf dem Remotecomputer an, in dem CMake Buildskripts für den ausgewählten Generator erstellt. Unterstützte Makros sind `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `remoteInstallRoot`: Gibt das Verzeichnis auf dem Remotecomputer an, in dem CMake Installationsziele für den ausgewählten Generator erstellt. Unterstützte Makros sind `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}` und `${env.VARIABLE}`, wobei `VARIABLE` eine Umgebungsvariable ist, die auf System-, Benutzer- oder Sitzungsebene definiert wurde.
- `remoteCopySources`: Ein `boolean`, der angibt, ob Visual Studio Quelldateien auf den Remotecomputer kopieren sollte. Der Standardwert ist "True". Legen Sie diesen Wert auf FALSE fest, wenn Sie die Dateisynchronisierung selbst verwalten.
- `remoteCopyBuildOutput`: Ein `boolean`, der angibt, ob die Buildausgaben vom Remotesystem kopiert werden sollen.
- `rsyncCommandArgs`: Gibt zusätzliche Befehlszeilenoptionen an, die an „rsync“ übergeben werden.
- `remoteCopySourcesExclusionList`: Ein `array`, das eine Liste mit Pfaden angibt, die beim Kopieren von Quelldateien ausgeschlossen werden sollen: Als Pfad kann der Name einer Datei/eines Verzeichnisses oder ein Pfad relativ zum Stammverzeichnis der Kopie angegeben werden. Die Platzhalter \\\"*\\\" und \\\"?\\\" können für einen Globmusterabgleich verwendet werden.
- `cmakeExecutable`: gibt den vollständigen Pfad zur ausführbaren CMake-Programmdatei an, einschließlich des Dateinamens und der Dateierweiterung.
- `remotePreGenerateCommand`: Gibt den Befehl an, der vor der Ausführung von CMake zum Analysieren der Datei „CMakeLists.txt“ ausgeführt wird.
- `remotePrebuildCommand`: Gibt den Befehl an, der vor der Erstellung auf dem Remotecomputer ausgeführt wird.
- `remotePostbuildCommand`: Gibt den Befehl an, der nach der Erstellung auf dem Remotecomputer ausgeführt wird.
- `variables`: Ein `array`, das Variablen angibt, die als „-Dname1=value1“, „-Dname2=value2“ usw. an CMake übergeben werden. 


