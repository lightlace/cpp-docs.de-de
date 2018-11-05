---
title: CMake-Projekte in Visual C++ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/18/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93cfa14e943e277b5255eeb486491c831eba0da3
ms.sourcegitcommit: 8c2de32e96c84d0147af3cce1e89e4f28707ff12
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/26/2018
ms.locfileid: "50143730"
---
# <a name="cmake-projects-in-visual-c"></a>CMake-Projekte in Visual C++

In diesem Artikel wird davon ausgegangen, dass Sie mit dem plattformübergreifenden Open Source-Tool „CMake“ vertraut sind, das zum Definieren von Buildprozessen verwendet wird, die auf mehreren Plattformen ausgeführt werden.

In Visual Studio 2015 können Visual Studio-Benutzer einen [CMake-Generator](https://cmake.org/cmake/help/v3.9/manual/cmake-generators.7.html) verwenden, um MSBuild-Projektdateien zu generieren, die anschließend von der IDE für IntelliSense sowie für das Durchsuchen und die Kompilierung verwendet werden.

Ab Visual Studio 2017 verwendet die Komponente **Visual C++-Tools für CMake** das Feature **Ordner öffnen**, um zu ermöglichen, dass die IDE CMake-Projektdateien (z.B. „CMakeLists.txt“) direkt für IntelliSense und das Durchsuchen nutzt. Wenn Sie einen Visual Studio-Generator verwenden, wird eine temporäre Projektdatei generiert und an „msbuild.exe“ übergeben. Diese wird jedoch nie für IntelliSense oder das Durchsuchen geladen.

**Visual Studio 2017, Version 15.3:** Es wird Unterstützung für Ninja- und Visual Studio-Generatoren bereitgestellt.

**Visual Studio 2017, Version 15.4:** Es wurde Unterstützung für CMake unter Linux hinzugefügt. Weitere Informationen finden Sie unter [Konfigurieren eines Linux CMake-Projekts](../linux/cmake-linux-project.md).

**Visual Studio 2017, Version 15.5:** Es wurde Unterstützung für das Importieren von vorhandenen CMake-Caches hinzugefügt. Visual Studio extrahiert benutzerdefinierte Variablen automatisch und erstellt eine vorab aufgefüllte CMakeSettings.json-Datei.

**Visual Studio 2017, Version 15.7:** Es wurde Unterstützung für das Deaktivieren der automatischen Cachegenerierung, der Zielansicht im **Projektmappen-Explorer** und der Kompilierung einzelner Dateien hinzugefügt.

## <a name="installation"></a>Installation

**Visual C++-Tools für CMake** wird standardmäßig als Teil der Workload **Desktopentwicklung mit C++** installiert.

![CMake-Komponente in der Workload „Desktopentwicklung mit C++“](media/cmake-install.png)

## <a name="ide-integration"></a>IDE-Integration

Wenn Sie auf **Datei > Öffnen > Ordner** klicken, um einen Ordner zu öffnen, der eine CMakeLists.txt-Datei enthält, geschieht Folgendes:

- Visual Studio fügt ein **CMake**-Menüelement zum Hauptmenü hinzu, das Befehle für das Anzeigen und Bearbeiten von CMake-Skripts enthält.
- Der **Projektmappen-Explorer** zeigt die Ordnerstruktur und die Dateien an.
- Visual Studio führt „CMake.exe“ aus und generiert den CMake-Cache für die *Standardkonfiguration* (x86 Debug). Die CMake-Befehlszeile wird im **Ausgabefenster** zusammen mit zusätzlichen Ausgaben von CMake angezeigt.  **Visual Studio 2017, Version 15.7 und höher:** Die automatische Cachegenerierung kann im Dialogfeld **Extras > Optionen > CMake > Allgemein** deaktiviert werden.
- Im Hintergrund beginnt Visual Studio damit, die Quelldateien zu indizieren, um IntelliSense, das Durchsuchen von Informationen, das Refactoring und vieles mehr zu ermöglichen. Während Sie arbeiten, überwacht Visual Studio die Änderungen im Editor und auf dem Datenträger, damit der Index mit den Quellen synchron ist.

Sie können Ordner öffnen, die eine beliebige Anzahl von CMake-Projekten enthalten. Visual Studio erkennt und konfiguriert alle CMakeLists.txt-Stammdateien in Ihrem Arbeitsbereich. CMake-Vorgänge (Konfigurieren, Erstellen, Debuggen) sowie C++ IntelliSense und das Durchsuchen sind für alle CMake-Projekte in Ihrem Arbeitsbereich verfügbar.

![CMake-Projekte mit mehreren Stammdateien](media/cmake-multiple-roots.png)

**Visual Studio 2017, Version 15.7 und höher:** Sie können die Projekte auch logisch strukturiert nach Zielen anzeigen. Wählen Sie in der Dropdownliste der Symbolleiste des **Projektmappen-Explorers** die Option **Zielansicht** aus:

![Schaltfläche für CMake-Zielansicht](media/cmake-targets-view.png)

## <a name="import-an-existing-cache"></a>Importieren eines vorhandenen Caches

Wenn Sie eine vorhandene Datei „CMakeLists.txt“ importieren, extrahiert Visual Studio benutzerdefinierte Variablen automatisch und erstellt eine vorab mit Daten aufgefüllte Datei [CMakeSettings.json](#cmake_settings), die auf diesen basiert. Der ursprüngliche Cache wird nicht geändert und kann weiterhin über die Befehlszeile oder über das Tool bzw. die IDE verwendet werden, mit dem bzw. der er generiert wurde. Die neue CMakeSettings.json-Datei wird bei der CMakeLists.txt-Stammdatei des Projekts platziert. Visual Studio generiert einen neuen Cache, der auf der Einstellungsdatei basiert.

**Visual Studio 2017, Version 15.7 und höher:** Die automatische Cachegenerierung kann im Dialogfeld **Extras > Optionen > CMake > Allgemein** außer Kraft gesetzt werden.

Nicht der gesamte Inhalt des Caches wird importiert.  Eigenschaften wie der Generator und der Speicherort des Compilers werden durch die Standardwerte ersetzt, die in der IDE bekanntermaßen funktionieren.

### <a name="to-import-an-existing-cache"></a>Importieren eines vorhandenen Caches

1. Klicken Sie im Hauptmenü auf **Datei > Öffnen > CMake**:

   ![Öffnen von CMake](media/cmake-file-open.png "Datei > Öffnen > CMake")

   Dadurch wird der Assistent **CMake-Projekt aus Cache importieren** gestartet.

2. Navigieren Sie zur CMakeCache.txt-Datei, die Sie importieren möchten, und klicken Sie dann auf **OK**. Der Assistent **CMake-Projekt aus Cache importieren** wird angezeigt:

   ![Importieren eines CMake-Caches](media/cmake-import-wizard.png "Öffnen des Assistenten zum Importieren von CMake-Caches")

   Wenn der Assistent abgeschlossen ist, wird die neue Datei „CMakeCache.txt“ im **Projektmappen-Explorer** neben der Stammdatei „CMakeLists.txt“ in Ihrem Projekt geöffnet.

## <a name="building-cmake-projects"></a>Erstellen von CMake-Projekten

Folgende Optionen stehen Ihnen zum Erstellen eines CMake-Projekts zur Verfügung:

1. Wählen Sie das Ziel aus der Dropdownliste **Debuggen** aus, und drücken Sie **F5**, oder klicken Sie auf die Schaltfläche **Ausführen** (grünes Dreieck). Das Projekt wird genau wie eine Visual Studio-Projektmappe zunächst erstellt.
1. Klicken Sie mit der rechten Maustaste auf CMakeLists.txt, und wählen Sie im Kontextmenü **Erstellen** aus. Wenn mehrere Ziele in Ihrer Ordnerstruktur vorhanden sind, können Sie auswählen, den Build für alle oder nur für ein bestimmtes Ziel durchzuführen.
1. Alternativ können Sie im Hauptmenü auf **Erstellen > Projektmappe erstellen** klicken bzw. **F7** oder **STRG+UMSCHALT+B** drücken. Stellen Sie sicher, dass ein CMake-Ziel bereits in der Dropdownliste **Startelement** auf der Symbolleiste **Allgemein** ausgewählt ist.

![CMake-Menübefehl „Erstellen“](media/cmake-build-menu.png "CMake build menu command")

Wenn ein Visual Studio-Generator als aktive Konfiguration ausgewählt ist, wird „MSBuild.exe“ über `-m -v:minimal`-Argumente aufgerufen. In der CMakeSettings.json-Datei können Sie zusätzliche Befehlszeilenargumente angeben, die über die `buildCommandArgs`-Eigenschaft an das Buildsystem übergeben werden sollen, um den Build anzupassen:

```json
"buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
```

Erwartungsgemäß werden die Buildergebnisse im **Ausgabefenster** und in der **Fehlerliste** angezeigt.

![CMake-Buildfehler](media/cmake-build-errors.png "CMake build errors")

In einem Ordner mit mehreren Buildzielen können Sie das Element **Erstellen** im Menü **CMake** oder das Kontextmenü **CMakeLists.txt** auswählen, um das CMake-Ziel für den Build anzugeben. Wenn Sie **STRG+UMSCHALT+B** in einem CMake-Projekt drücken, wird das derzeit aktive Dokument erstellt.

## <a name="debug-the-project"></a>Debuggen des Projekts

Wenn Sie ein CMake-Projekt debuggen möchten, wählen Sie die gewünschte Konfiguration aus, und drücken Sie **F5**. Klicken Sie alternativ auf die Schaltfläche **Ausführen** auf der Symbolleiste. Wenn die Schaltfläche **Ausführen** „Startelement auswählen“ anzeigt, klicken Sie auf den Dropdownpfeil, und wählen Sie das Ziel aus, das ausgeführt werden soll. (In einem CMake-Projekt ist die Option „Aktuelles Dokument“ nur für CPP-Dateien gültig.)

![CMake-Schaltfläche „Ausführen“](media/cmake-run-button.png "Cmake run button")

Durch **Ausführen** oder **F5** wird das Projekt zunächst erstellt, wenn seit dem vorherigen Build Änderungen vorgenommen wurden.

## <a name="configure-cmake-debugging-sessions"></a>Konfigurieren von CMake-Debugsitzungen

Alle ausführbaren CMake-Ziele werden in der Dropdownliste **Startelement** auf der Symbolleiste **Allgemein** angezeigt. Wählen Sie eines aus, und starten Sie den Debugger, um eine Debugsitzung zu starten.

![CMake-Dropdownliste „Startelement“](media/cmake-startup-item-dropdown.png "CMake startup item dropdown")

Sie können eine Debugsitzung ebenfalls über die CMake-Menüs starten.

Wenn Sie die Debugeinstellungen für ein beliebiges ausführbares CMake-Ziel in Ihrem Projekt anpassen möchten, klicken Sie mit der rechten Maustaste auf die entsprechende CMakeLists.txt-Datei, und wählen Sie **Debug- und Starteinstellungen** aus. Wenn Sie im Untermenü ein CMake-Ziel auswählen, wird eine Datei namens „launch.vs.json“ erstellt. Die Datei wird vorab mit Informationen zum ausgewählten CMake-Ziel aufgefüllt, und Sie können zusätzliche Parameter wie Programmargumente oder den Debuggertyp angeben. Wenn Sie in einer CMakeSettings.json-Datei auf einen Schlüssel verweisen möchten, stellen Sie diesem „CMake.“ in launch.vs.json voran. In folgendem Beispiel wird eine einfache launch.vs.json-Datei dargestellt, die den Wert des Schlüssels „remoteCopySources“ aus der Datei „CMakeSettings.json“ für die derzeit ausgewählte Konfiguration abruft:

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "default",
      "project": "CMakeLists.txt",
      "projectTarget": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "name": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "args": ["${cmake.remoteCopySources}"]
    }
  ]
}
```

Sobald Sie die Datei „launch.vs.json“ speichern, wird ein Eintrag mit dem neuen Namen in der Dropdownliste **Startelement** erstellt. Indem Sie die Datei „launch.vs.json“ bearbeiten, können Sie beliebig viele Debugkonfigurationen für beliebig viele CMake-Ziele erstellen.

**Visual Studio 2017, Version 15.4:** „launch.vs.json“ unterstützt Variablen, die in „CMakeSettings.json“ (siehe unten) deklariert werden und auf die aktuell ausgewählte Konfiguration angewendet werden können. Sie verfügt ebenfalls über einen Schlüssel namens „currentDir“, der das aktuelle Verzeichnis der gestarteten App festlegt:

```json
{
  "type": "default",
  "project": "CMakeLists.txt",
  "projectTarget": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
  "name": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
  "currentDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}"
}
```

Wenn Sie die App ausführen, entspricht der Wert von `currentDir` etwa Folgendem:

```cmd
C:\Users\satyan\7f14809a-2626-873e-952e-cdf038211175\
```

## <a name="editing-cmakeliststxt-files"></a>Bearbeiten von CMakeLists.txt-Dateien

Wenn Sie eine CMakeLists.txt-Datei bearbeiten möchten, klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei, und wählen Sie **Öffnen** aus. Wenn Sie Änderungen an der Datei vornehmen, wird eine gelbe Statusleiste angezeigt, die Sie darüber informiert, dass IntelliSense ein Update durchführen möchte und die Möglichkeit bietet, den Updatevorgang abzubrechen. Weitere Informationen zu „CMakeLists.txt“ finden Sie unter [CMake documentation (CMake-Dokumentation)](https://cmake.org/documentation/).

   ![Bearbeiten der Datei „CMakeLists.txt“](media/cmake-cmakelists.png "CMakeLists.txt file editing")

Sobald Sie die Datei speichern, wird der Konfigurationsschritt automatisch erneut ausgeführt. Dieser zeigt Informationen im **Ausgabefenster** an. Fehler und Warnungen werden in der **Fehlerliste** oder im **Ausgabefenster** angezeigt. Doppelklicken Sie auf einen Fehler in der **Fehlerliste**, um zur problematischen Zeile in CMakeLists.txt zu navigieren.

   ![Fehler in der Datei „CMakeLists.txt“](media/cmake-cmakelists-error.png "CMakeLists.txt file errors")

## <a name="cmake_settings"></a> CMake-Einstellungen und benutzerdefinierte Konfigurationen

Standardmäßig stellt Visual Studio sechs CMake-Standardkonfigurationen ("x86-Debug", "x86-Release", "x64-Debug", "x64-Release", "Linux-Debug" and "Linux-Release") bereit. Diese Konfigurationen definieren, wie „CMake.exe“ aufgerufen wird, um den CMake-Cache für ein bestimmtes Projekt zu erstellen. Wenn Sie diese Konfigurationen ändern oder eine neue benutzerdefinierte Konfiguration erstellen möchten, klicken Sie auf **CMake > CMake-Einstellungen ändern**, und wählen Sie die CMakeLists.txt-Datei aus, für die die Einstellungen gelten. Der Befehl **CMake-Einstellungen** ändern ist ebenfalls über das Kontextmenü der Datei im **Projektmappen-Explorer** verfügbar. Dieser Befehl erstellt eine CMakeSettings.json-Datei im Projektordner. Diese Datei wird verwendet, um die CMake-Cachedatei erneut zu erstellen, z.B. nach einem **Bereinigungsvorgang**.

   ![CMake-Hauptmenübefehl für das Ändern von Einstellungen](media/cmake-change-settings.png)

JSON-IntelliSense unterstützt Sie beim Bearbeiten der CMakeSettings.json-Datei:

   ![JSON-IntelliSense für CMake](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

Im Folgenden wird eine Beispielkonfiguration veranschaulicht, die Sie als Ausgangspunkt zum Erstellen einer eigenen Konfiguration in „CMakeSettings.json“ verwenden können:

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

1. **name:** der Name, der in der Dropdownliste für die C++-Konfiguration angezeigt wird Dieser Eigenschaftswert kann ebenfalls als Makro (`${name}`) verwendet werden, um andere Eigenschaftswerte anzugeben. Ein Beispiel finden Sie in der **buildRoot**-Definition in „CMakeSettings.json“.

1. **generator:** führt eine Zuordnung für die Option **-G** durch und gibt den Generator an, der verwendet werden soll Diese Eigenschaft kann ebenfalls als Makro (`${generator}`) verwendet werden, um andere Eigenschaftswerte anzugeben. Visual Studio unterstützt derzeit folgende CMake-Generatoren:

    - "Ninja"
    - "Visual Studio 14 2015"
    - "Visual Studio 14 2015 ARM"
    - "Visual Studio 14 2015 Win64"
    - "Visual Studio 15 2017"
    - "Visual Studio 15 2017 ARM"
    - "Visual Studio 15 2017 Win64"

Da Ninja für schnelle Buildgeschwindigkeiten statt für Flexibilität und Funktionalität entwickelt wurde, ist dieser als Standardwert festgelegt. Einige CMake-Projekte können jedoch mit Ninja keinen ordnungsgemäßen Build durchführen. In diesem Fall können Sie CMake anweisen, stattdessen ein Visual Studio-Projekt zu erstellen.

Öffnen Sie „CMakeSettings.json“ über das Hauptmenü, indem Sie auf **CMake > CMake-Einstellungen ändern** klicken, um einen Visual Studio-Generator anzugeben. Löschen Sie „Ninja“, und geben Sie „V“ ein. Dadurch wird IntelliSense aktiviert, und Sie können den gewünschten Generator auswählen.

1. **buildRoot:** führt eine Zuordnung für die Option **-DCMAKE_BINARY_DIR** und gibt an, wo der CMake-Cache erstellt wird Wenn der Ordner noch nicht vorhanden ist, wird dieser erstellt.

1. **variables:** enthält ein Name/Wert-Paar von CMake-Variablen, die als **-D** *_name_=_value_* an CMake übergeben werden. Wenn die Buildanweisungen Ihres CMake-Projekts das direkte Hinzufügen aller Variablen zur CMake-Cachedatei festlegen, wird empfohlen, diese stattdessen hier hinzuzufügen. Im folgenden Beispiel wird gezeigt, wie Sie die Name-Wert-Paare im Code angeben können:

```json
"variables": [
    {
      "name": "CMAKE_CXX_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe"
    },
    {
      "name": "CMAKE_C_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe"
    }
  ]
