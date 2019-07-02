---
title: CMakeSettings.json-Schemareferenz
ms.date: 05/16/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: cc9b9a788f17e9257bed628024e3f65dfc89fb23
ms.sourcegitcommit: b233f05adae607f75815111006a771c432df5a9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67516384"
---
# <a name="cmakesettingsjson-schema-reference"></a>CMakeSettings.json-Schemareferenz

Die **"cmakesettings.JSON"** -Datei enthält Informationen, der angibt, wie Visual Studio mit CMake zum Erstellen eines Projekts für eine bestimmte Plattform interagieren soll. Diese Datei speichert Informationen wie Umgebungsvariablen oder Argumente für die „cmake.exe“-Umgebung. Sie können sie direkt bearbeiten oder den **CMake-Einstellungs-Editor** verwenden (Visual Studio 2019 und höher). Weitere Informationen über den Editor finden Sie unter [Anpassen von CMake-Buildeinstellungen in Visual Studio](customize-cmake-settings.md).

## <a name="environments"></a>Umgebungen

Das `environments`-Array enthält eine Liste von `items` vom Typ `object`, die ein Compilertoolset „Umgebung“ definieren. Eine Umgebung kann zur Anwendung einer Gruppe von Variablen auf eine `configuration` verwendet werden. Jedes Element im `environments`-Array besteht aus Folgendem:

- `namespace`: Benennt die Umgebung, sodass durch die Form `namespace.variable` über eine Konfiguration auf deren Variablen verwiesen werden kann. Das Standardumgebungsobjekt wird `env` genannt und mit bestimmten Systemumgebungsvariablen aufgefüllt, darunter `%USERPROFILE%`.
- `environment`: Identifiziert diese Gruppe von Variablen eindeutig. Ermöglicht der Gruppe, später in einem `inheritEnvironments`-Eintrag geerbt zu werden.
- `groupPriority`: Eine ganze Zahl, die bei der Auswertung die Priorität dieser Variablen angibt. Elemente mit höherer Nummer werden zuerst ausgewertet.
- `inheritEnvironments`: Ein Array von Werten, die die Gruppe von Umgebungen angeben, die von dieser Gruppe geerbt werden. Durch dieses Feature können Sie Standardumgebungen vererben und benutzerdefinierte Umgebungsvariablen erstellen, die bei der Ausführung an „CMake.exe“ übergeben werden.

   ```json
   "inheritEnvironments": [ "msvc_x64_x64" ]
   ```

   Das obige Beispiel entspricht der Ausführung der **Developer-Eingabeaufforderung für Visual Studio 2017** oder der **Developer-Eingabeaufforderung für Visual Studio 2019** mit den Argumenten **-arch=amd64 -host_arch=amd64**. Es können jede benutzerdefinierte Umgebung oder diese vordefinierten Umgebungen verwendet werden:
 
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
  
  **Nur Visual Studio 2019:**
  - Visual Studio 16 2019
  - Visual Studio 16 2019 Win64
  - Visual Studio 16 2019 ARM

  **Visual Studio 2017 und höher:**
  - Visual Studio 15 2017
  - Visual Studio 15 2017 Win64
  - Visual Studio 15 2017 ARM
  - Visual Studio 14 2015
  - Visual Studio 14 2015 Win64
  - Visual Studio 14 2015 ARM
  - Unix Makefiles
  - Ninja

Da Ninja für schnelle Buildgeschwindigkeiten statt für Flexibilität und Funktionalität entwickelt wurde, ist dieser als Standardwert festgelegt. Einige CMake-Projekte können jedoch mit Ninja keinen ordnungsgemäßen Build durchführen. In diesem Fall können Sie CMake anweisen, stattdessen ein Visual Studio-Projekt zu erstellen.

Öffnen Sie `CMakeSettings.json` über das Hauptmenü, indem Sie auf **CMake > CMake-Einstellungen ändern** klicken, um einen Visual Studio-Generator in Visual Studio 2017 anzugeben. Löschen Sie „Ninja“, und geben Sie „V“ ein. Dadurch wird IntelliSense aktiviert, und Sie können den gewünschten Generator auswählen.

Um einen Visual Studio-Generator in Visual Studio 2019 anzugeben, klicken Sie mit der rechten Maustaste auf die Datei „CMakeLists.txt“im **Projektmappen-Explorer**, und wählen Sie **CMake-Einstellungen für Projekt** > **Erweiterte Einstellungen anzeigen** > **CMake-Generator** aus.

