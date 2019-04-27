---
title: Anpassen von CMake-Buildeinstellungen in Visual Studio
ms.date: 03/05/2019
helpviewer_keywords:
- CMake build settings
ms.openlocfilehash: 4864e094ab967a563b153fa79fd0bf5c375f40f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274599"
---
# <a name="customize-cmake-build-settings"></a>Anpassen von CMake-Buildeinstellungen

Visual Studio bietet verschiedene CMake-Konfigurationen, die definieren, wie „CMake.exe“ aufgerufen wird, um den CMake-Cache für ein bestimmtes Projekt zu erstellen. Klicken Sie zum Hinzufügen einer neuen Konfiguration in der Symbolleiste auf die Konfigurations-Dropdownliste, und wählen Sie **Konfigurationen verwalten...** aus:

   ![CMake: „Konfigurationen verwalten...“](media/cmake-manage-configurations.png)

Sie können aus der Liste vordefinierter Konfigurationen wählen:

   ![Vordefinierte CMake-Konfigurationen](media/cmake-configurations.png)

Wenn Sie zum ersten Mal eine Konfiguration auswählen, erstellt Visual Studio im Stammordner des Projekts eine `CMakeSettings.json`-Datei. Diese Datei wird verwendet, um die CMake-Cachedatei erneut zu erstellen, z.B. nach einem **Bereinigungsvorgang**. 

Klicken Sie zum Hinzufügen einer zusätzlichen Konfiguration mit der rechten Maustaste auf `CMakeSettings.json`, und wählen Sie **Konfiguration hinzufügen** aus. 

   ![CMake: „Konfiguration hinzufügen“](media/cmake-add-configuration.png "CMake: „Konfiguration hinzufügen“")

