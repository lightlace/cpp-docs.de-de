---
title: Anpassen von CMake-Buildeinstellungen in Visual Studio
ms.date: 04/25/2019
helpviewer_keywords:
- CMake build settings
ms.openlocfilehash: 20ed066f71a5c8c3acb00ef5923fa5c9f16ac229
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877158"
---
# <a name="customize-cmake-build-settings"></a>Anpassen von CMake-Buildeinstellungen

::: moniker range="vs-2019"

In Visual Studio-2019 und höher können Sie zum Hinzufügen von Konfigurationen und deren Einstellungen anpassen, indem die **CMake-einstellungs-Editor**. Der Editor eine einfachere Alternative zu der Datei "cmakesettings.JSON" manuell bearbeitet werden soll, wenn Sie die Datei direkt bearbeiten möchten, Sie können jedoch auf die **JSON bearbeiten** -Link in der oberen rechten Ecke der Editor. 

Um den Editor zu öffnen, klicken Sie auf die **Konfiguration** -Dropdown in der Hauptsymbolleiste auf, und wählen Sie **Konfigurationen verwalten**.

![CMake-Konfigurationen-Dropdownliste](media/vs2019-cmake-manage-configurations.png)

Nun Sie sehen die **Einstellungs-Editor** mit den installierten Konfigurationen auf der linken Seite. 

![CMake-einstellungs-editor](media/cmake-settings-editor.png)

Visual Studio bietet zwei Konfigurationen standardmäßig: `x64-Debug` und `x86-Debug`. Sie können zusätzliche Konfigurationen hinzufügen, indem Sie auf das grüne Pluszeichen. Die Einstellungen, die Sie im Editor finden Sie unter variieren, je nachdem, die welche Konfiguration ausgewählt ist.

Die Optionen, die Sie im Editor auswählen, werden in eine Datei namens "cmakesettings.JSON" geschrieben. Diese Datei enthält die Befehlszeilenargumente und Umgebungsvariablen, die an CMake übergeben werden, wenn Sie die Projekte erstellen. Visual Studio ändert die Datei "cmakelists.txt" nie automatisch; Mithilfe von "cmakesettings.JSON" können Sie den Build über Visual Studio anpassen, während die CMake-Projektdateien unveränderten, sodass andere Mitglieder Ihres Teams diese mit beliebigen Tools nutzen können, die sie verwenden.

## <a name="cmake-general-settings"></a>Allgemeine CMake-Einstellungen

Die folgenden Einstellungen stehen zur Verfügung, unter dem **allgemeine** Überschrift:

### <a name="configuration-name"></a>Konfigurationsname

Entspricht der **Namen** festlegen. Dies ist der Name in der C++ Dropdownliste "Konfiguration". Sie können die `${name}` Makro, um andere Eigenschaftswerte wie z. B. Pfade zu erstellen.


### <a name="configuration-type"></a>Konfigurationstyp

Entspricht der **ConfigurationType** festlegen. Definiert den Typ des Build-Konfiguration für den ausgewählten Generator. Derzeit werden die Werte "Debug", "MinSizeRel", "Release" und "RelWithDebInfo" unterstützt.

### <a name="toolset"></a>Toolset

Entspricht der **InheritedEnvironments** festlegen. Definiert die Compiler-Umgebung, die zum Erstellen der ausgewählten Konfigurations verwendet werden. Unterstützte Werte hängen von der Art der Konfiguration ab. Um eine benutzerdefinierte Umgebung erstellen, klicken Sie auf die **JSON bearbeiten** -link in der oben rechts im Einstellungs-Editor und bearbeiten Sie die Datei "cmakesettings.JSON" direkt.

### <a name="cmake-toolchain-file"></a>CMake-toolkette-Datei

Pfad zur Datei CMake-toolkette. Übergeben an CMake als "-DCMAKE_TOOLCHAIN_FILE = \<" FilePath ">".

### <a name="build-root"></a>Erstellen von root

Entspricht **BuildRoot**. Ordnet **-DCMAKE_BINARY_DIR** wechseln, und gibt an, in dem die CMake-Cache erstellt wird. Wenn der Ordner noch nicht vorhanden ist, wird dieser erstellt.

## <a name="command-arguments"></a>Befehlsargumente

Die folgenden Einstellungen stehen zur Verfügung, unter dem **Befehlsargumente** Überschrift:

### <a name="cmake-command-arguments"></a>Befehlsargumente für CMake