Wenn in der aktiven Konfiguration ein Visual Studio-Generator angegeben ist, wird standardmäßig „MSBuild.exe“ über `-m -v:minimal`-Argumente aufgerufen. In der Datei `CMakeSettings.json` können Sie zusätzliche [MSBuild-Befehlszeilenargumente](../build/reference/msbuild-visual-cpp-overview.md) angeben, die über die Eigenschaft `buildCommandArgs` an das Buildsystem übergeben werden sollen, um den Build anzupassen:

   ```json
   "buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
   ```

- `configurationType`: Gibt die Buildtypkonfiguration für den ausgewählten Generator an. Folgende stehen zur Auswahl:
 
  - Debug
  - Freigabe
  - MinSizeRel
  - RelWithDebInfo
 
- `inheritEnvironments`: Gibt mindestens eine Compilerumgebung an, von der diese Konfiguration abhängt. Dabei kann es sich um jede benutzerdefinierte Umgebung oder eine der vordefinierten Umgebungen handeln.
- `buildRoot`: Gibt das Verzeichnis an, in dem CMake Buildskripts für den ausgewählten Generator erstellt.  Ist dem Schalter **-DCMAKE_BINARY_DIR** zugeordnet und gibt an, wo der CMake-Cache erstellt wird. Wenn der Ordner nicht vorhanden ist, wird er erstellt. Zu den unterstützten Makros gehören `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `installRoot`: Gibt das Verzeichnis an, in dem CMake Installationsziele für den ausgewählten Generator erstellt. Unterstützte Makros sind `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `cmakeCommandArgs`: Gibt zusätzliche Befehlszeilenoptionen an, die beim Aufruf zum Generieren des Caches an CMake übergeben werden.
- `cmakeToolchain`: Gibt die Toolkettendatei an. Diese wird über „-DCMAKE_TOOLCHAIN_FILE“ an CMake übergeben.
- `buildCommandArgs`: Gibt native Buildoptionen an, die nach „--build --“ an CMake übergeben werden. Beispielsweise wird beim Übergeben von „-v“ mithilfe des Ninja-Generators erzwungen, dass Ninja Befehlszeilen ausgibt. Weitere Informationen zu Ninja-Befehlen finden Sie unter [Ninja-Befehlszeilenargumente](#ninja).
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

### <a name="additional-settings-for-cmake-linux-projects"></a>Zusätzliche Einstellungen für CMake-Projekte unter Linux. 

- `remoteMachineName`: Gibt den Namen des Linux-Remotecomputers an, auf dem CMake, Builds und der Debugger gehostet werden. Verwenden Sie den Verbindungs-Manager zum Hinzufügen neuer Linux-Computer. Unterstützte Makros sind `${defaultRemoteMachineName}`.
- `remoteCopySourcesOutputVerbosity`: Gibt den Ausführlichkeitsgrad des Quellkopiervorgangs zum Remotecomputer an. Zur Auswahl stehen „Normal“ (Regulär), „Verbose“ (Ausführlich) und „Diagnostic“ (Diagnostisch).
- `remoteCopySourcesConcurrentCopies`: Gibt die Anzahl gleichzeitiger Kopien, die während der Synchronisierung der Quellen auf den Remotecomputer (nur Sftp) verwendet.
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
- `variables`: enthält ein Name/Wert-Paar von CMake-Variablen, die als **-D** *_name_=_value_* an CMake übergeben werden. Wenn die Buildanweisungen Ihres CMake-Projekts das direkte Hinzufügen aller Variablen zur CMake-Cachedatei festlegen, wird empfohlen, diese stattdessen hier hinzuzufügen. Im folgenden Beispiel wird gezeigt, wie Sie die Name/Wert-Paare für das Toolset 14.14.26428 MSVC angeben können:

```json
"variables": [
    {
      "name": "CMAKE_CXX_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe",
      "type": "FILEPATH"
    },
    {
      "name": "CMAKE_C_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe",
      "type": "FILEPATH"
    }
  ]
```

Beachten Sie, dass standardmäßig vom Typ „STRING“ ausgegangen wird, wenn Sie den `"type"` nicht definieren.

## <a name="environment-variables"></a>Umgebungsvariablen

`CMakeSettings.json` unterstützt ebenfalls die Verwendung von Umgebungsvariablen in allen zuvor erwähnten Eigenschaften. Die Syntax zum Erweitern der Umgebungsvariable %FOO% ist `${env.FOO}`.

Sie haben in dieser Datei ebenfalls Zugriff auf integrierte Makros:

- `${workspaceRoot}`: stellt den vollständigen Pfad des Arbeitsbereichsordners bereit
- `${workspaceHash}`: Hash des Speicherorts für den Arbeitsbereich; nützlich für das Erstellen eines eindeutigen Bezeichners für den aktuellen Arbeitsbereich (z.B. für die Verwendung in Ordnerpfaden)
- `${projectFile}`: der vollständige Pfad der CMakeLists.txt-Stammdatei
- `${projectDir}`: der vollständige Pfad des Ordners der CMakeLists.txt-Stammdatei
- `${thisFile}`: der vollständige Pfad der Datei `CMakeSettings.json`
- `${name}`: der Name der Konfiguration
- `${generator}`: der Name des CMake-Generators, der in dieser Konfiguration verwendet wurde


### <a name="custom-environment-variables"></a>Benutzerdefinierte Umgebungsvariablen

In `CMakeSettings.json` können Sie benutzerdefinierte Umgebungsvariablen global oder pro Konfiguration in der Eigenschaft **environments** definieren. In folgendem Beispiel wird eine globale Variable (**BuildDir**) definiert, die in den Konfigurationen „x86-Debug“ und „x64-Debug“ geerbt wird. Jede Konfiguration verwendet die Variable, um den Wert für die Eigenschaft **buildRoot** der Konfiguration anzugeben. Beachten Sie ebenfalls, wie jede Konfiguration die Eigenschaft **inheritEnvironments** verwendet, um eine Variable anzugeben, die nur für diese Konfiguration gilt.

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x86 compiler.
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.BuildDir}\\${name}"    },
    {
      "name": "x64-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x64 compiler.
      "inheritEnvironments": [ "msvc_x64" ],
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

Im nächsten Beispiel definiert die x86-Debug-Konfiguration einen eigenen Wert für die Eigenschaft **BuildDir**. Dieser Wert überschreibt den Wert, der von der globalen Eigenschaft **BuildDir** festgelegt wird, sodass **BuildRoot** zu `D:\custom-builddir\x86-Debug` ausgewertet wird.

```json
{
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",

      // The syntax for this property is the same as the global one above.
      "environments": [
        {
          // Replace the global property entirely.
          "BuildDir": "D:\\custom-builddir"
          // This environment does not specify a namespace, hence by default "env" will be assumed.
          // "namespace" : "name" would require that this variable be referenced with "${name.BuildDir}".
        }
      ],

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      // Evaluates to "D:\custom-builddir\x86-Debug"
      "buildRoot": "${env.BuildDir}\\${name}"
    },
    {
      "name": "x64-Debug",

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x64" ],
      // Since this configuration doesn’t modify BuildDir, it inherits
      // from the one defined globally.
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

## <a name="ninja"></a> Ninja-Befehlszeilenargumente

Wenn keine Ziele festgelegt sind, wird das Standardziel erstellt.

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|Option|Beschreibung|
|--------------|------------|
| --version  | Ausgabe der Ninja-Version ("1.7.1")|
|   -C DIR   | Änderung in DIR, bevor andere Aktionen ausgeführt werden|
|   -f FILE  | Angabe der Eingabedatei für den Build (Standard: build.ninja)|
|   -j N     | Ausführen von N gleichzeitigen Aufträgen (Standard: 14, abgeleitet von den verfügbaren CPUs)|
|   -k N     | Fortsetzen, bis N Aufträge fehlschlagen (Standard: 1)|
|   -l N     | Kein Starten von neuen Aufträgen, wenn die durchschnittliche Auslastung größer als N ist|
|   -n       | Testausführung (Befehle werden nicht ausgeführt, verhalten sich jedoch, als wären sie erfolgreich)|
|   -v       | Anzeigen aller Befehlszeilen während des Builds|
|   -d MODE  | Aktivieren des Debuggens (verwenden Sie „-d list“, um Modi aufzulisten)|
|   -t TOOL  | Ausführen eines Zusatztools (verwenden Sie „-t list“, um zusätzliche Tools aufzulisten). Beendet Optionen auf oberster Ebene; weitere Flags werden an das Tool übergeben.|
|   -w FLAG  | Anpassen von Warnungen (verwenden Sie „-w list“, um Warnungen aufzulisten)|




