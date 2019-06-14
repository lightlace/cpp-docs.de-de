---
title: Anpassen von CMake-Buildeinstellungen in Visual Studio
ms.date: 05/16/2019
helpviewer_keywords:
- CMake build settings
ms.openlocfilehash: a00b18f163758be0238a05c4d2af3195014d79b0
ms.sourcegitcommit: fde637f823494532314790602c2819f889706ff6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/13/2019
ms.locfileid: "67042538"
---
# <a name="customize-cmake-build-settings"></a>Anpassen von CMake-Buildeinstellungen

::: moniker range="vs-2019"

In Visual Studio 2019 und höher können Sie mithilfe des **CMake-Einstellungs-Editors** Konfigurationen hinzufügen und ihre Einstellungen anpassen. Der Editor soll eine einfachere Alternative zur manuellen Bearbeitung der CMakeSettings.json-Datei bieten, aber wenn Sie es vorziehen, die Datei direkt zu bearbeiten, können Sie auf den Link **JSON bearbeiten** oben rechts im Editor klicken. 

Um den Editor zu öffnen, klicken Sie auf die Dropdownliste **Konfiguration** in der Hauptsymbolleiste, und wählen Sie **Konfigurationen verwalten** aus.

![Dropdownliste „CMake-Konfigurationen“](media/vs2019-cmake-manage-configurations.png)

Jetzt wird der **Einstellungs-Editor** mit den installierten Konfigurationen auf der linken Seite angezeigt. 

![CMake-Einstellungs-Editor](media/cmake-settings-editor.png)

Visual Studio bietet standardmäßig zwei Konfigurationen: `x64-Debug` und `x86-Debug`. Sie können zusätzliche Konfigurationen hinzufügen, indem Sie auf das grüne Pluszeichen klicken. Die Einstellungen, die Sie im Editor sehen, können sich je nach ausgewählter Konfiguration unterscheiden.

Die Optionen, die Sie im Editor auswählen, werden in eine Datei mit dem Namen „CMakeSettings.json“ geschrieben. Diese Datei stellt Befehlszeilenargumente und Umgebungsvariablen zur Verfügung, die beim Erstellen der Projekte an CMake übergeben werden. Visual Studio ändert „CMakeLists.txt“ nie automatisch; mithilfe von „CMakeSettings.json“ können Sie den Build durch Visual Studio anpassen, ohne die CMake-Projektdateien zu bearbeiten, so dass andere in Ihrem Team sie mit Tools ihrer Wahl nutzen können.

## <a name="cmake-general-settings"></a>CMake – allgemeine Einstellungen

Die folgenden Einstellungen sind unter der Überschrift **Allgemein** verfügbar:

### <a name="configuration-name"></a>Konfigurationsname

Entspricht der Einstellung **name**. Die ist der Name, der in der Dropdownliste für die C++-Konfiguration angezeigt wird. Sie können das `${name}`-Makro verwenden, um weitere Eigenschaftswerte wie etwa Pfade zu verfassen.


### <a name="configuration-type"></a>Konfigurationstyp

Entspricht der Einstellung **configurationType**. Definiert den Typ der Buildkonfiguration für den ausgewählten Generator. Derzeit werden die Werte "Debug", "MinSizeRel", "Release" und "RelWithDebInfo" unterstützt.

### <a name="toolset"></a>Toolset

Entspricht der Einstellung **inheritedEnvironments**. Definiert die Compilerumgebung, die zum Erstellen der ausgewählten Konfiguration verwendet wird. Die unterstützten Werte hängen von der Art der Konfiguration ab. Um eine benutzerdefinierte Umgebung zu erstellen, klicken Sie auf den Link **JSON bearbeiten** in der oberen rechten Ecke des Einstellungs-Editors, und bearbeiten Sie die CMakeSettings.json-Datei direkt.

### <a name="cmake-toolchain-file"></a>CMake-Toolkettendatei

Pfad zur CMake-Toolkettendatei. Wird an CMake als „-DCMAKE_TOOLCHAIN_FILE = \<dateipfad>“ übergeben.

### <a name="build-root"></a>Buildstamm

Entspricht **buildRoot**. Ist dem Schalter **-DCMAKE_BINARY_DIR** zugeordnet und gibt an, wo der CMake-Cache erstellt wird. Wenn der Ordner noch nicht vorhanden ist, wird dieser erstellt.

## <a name="command-arguments"></a>Befehlsargumente