```

1. **cmakeCommandArgs:** gibt alle zusätzlichen Optionen an, die an „CMake.exe“ übergeben werden sollen

2. **configurationType:** definiert den Typ der Buildkonfiguration für den ausgewählten Generator Derzeit werden die Werte "Debug", "MinSizeRel", "Release" und "RelWithDebInfo" unterstützt.

3. **ctestCommandArgs:** gibt zusätzliche Optionen an, die beim Ausführen von Tests an CTest übergeben werden sollen.

4. **ctestCommandArgs:** gibt zusätzliche Optionen an, die an das zugrunde liegende Buildsystem übergeben werden sollen. Beispielsweise wird beim Übergeben von „-v“ mithilfe des Ninja-Generators erzwungen, dass Ninja Befehlszeilen ausgibt.

### <a name="environment-variables"></a>Umgebungsvariablen

„CMakeSettings.json“ unterstützt ebenfalls die Verwendung von Umgebungsvariablen in sämtlichen zuvor erwähnten Eigenschaften. Die Syntax zum Erweitern der Umgebungsvariable %FOO% ist `${env.FOO}`.
Sie haben in dieser Datei ebenfalls Zugriff auf integrierte Makros:

- `${workspaceRoot}`: stellt den vollständigen Pfad des Arbeitsbereichsordners bereit
- `${workspaceHash}`: Hash des Speicherorts für den Arbeitsbereich; nützlich für das Erstellen eines eindeutigen Bezeichners für den aktuellen Arbeitsbereich (z.B. für die Verwendung in Ordnerpfaden)
- `${projectFile}`: der vollständige Pfad der CMakeLists.txt-Stammdatei
- `${projectDir}`: der vollständige Pfad des Ordners der CMakeLists.txt-Stammdatei
- `${thisFile}`: der vollständige Pfad der CMakeSettings.json-Datei
- `${name}`: der Name der Konfiguration
- `${generator}`: der Name des CMake-Generators, der in dieser Konfiguration verwendet wurde

### <a name="ninja-command-line-arguments"></a>Ninja-Befehlszeilenargumente

Wenn keine Ziele festgelegt sind, wird das Standardziel erstellt (siehe Anleitung).

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|Option|Beschreibung |
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

### <a name="inherited-environments-visual-studio-2017-version-155"></a>Geerbte Umgebungen (Visual Studio 2017 Version 15.5)

„CMakeSettings.json“ unterstützt nun geerbte Umgebungen. Durch dieses Feature können Sie Standardumgebungen vererben und benutzerdefinierte Umgebungsvariablen erstellen, die bei der Ausführung an „CMake.exe“ übergeben werden.

```json
  "inheritEnvironments": [ "msvc_x64_x64" ]