Entspricht **CmakeCommandArgs**. Gibt zusätzlichen Schalter, die Sie an CMake.exe übergeben möchten.

### <a name="build-command-arguments"></a>Befehlsargumente erstellen

Entspricht **BuildCommandArgs**: Gibt zusätzliche Schalter für die Übergabe an den zugrunde liegenden Buildsystems. Beispielsweise wird beim Übergeben von „-v“ mithilfe des Ninja-Generators erzwungen, dass Ninja Befehlszeilen ausgibt.


### <a name="ctest-command-arguments"></a>CTest-Befehlsargumente

Entspricht**CtestCommandArgs**: Gibt zusätzliche Schalter an CTest übergeben werden soll, beim Ausführen von Tests.

## <a name="general-settings-for-remote-builds"></a>Allgemeine Einstellungen für die remote-builds

Für Konfigurationen wie Linux, die remote-Builds zu verwenden, sind auch die folgenden Einstellungen verfügbar:

### <a name="rsync-command-arguments"></a>Befehlsargumente rsync

Geben Sie Befehlsargumente an Rsync übergeben werden. 

## <a name="cmake-variables-and-cache"></a>CMake-Variablen und cache

Diese Einstellungen ermöglichen Ihnen das CMake-Variablen festlegen und speichern Sie sie in "cmakesettings.JSON". Sie werden an CMake übergeben werden, zum Zeitpunkt der Erstellung und überschreibt alle Werte in der Datei "CMakeLists.txt" sein können. Sie können in diesem Abschnitt auf die gleiche Weise verwenden, die Sie möglicherweise die CMakeGUI verwenden, um eine Liste aller verfügbaren so bearbeiten Sie CMake Variablen anzuzeigen. Klicken Sie auf die **speichern und Generieren von Cache** Schaltfläche zum Anzeigen einer Liste aller CMake-Variablen, die verfügbar sind, zu bearbeiten, einschließlich der erweiterten Variablen (pro der CMakeGUI). Sie können die Liste mit Variablen Namen filtern. 

Entspricht **Variablen**: enthält ein Name / Wert-Paar von CMake-Variablen, die als übergeben wird **-D** *_Namen_ =  _Wert_* an CMake. Wenn die Buildanweisungen Ihres CMake-Projekts das direkte Hinzufügen aller Variablen zur CMake-Cachedatei festlegen, wird empfohlen, diese stattdessen hier hinzuzufügen.

## <a name="advanced-settings"></a>Erweiterte Einstellungen

### <a name="cmake-generator"></a>Generator von CMake

Entspricht **Generator**: Ordnet die CMake **: Password-g** wechseln, und gibt an, der Generator verwendet werden. Diese Eigenschaft kann ebenfalls als Makro (`${generator}`) beim Erstellen anderer Eigenschaftswerte verwendet werden. Visual Studio unterstützt derzeit folgende CMake-Generatoren:

  - "Ninja"
  - "Makefiles Unix"
  - "Visual Studio 16 2019"
  - "Visual Studio 16 2019 Win64"
  - - "Visual Studio 16 2019 ARM"
  - "Visual Studio 15 2017"
  - "Visual Studio 15 2017 Win64"
  - "Visual Studio 15 2017 ARM"
  - "Visual Studio 14 2015"
  - "Visual Studio 14 2015 Win64"
  - "Visual Studio 14 2015 ARM"
  
  Da Ninja für schnelle Buildgeschwindigkeiten statt für Flexibilität und Funktionalität entwickelt wurde, ist dieser als Standardwert festgelegt. Einige CMake-Projekte können jedoch mit Ninja keinen ordnungsgemäßen Build durchführen. In diesem Fall können Sie CMake anweisen, stattdessen ein Visual Studio-Projekt zu erstellen.

### <a name="intellisense-mode"></a>IntelliSense-Modus

Legen Sie für genaue IntelliSense diese auf den entsprechenden Wert für das Projekt aus.

### <a name="install-directory"></a>Installationsverzeichnis

Das Verzeichnis, in dem CMake Ziele installiert wird, die sie erstellt.

### <a name="cmake-executable"></a>CMake-ausführbare Datei

Der vollständige Pfad zur ausführbaren CMake Datei, einschließlich Dateiname und Erweiterung. Geben Sie für remote-Builds den CMake-Speicherort auf dem Remotecomputer ein.

Für Konfigurationen wie Linux, die remote-Builds zu verwenden, sind auch die folgenden Einstellungen verfügbar:

### <a name="remote-cmakeliststxt-root"></a>Datei "cmakelists.txt" remotestamm