Die folgenden Einstellungen sind unter der Überschrift **Befehlsargumente** verfügbar:

### <a name="cmake-command-arguments"></a>CMake-Befehlsargumente

Entspricht **cmakeCommandArgs**. Gibt alle zusätzlichen Schalter an, die Sie an „CMake.exe“ übergeben möchten.

### <a name="build-command-arguments"></a>Build-Befehlsargumente

Entspricht **buildCommandArgs**: Gibt zusätzliche Schalter an, die dem zugrundeliegenden Buildsystem übergeben werden sollen. Beispielsweise wird beim Übergeben von „-v“ mithilfe des Ninja-Generators erzwungen, dass Ninja Befehlszeilen ausgibt.


### <a name="ctest-command-arguments"></a>CTest-Befehlsargumente

Entspricht **ctestCommandArgs**: Gibt zusätzliche Schalter an, die beim Ausführen von Tests an CTest übergeben werden.

## <a name="general-settings-for-remote-builds"></a>Allgemeine Einstellungen für Remotebuilds

Für Konfigurationen wie Linux, die Remotebuilds verwenden, sind ferner die folgenden Einstellungen verfügbar:

### <a name="rsync-command-arguments"></a>rsync-Befehlsargumente

Geben Sie alle Befehlsargumente an, die an rsync übergeben werden sollen. 

## <a name="cmake-variables-and-cache"></a>CMake-Variablen und -Cache

Mithilfe dieser Einstellungen können Sie CMake-Variablen festlegen und sie in „CMakeSettings.json“ speichern. Sie werden zur Erstellungszeit an CMake übergeben und setzen die in der Datei „CMakeLists.txt“ vorhandenen Werte außer Kraft. Sie können diesen Abschnitt in der gleichen Weise verwenden, in der Sie das CMakeGUI verwenden, um eine Liste aller für die Bearbeitung verfügbaren CMake-Variablen anzuzeigen. Klicken Sie auf die Schaltfläche **Speichern und Cache generieren**, um eine Liste aller für die Bearbeitung verfügbaren CMake-Variablen anzuzeigen, einschließlich erweiterter Variablen (mithilfe des CMakeGUI). Sie können die Liste nach dem Variablennamen filtern. 

Entspricht **variables:** enthält ein Name/Wert-Paar von CMake-Variablen, die als **-D** *_name_=_value_* an CMake übergeben werden. Wenn die Buildanweisungen Ihres CMake-Projekts das direkte Hinzufügen aller Variablen zur CMake-Cachedatei festlegen, wird empfohlen, diese stattdessen hier hinzuzufügen.

## <a name="advanced-settings"></a>Erweiterte Einstellungen

### <a name="cmake-generator"></a>CMake-Generator

Entspricht **generator**: ist dem CMake-Schalter **-G** zugeordnet und gibt den Generator an, der verwendet werden soll. Diese Eigenschaft kann ebenfalls als Makro (`${generator}`) beim Erstellen anderer Eigenschaftswerte verwendet werden. Visual Studio unterstützt derzeit folgende CMake-Generatoren:

  - "Ninja"
  - "Unix Makefiles"
  - "Visual Studio 16 2019"
  - "Visual Studio 16 2019 Win64"
  - "Visual Studio 16 2019 ARM"
  - "Visual Studio 15 2017"
  - "Visual Studio 15 2017 Win64"
  - "Visual Studio 15 2017 ARM"
  - "Visual Studio 14 2015"
  - "Visual Studio 14 2015 Win64"
  - "Visual Studio 14 2015 ARM"
  
  Da Ninja für schnelle Buildgeschwindigkeiten statt für Flexibilität und Funktionalität entwickelt wurde, ist dieser als Standardwert festgelegt. Einige CMake-Projekte können jedoch mit Ninja keinen ordnungsgemäßen Build durchführen. In diesem Fall können Sie CMake anweisen, stattdessen ein Visual Studio-Projekt zu erstellen.

### <a name="intellisense-mode"></a>IntelliSense-Modus

Um eine präzise Funktion von IntelliSense zu erreichen, legen Sie dies auf den passenden Wert für Ihr Projekt fest.

### <a name="install-directory"></a>Installationsverzeichnis

Das Verzeichnis, in dem CMake die von ihm erstellten Ziele installiert.

### <a name="cmake-executable"></a>Ausführbare CMake-Datei

Der vollständige Pfad zur ausführbaren CMake-Datei, einschließlich des Dateinamens und der Erweiterung. Geben Sie für Remotebuilds den CMake-Speicherort auf dem Remotecomputer an.