```

Das obige Beispiel entspricht der Ausführung der **Developer-Eingabeaufforderung für Visual Studio 2017** mit den Argumenten **-arch=amd64 -host_arch=amd64**.

In der folgenden Tabelle werden die Standardwerte gezeigt:

|Kontextname|Beschreibung |
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

In „CMakeSettings.json“ können Sie benutzerdefinierte Umgebungsvariablen global oder pro Konfiguration in der Eigenschaft **environments** definieren. In folgendem Beispiel wird eine globale Variable (**BuildDir**) definiert, die in den Konfigurationen „x86-Debug“ und „x64-Debug“ geerbt wird. Jede Konfiguration verwendet die Variable, um den Wert für die Eigenschaft **buildRoot** der Konfiguration anzugeben. Beachten Sie ebenfalls, wie jede Konfiguration die Eigenschaft **inheritEnvironments** verwendet, um eine Variable anzugeben, die nur für diese Konfiguration gilt.

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

Im nächsten Beispiel definiert die Konfiguration „x86-Debug“ ihren eigenen Wert für die Eigenschaft **BuildDir**. Dieser Wert überschreibt den Wert, der von der globalen Eigenschaft **BuildDir** festgelegt wurde, sodass **buildRoot** zu `D:\custom-builddir\x86-Debug` ausgewertet wird.

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
          "BuildDir": "D:\\custom-builddir",
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

## <a name="cmake-configure-step"></a>CMake-Konfigurationsschritt

Wenn wichtige Änderungen an den Dateien „CMakeSettings.json“ oder „CMakeLists.txt“ vorgenommen werden, führt Visual Studio den CMake-Konfigurationsschritt automatisch erneut aus. Wenn der Konfigurationsschritt ohne Fehler abgeschlossen wird, sind die gesammelten Informationen in C++ IntelliSense, in den C++-Sprachdiensten sowie in Build- und Debugvorgängen verfügbar.

Wenn mehrere CMake-Projekte den gleichen CMake-Konfigurationsnamen (z.B. „x86-Debug“) verwenden, werden alle konfiguriert und erstellt (in einem eigenen Stammordner für den Build), wenn diese Konfiguration ausgewählt ist. Sie können die Ziele aller CMake-Projekte debuggen, die in dieser CMake-Konfiguration enthalten sind.

   ![CMake-Menüelement „Nur erstellen“](media/cmake-build-only.png "CMake Build Only menu item")

Wenn Sie Build- und Debugsitzungen auf eine Teilmenge der Projekte im Arbeitsbereich begrenzen möchten, erstellen Sie eine neue Konfigurationen mit einem eindeutigen Namen in der Datei „CMakeSettings.json“, und wenden Sie sie nur auf diese Projekte an. Wenn diese Konfiguration ausgewählt ist, werden die IntelliSense-, Build- und Debugbefehle nur für die angegebenen Projekte aktiviert.

## <a name="troubleshooting-cmake-cache-errors"></a>Behandlung von CMake-Cachefehlern

Wenn Sie weitere Informationen zum Status des CMake-Caches benötigen, um ein Problem zu diagnostizieren, öffnen Sie das Hauptmenü **CMake** oder das Kontextmenü **CMakeLists.txt** im **Projektmappen-Explorer**, um einen der folgenden Befehle auszuführen:

- **Cache anzeigen** öffnet die Datei „CMakeCache.txt“ aus dem Stammordner des Builds im Editor. (Alle Änderungen, die Sie hier an „CMakeCache.txt“ vornehmen, werden verworfen, wenn Sie den Cache bereinigen. Weitere Informationen dazu, wie die Änderungen nach dem Löschen des Caches beibehalten werden, finden Sie in diesem Artikel unter [CMake-Einstellungen und benutzerdefinierte Konfigurationen](#cmake_settings).)

- **Cacheordner öffnen** öffnet ein Explorer-Fenster zum Stammordner des Builds.

- **Cache bereinigen** löscht den Stammordner des Builds, sodass der nächste CMake-Konfigurationsschritt mit einem leeren Cache beginnt.

- **Cache generieren** erzwingt die Ausführung des Schritts „Generieren“, auch wenn Visual Studio die Umgebung für aktuell hält.

**Visual Studio 2017, Version 15.7 und höher:** Die automatische Cachegenerierung kann im Dialogfeld **Extras > Optionen > CMake > Allgemein** deaktiviert werden.

## <a name="single-file-compilation"></a>Kompilierung einzelner Dateien

**Visual Studio 2017, Version 15.7 und höher:** Klicken Sie zum Erstellen einer einzelnen Datei in einem CMake-Projekt mit der rechten Maustaste auf die Datei im **Projektmappen-Explorer**, und klicken Sie auf **Kompilieren**. Sie können die derzeit im Editor geöffnete Datei auch über das CMake-Hauptmenü erstellen:

![Kompilierung einzelner Dateien in CMake](media/cmake-single-file-compile.png)

## <a name="run-cmake-from-the-command-line"></a>Ausführen von CMake über die Befehlszeile
Wenn Sie CMake über den Visual Studio-Installer installiert haben, können Sie CMake über die Befehlszeile ausführen, indem Sie die folgenden Schritte ausführen:

1. Führen Sie die entsprechende Datei „vsdevcmd.bat“ (x86/x64) aus. Weitere Informationen finden Sie unter [Erstellen über die Befehlszeile](../build/building-on-the-command-line.md).
1. Wechseln Sie zu Ihrem Ausgabeordner.
1. Führen Sie CMake zum Erstellen/Konfigurieren Ihrer App aus.