JSON-IntelliSense unterstützt Sie beim Bearbeiten der Datei `CMakeSettings.json`:

   ![JSON-IntelliSense für CMake](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

Sie können die Datei auch mithilfe des **Editors für CMake-Einstellungen** bearbeiten. Klicken Sie mit der rechten Maustaste im **Projektmappen-Explorer** auf `CMakeSettings.json`, und wählen Sie **CMake-Einstellungen bearbeiten** aus. Alternativ können Sie oben im Editor-Fenster aus der Konfigurations-Dropdownliste **Konfigurationen verwalten...** auswählen. 

Sie können `CMakeSettings.json` auch direkt bearbeiten, um benutzerdefinierte Konfigurationen zu erstellen. Im Folgenden wird eine Beispielkonfiguration gezeigt, die Sie als Ausgangspunkt verwenden können:

```json
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "-v",
      "ctestCommandArgs": ""
    },

```

- **name:** der Name, der in der Dropdownliste für die C++-Konfiguration angezeigt wird Mit dem Makro `${name}` können Sie diesen Wert verwenden, wenn Sie andere Eigenschaftswerte wie Pfade verwenden. Ein Beispiel finden Sie in der **buildRoot**-Definition in `CMakeSettings.json`.

- **generator:** Führt eine Zuordnung für die CMake-Option **-G** durch und gibt den Generator an, der verwendet werden soll. Diese Eigenschaft kann ebenfalls als Makro (`${generator}`) beim Erstellen anderer Eigenschaftswerte verwendet werden. Visual Studio unterstützt derzeit folgende CMake-Generatoren:

  - "Ninja"
  - "Visual Studio 14 2015"
  - "Visual Studio 14 2015 ARM"
  - "Visual Studio 14 2015 Win64"
  - "Visual Studio 15 2017"
  - "Visual Studio 15 2017 ARM"
  - "Visual Studio 15 2017 Win64"

  Da Ninja für schnelle Buildgeschwindigkeiten statt für Flexibilität und Funktionalität entwickelt wurde, ist dieser als Standardwert festgelegt. Einige CMake-Projekte können jedoch mit Ninja keinen ordnungsgemäßen Build durchführen. In diesem Fall können Sie CMake anweisen, stattdessen ein Visual Studio-Projekt zu erstellen.

  Öffnen Sie `CMakeSettings.json` über das Hauptmenü, indem Sie auf **CMake > CMake-Einstellungen ändern** klicken, um einen Visual Studio-Generator anzugeben. Löschen Sie „Ninja“, und geben Sie „V“ ein. Dadurch wird IntelliSense aktiviert, und Sie können den gewünschten Generator auswählen.

  Wenn in der aktiven Konfiguration ein Visual Studio-Generator angegeben ist, wird standardmäßig „MSBuild.exe“ über `-m -v:minimal`-Argumente aufgerufen. In der Datei `CMakeSettings.json` können Sie zusätzliche [MSBuild-Befehlszeilenargumente](../build/reference/msbuild-visual-cpp-overview.md) angeben, die über die Eigenschaft `buildCommandArgs` an das Buildsystem übergeben werden sollen, um den Build anzupassen:
    
    ```json
    "buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
    ```

- **buildRoot:** führt eine Zuordnung für die Option **-DCMAKE_BINARY_DIR** und gibt an, wo der CMake-Cache erstellt wird Wenn der Ordner noch nicht vorhanden ist, wird dieser erstellt.

- **variables:** enthält ein Name/Wert-Paar von CMake-Variablen, die als **-D** *_name_=_value_* an CMake übergeben werden. Wenn die Buildanweisungen Ihres CMake-Projekts das direkte Hinzufügen aller Variablen zur CMake-Cachedatei festlegen, wird empfohlen, diese stattdessen hier hinzuzufügen. Im folgenden Beispiel wird gezeigt, wie Sie die Name/Wert-Paare für das Toolset 14.14.26428 MSVC angeben können:

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

Beachten Sie, dass Sie keine definieren die `"type"`, den Typ "STRING" wird standardmäßig angenommen werden.

- **cmakeCommandArgs:** gibt alle zusätzlichen Optionen an, die an „CMake.exe“ übergeben werden sollen

- **configurationType:** definiert den Typ der Buildkonfiguration für den ausgewählten Generator Derzeit werden die Werte "Debug", "MinSizeRel", "Release" und "RelWithDebInfo" unterstützt.

- **ctestCommandArgs:** gibt zusätzliche Optionen an, die beim Ausführen von Tests an CTest übergeben werden sollen.

- **ctestCommandArgs:** gibt zusätzliche Optionen an, die an das zugrunde liegende Buildsystem übergeben werden sollen. Beispielsweise wird beim Übergeben von „-v“ mithilfe des Ninja-Generators erzwungen, dass Ninja Befehlszeilen ausgibt.

Für CMake-Projekte unter Linux sind zusätzliche Einstellungen verfügbar. Weitere Informationen finden Sie unter [Configure a CMake Linux project (Konfigurieren eines CMake-Projekts unter Linux)](../linux/cmake-linux-project.md).

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

## <a name="ninja-command-line-arguments"></a>Ninja-Befehlszeilenargumente

Wenn keine Ziele festgelegt sind, wird das Standardziel erstellt (siehe Anleitung).

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
|   -t TOOL  | Ausführen eines Zusatztools (verwenden Sie „-t list“, um zusätzliche Tools aufzulisten). beendet der obersten Ebene Optionen; Weitere Flags an das Tool übergeben werden.|
|   -w FLAG  | Anpassen von Warnungen (verwenden Sie „-w list“, um Warnungen aufzulisten)|

## <a name="inherited-environments"></a>Geerbte Umgebungen

 `CMakeSettings.json` unterstützt geerbte Umgebungen. Durch dieses Feature können Sie Standardumgebungen vererben und benutzerdefinierte Umgebungsvariablen erstellen, die bei der Ausführung an „CMake.exe“ übergeben werden.

```json
  "inheritEnvironments": [ "msvc_x64_x64" ]
```

Das obige Beispiel entspricht der Ausführung der **Developer-Eingabeaufforderung für Visual Studio 2017** mit den Argumenten **-arch=amd64 -host_arch=amd64**.

In der folgenden Tabelle werden die Standardwerte gezeigt:

|Kontextname|Beschreibung|
|-----------|-----------------|
|vsdev|Die Standardumgebung von Visual Studio|
|msvc_x86|Kompiliert mithilfe von x86-Tools für x86|
|msvc_arm| Kompiliert mithilfe von x86-Tools für ARM|
|msvc_arm64|Kompiliert mithilfe von x86-Tools für ARM64|
|msvc_x86_x64|Kompiliert mithilfe von x86-Tools für AMD64|
|msvc_x64_x64|Kompiliert mithilfe von 64-Bit-Tools für AMD64|
|msvc_arm_x64|Kompiliert mithilfe von 64-Bit-Tools für ARM|
|msvc_arm64_x64|Kompiliert mithilfe von 64-Bit-Tools für ARM64|

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

## <a name="see-also"></a>Siehe auch

[CMake Projects in Visual Studio (CMake-Projekte in Visual Studio)](cmake-projects-in-visual-studio.md)<br/>
[Konfigurieren eines Linux CMake-Projekts](../linux/cmake-linux-project.md)<br/>
[Herstellen einer Verbindung mit Ihrem Linux-Remotecomputer](../linux/connect-to-your-remote-linux-computer.md)<br/>
[Konfigurieren von CMake-Debugsitzungen](configure-cmake-debugging-sessions.md)<br/>
[Bereitstellen, Ausführen und Debuggen Ihres Linux-Projekts](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake predefined configuration reference (Referenz für vordefinierte CMake-Konfigurationen)](cmake-predefined-configuration-reference.md)<br/>