Für Konfigurationen wie Linux, die Remotebuilds verwenden, sind ferner die folgenden Einstellungen verfügbar:

### <a name="remote-cmakeliststxt-root"></a>Remoteverzeichnis der Stammdatei „CMakeLists.txt“

Das Verzeichnis auf dem Remotecomputer, das die Stammdatei „CMakeLists.txt“ enthält.

### <a name="remote-install-root"></a>Installationsstammverzeichnis auf dem Remotesystem

Das Verzeichnis auf dem Remotecomputer, in dem CMake Zieldateien installiert.

### <a name="remote-copy-sources"></a>Quellen auf Remotesystem kopieren

Gibt an, ob Quelldateien auf den Remotecomputer kopiert werden sollen, und ermöglicht Ihnen, anzugeben, ob rsync oder sftp verwendet werden soll. 

## <a name="directly-edit-cmakesettingsjson"></a>„CMakeSettings.json“ direkt bearbeiten

Sie können `CMakeSettings.json` auch direkt bearbeiten, um benutzerdefinierte Konfigurationen zu erstellen. Der **Einstellungs-Editor** weist eine Schaltfläche **JSON bearbeiten** oben rechts auf, mit der die Datei zur Bearbeitung geöffnet wird. 

Das folgende Beispiel zeigt eine Beispielkonfiguration, die Sie als Ausgangspunkt verwenden können:

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

JSON-IntelliSense unterstützt Sie beim Bearbeiten der Datei `CMakeSettings.json`:

   ![JSON-IntelliSense für CMake](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

Der JSON-Editor informiert Sie auch, wenn Sie inkompatible Einstellungen auswählen.

Weitere Informationen zu den einzelnen Eigenschaften in der Datei finden Sie in der [CMakeSettings.json-Schemareferenz](cmakesettings-reference.md).

::: moniker-end

::: moniker range="<=vs-2017"

Visual Studio 2017 bietet verschiedene CMake-Konfigurationen, die definieren, wie „CMake.exe“ aufgerufen wird, um den CMake-Cache für ein bestimmtes Projekt zu erstellen. Klicken Sie zum Hinzufügen einer neuen Konfiguration in der Symbolleiste auf die Konfigurations-Dropdownliste, und wählen Sie **Konfigurationen verwalten...** aus:

   ![CMake: „Konfigurationen verwalten...“](media/cmake-manage-configurations.png)

Sie können aus der Liste vordefinierter Konfigurationen wählen:

   ![Vordefinierte CMake-Konfigurationen](media/cmake-configurations.png)

Wenn Sie zum ersten Mal eine Konfiguration auswählen, erstellt Visual Studio im Stammordner des Projekts eine `CMakeSettings.json`-Datei. Diese Datei wird verwendet, um die CMake-Cachedatei erneut zu erstellen, z.B. nach einem **Bereinigungsvorgang**. 

Klicken Sie zum Hinzufügen einer zusätzlichen Konfiguration mit der rechten Maustaste auf `CMakeSettings.json`, und wählen Sie **Konfiguration hinzufügen** aus. 

   ![CMake: „Konfiguration hinzufügen“](media/cmake-add-configuration.png "CMake: „Konfiguration hinzufügen“")

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

JSON-IntelliSense unterstützt Sie beim Bearbeiten der Datei `CMakeSettings.json`:

   ![JSON-IntelliSense für CMake](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

Weitere Informationen zu den einzelnen Eigenschaften in der Datei finden Sie in der [CMakeSettings.json-Schemareferenz](cmakesettings-reference.md).

::: moniker-end

## <a name="see-also"></a>Siehe auch

[CMake Projects in Visual Studio (CMake-Projekte in Visual Studio)](cmake-projects-in-visual-studio.md)<br/>
[Konfigurieren eines Linux CMake-Projekts](../linux/cmake-linux-project.md)<br/>
[Herstellen einer Verbindung mit Ihrem Linux-Remotecomputer](../linux/connect-to-your-remote-linux-computer.md)<br/>
[Konfigurieren von CMake-Debugsitzungen](configure-cmake-debugging-sessions.md)<br/>
[Bereitstellen, Ausführen und Debuggen Ihres Linux-Projekts](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake predefined configuration reference (Referenz für vordefinierte CMake-Konfigurationen)](cmake-predefined-configuration-reference.md)<br/>