Das Verzeichnis auf dem Remotecomputer, der die Datei "cmakelists.txt" Stammdatei enthält.

### <a name="remote-install-root"></a>Remoteinstallation-Stamm

Das Verzeichnis auf dem Remotecomputer, in dem CMake Ziele installiert, werden soll.

### <a name="remote-copy-sources"></a>Remotekopie-Quellen

Gibt an, ob Quelldateien auf den Remotecomputer kopieren und können Sie angeben, ob Sie verwendet werden, Rsync oder Sftp. 

## <a name="directly-edit-cmakesettingsjson"></a>"Cmakesettings.JSON" direkt bearbeitet werden.

Sie können auch direkt bearbeiten, `CMakeSettings.json` , benutzerdefinierte Konfigurationen zu erstellen. Die **Einstellungs-Editor** verfügt über eine **JSON bearbeiten** -Schaltfläche in der oberen rechten Ecke, die die Datei zur Bearbeitung geöffnet wird. 

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

JSON-IntelliSense können Sie das Bearbeiten der `CMakeSettings.json` Datei:

   ![JSON-IntelliSense für CMake](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

Im JSON-Editor informiert auch, wenn Sie nicht kompatible Einstellungen auswählen.

Weitere Informationen zu den einzelnen Eigenschaften in der Datei finden Sie unter ["cmakesettings.JSON" Schemareferenz](cmakesettings-reference.md).

::: moniker-end

::: moniker range="<=vs-2017"

Visual Studio 2017 bietet mehrere CMake-Konfigurationen, die definieren, wie CMake.exe aufgerufen wird, um den CMake-Cache für ein bestimmtes Projekt zu erstellen. Klicken Sie zum Hinzufügen einer neuen Konfiguration in der Symbolleiste auf die Konfigurations-Dropdownliste, und wählen Sie **Konfigurationen verwalten...** aus:

   ![CMake: „Konfigurationen verwalten...“](media/cmake-manage-configurations.png)

Sie können aus der Liste vordefinierter Konfigurationen wählen:

   ![Vordefinierte CMake-Konfigurationen](media/cmake-configurations.png)

Wenn Sie zum ersten Mal eine Konfiguration auswählen, erstellt Visual Studio im Stammordner des Projekts eine `CMakeSettings.json`-Datei. Diese Datei wird verwendet, um die CMake-Cachedatei erneut zu erstellen, z.B. nach einem **Bereinigungsvorgang**. 

Klicken Sie zum Hinzufügen einer zusätzlichen Konfiguration mit der rechten Maustaste auf `CMakeSettings.json`, und wählen Sie **Konfiguration hinzufügen** aus. 

   ![CMake: „Konfiguration hinzufügen“](media/cmake-add-configuration.png "CMake: „Konfiguration hinzufügen“")

Sie können die Datei auch mithilfe des **Editors für CMake-Einstellungen** bearbeiten. Klicken Sie mit der rechten Maustaste im **Projektmappen-Explorer** auf `CMakeSettings.json`, und wählen Sie **CMake-Einstellungen bearbeiten** aus. Alternativ können Sie oben im Editor-Fenster aus der Konfigurations-Dropdownliste **Konfigurationen verwalten...** auswählen. 

Sie können auch direkt bearbeiten, `CMakeSettings.json` zum Erstellen von benutzerdefinierter Konfigurationen des folgenden Beispiels zeigt eine Beispielkonfiguration, die Sie als Ausgangspunkt verwenden können:

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

Weitere Informationen zu den einzelnen Eigenschaften in der Datei finden Sie unter ["cmakesettings.JSON" Schemareferenz](cmakesettings-reference.md).

::: moniker-end

## <a name="see-also"></a>Siehe auch

[CMake Projects in Visual Studio (CMake-Projekte in Visual Studio)](cmake-projects-in-visual-studio.md)<br/>
[Konfigurieren eines Linux CMake-Projekts](../linux/cmake-linux-project.md)<br/>
[Herstellen einer Verbindung mit Ihrem Linux-Remotecomputer](../linux/connect-to-your-remote-linux-computer.md)<br/>
[Konfigurieren von CMake-Debugsitzungen](configure-cmake-debugging-sessions.md)<br/>
[Bereitstellen, Ausführen und Debuggen Ihres Linux-Projekts](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake predefined configuration reference (Referenz für vordefinierte CMake-Konfigurationen)](cmake-predefined-configuration-reference.md)<br/>
