---
title: CMake Projekte in Visual C++ | Microsoft Docs
ms.custom: 
ms.date: 08/08/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8b9f00e511be43e5a6b77abae6394013e4e33a34
ms.sourcegitcommit: 2cca90d965f76ebf1d741ab901693a15d5b8a4df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2018
---
# <a name="cmake-projects-in-visual-c"></a>CMake Projekte in Visual C++

In diesem Artikel wird davon ausgegangen, dass Sie mit CMake ein plattformübergreifende Open-Source-Tool zum Definieren von Buildprozesse, die auf mehreren Plattformen ausgeführt vertraut sind.

Erst vor kurzem konnte Visual Studio-Benutzer CMake verwenden, um MSBuild-Projektdateien zu generieren, die die IDE dann für IntelliSense verwendet, durchsuchen und Kompilierung. Ab Visual Studio 2017 die **Visual C++-Tools für CMake** -Komponente verwendet die **Ordner öffnen** Funktion so aktivieren Sie die IDE CMake-Projektdateien (z. B. CMakeLists.txt) direkt für die Zwecke zu nutzen von IntelliSense und durchsuchen. Wenn Sie einen Visual Studio-Generator verwenden, wird eine temporäre Projektdatei wird generiert und an msbuild.exe übergeben, wird jedoch nie für IntelliSense oder Durchsuchen Zwecke geladen werden. 

**Visual Studio 2017 Version 15.3**: Unterstützung für Ninja und Visual Studio-Generatoren angeboten wird.

**Visual Studio 2017 Version 15.4**: Unterstützung für CMake unter Linux hinzugefügt wird. Weitere Informationen finden Sie unter [Konfigurieren eines Linux CMake-Projekts](../linux/cmake-linux-project.md).

**Visual Studio 2017 Version 15.5**: Unterstützung für importieren einen vorhandenen CMake Cache hinzugefügt wird. Visual Studio extrahiert die benutzerdefinierte Variablen automatisch und erstellt eine vorgegebene CMakeSettings.json-Datei.


## <a name="installation"></a>Installation

**Visual C++-Tools für CMake** wird standardmäßig installiert, als Teil der **Desktopentwicklung mit C++** arbeitsauslastung.

![CMake-Komponente in C++-Desktop-arbeitsauslastung](media/cmake-install.png)
 
## <a name="ide-integration"></a>Integration von IDE

Bei Auswahl **Datei | Open | Ordner** um einen Ordner mit einer CMakeLists.txt-Datei zu öffnen, werden die folgenden Aufgaben durchgeführt:

- Visual Studio fügt eine **CMake** Menüelement im Hauptmenü mit Befehlen zum Anzeigen und Bearbeiten von CMake-Skripts.
- **Projektmappen-Explorer** zeigt die Ordnerstruktur und die Dateien.
- Visual Studio CMake.exe ausgeführt und erzeugt die CMake Cache für den standardmäßigen *Konfiguration*, also X86 Debuggen. Die Befehlszeile CMake wird angezeigt, der **Fenster "Ausgabe"**, zusammen mit zusätzlichen Ausgabe CMake.
- Indizieren die Quelldateien zum Aktivieren von IntelliSense, Informationen zum Durchsuchen, Umgestaltung usw. startet Visual Studio das im Hintergrund. Bei der Arbeit überwacht Visual Studio Änderungen im Editor angezeigt und auch auf dem Datenträger auf ihren Index mit den Datenquellen synchronisiert werden.
 
Sie können Ordner mit der eine beliebige Anzahl von CMake Projekte öffnen. Visual Studio erkennt und alle "Root" CMakeLists.txt Dateien in Ihrem Arbeitsbereich konfiguriert. CMake Vorgänge (konfigurieren, erstellen, Debuggen) sowie als C++ IntelliSense und Durchsuchen von allen CMake Projekte in Ihrem Arbeitsbereich zur Verfügung stehen.

![CMake-Projekt mit mehreren Stammelementen](media/cmake-multiple-roots.png) 

## <a name="import-an-existing-cache"></a>Importieren Sie einen vorhandenen cache

Wenn Sie eine vorhandene CMakeCache.txt-Datei importieren, werden von Visual Studio automatisch benutzerdefinierte Variablen extrahiert und erstellt eine vorgegebene CMakeSettings.json-Datei auf ihrer Grundlage. Die ursprüngliche Cache wird nicht in keiner Weise geändert und kann weiterhin verwendet werden, über die Befehlszeile oder mit beliebigen Tool oder die IDE, zum Generieren verwendet wurde. Die neue CMakeSettings.json-Datei wird zusammen mit den Stamm des Projekts CMakeLists.txt platziert. Visual Studio generiert einen neuen Cache basierend die Einstellungsdatei. Nicht alle Elemente im Cache wird importiert.  Eigenschaften wie den Generator und den Speicherort der Compiler werden durch Standardwerte ersetzt, die bekannt sind, auch bei der IDE ordnungsgemäß funktionieren.

### <a name="to-import-an-existing-cache"></a>So importieren Sie einen vorhandenen cache

1. Wählen Sie im Hauptmenü **Datei | Open | CMake**:

   ![Öffnen Sie CMake](media/cmake-file-open.png "-Datei, öffnen, CMake") 

   Daraufhin wird die **Import CMake aus dem Cache** Assistenten. 
   
2. Navigieren Sie zu der CMakeCache.txt-Datei, die Sie importieren möchten, und klicken Sie dann auf **OK**. Die **CMake-Import-Projekt aus dem Cache** -Assistent wird angezeigt:

   ![Importieren ein Caches CMake](media/cmake-import-wizard.png "Importassistenten Cache CMake öffnen") 

   Wenn der Assistent abgeschlossen ist, sehen Sie die neue CMakeCache.txt-Datei in **Projektmappen-Explorer** neben der Datei im Stammverzeichnis CMakeLists.txt in Ihrem Projekt.


## <a name="building-cmake-projects"></a>Erstellen von CMake-Projekten

Um ein CMake-Projekt erstellen, müssen Sie diese Optionen aus:

1. Wählen Sie das Ziel in der **Debuggen** Dropdownliste, und drücken Sie **F5**, oder klicken Sie auf die **ausführen** Schaltfläche (grünes Dreieck). Das Projekt erstellt automatisch zuerst, wie Visual Studio-Projektmappe.
1. Klicken Sie mit der rechten Maustaste auf den CMakeLists.txt, und wählen **erstellen** aus dem Kontextmenü. Wenn Sie mehrere Ziele in der Ordnerstruktur verfügen, können Sie auswählen, um alle oder nur ein bestimmtes Ziel zu erstellen oder
1. Wählen Sie im Hauptmenü **erstellen | Projektmappe** (**F7** oder **STRG + UMSCHALT + B**). Stellen Sie sicher, dass ein Ziel CMake bereits, in ausgewählt ist der **Startelement** Dropdownliste in der **allgemeine** Symbolleiste.

![CMake erstellen Menübefehl](media/cmake-build-menu.png "Cmake erstellen Befehlsmenü") 

Wenn ein Visual Studio-Generator für die aktive Konfiguration aktiviert ist, wird mit MSBuild.exe aufgerufen `-m -v:minimal` Argumente. Anpassen des Builds, in der Datei CMakeSettings.json können Sie angeben, zusätzliche befehlzeilenargumente über das Buildsystem übergeben werden die `buildCommandArgs` Eigenschaft:

```json
"buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
```

Wie zu erwarten, werden Buildergebnissen angezeigt, der **Fenster "Ausgabe"** und **Fehlerliste**.
 
![Buildfehler, CMake](media/cmake-build-errors.png "CMake Buildfehler")

In einen Ordner mit mehreren Buildzielen, können Sie die **erstellen** Element auf der **CMake** Menü oder die **CMakeLists.txt** Kontextmenü, um festzulegen, welche Zielserver CMake erstellen. Drücken **STRG + UMSCHALT + B** in einem CMake Projektbuilds das aktuelle Dokument.

## <a name="debug-the-project"></a>Debuggen des Projekts

Um ein CMake-Projekt debuggen, wählen Sie die gewünschte Konfiguration, und drücken Sie **F5**, oder drücken Sie die **ausführen** auf der Symbolleiste. Wenn die **ausführen** Schaltfläche "Start-Element auswählen", wählen Sie den Dropdownpfeil, und wählen Sie das Ziel, das Sie ausführen möchten. (In einem Projekt auf CMake "aktuellen Dokument" Option ist nur gültig für cpp-Dateien.) 

![Führen Sie CMake Schaltfläche](media/cmake-run-button.png "Cmake ausführen Schaltfläche")


Die **ausführen** oder **F5** Befehle wird zuerst das Projekt erstellen, wenn Änderungen seit der vorherigen Build vorgenommen wurden.

## <a name="configure-cmake-debugging-sessions"></a>Konfigurieren von CMake Debugsitzungen

Alle ausführbaren CMake Ziele werden angezeigt, der **Startelement** Dropdownliste in der **allgemeine** Symbolleiste. Um eine Debugsitzung zu starten, wählen Sie eine, und starten Sie des Debuggers.

![CMake Startup-Element-Dropdownliste](media/cmake-startup-item-dropdown.png "CMake Startup-Element-Dropdownliste")


Sie können auch eine Debugsitzung in den Menüs CMake starten.

Klicken Sie zum Anpassen der Debuggereinstellungen für jedes beliebige ausführbare CMake Ziel in Ihrem Projekt mit der rechten Maustaste auf das bestimmte CMakeLists.txt-Datei, und wählen Sie **Debug- und Starteinstellungen**. Wenn Sie ein Ziel CMake in den Untermenüs auswählen, wird eine Datei namens launch.vs.json erstellt. Diese Datei wird mit Informationen zu Ziel-CMake gewähltem vorab aufgefüllt und können Sie zusätzliche Parameter wie z. B. Programmargumente oder Debuggertyp angeben. Um eine beliebige Taste in einer Datei CMakeSettings.json zu verweisen, leiten Sie ihn mit "Cmake." in launch.vs.json. Das folgende Beispiel zeigt eine einfache launch.vs.json-Datei, die abruft, den Wert des Schlüssels "RemoteCopySources" in der Datei CMakeSettings.json für die ausgewählte Konfiguration:

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

Sobald Sie die launch.vs.json-Datei speichern, wird ein Eintrag erstellt, der **Startelement** Dropdownliste mit den neuen Namen. Durch Bearbeiten der launch.vs.json-Datei, können Sie erstellen, wie viele Konfigurationen Debuggen, wie Sie für eine beliebige Anzahl von CMake Ziele wie folgt aussehen.

**Visual Studio 2017 Version 15.4**: Launch.vs.json unterstützt Variablen, der in CMakeSettings.json (siehe unten) deklariert werden und auf die aktuell ausgewählte Konfiguration geeignet sind. Es verfügt auch über einen Schlüssel namens "CurrentDir", die das aktuelle Verzeichnis der Anwendung startet app festlegt:


```json
{
"type": "default",
"project": "CMakeLists.txt",
"projectTarget": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
"name": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
"currentDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}"
}
```

Wenn Sie die Anwendung ausführen, den Wert des `currentDir` ist etwas Ähnliches wie

```cmd
C:\Users\satyan\7f14809a-2626-873e-952e-cdf038211175\
```

## <a name="editing-cmakeliststxt-files"></a>Bearbeiten von CMakeLists.txt-Dateien

Um eine CMakeLists.txt-Datei zu bearbeiten, klicken Sie mit der rechten Maustaste auf die Datei im **Projektmappen-Explorer** , und wählen Sie **öffnen**. Wenn Sie Änderungen an der Datei vornehmen, wird eine gelbe Statusleiste wird angezeigt und informiert, dass IntelliSense aktualisiert, und Ihnen eine Möglichkeit zum Update-Vorgang "Abbrechen bietet". Informationen zu CMakeLists.txt finden Sie unter der [CMake Dokumentation](https://cmake.org/documentation/).

   ![Bearbeiten von CMakeLists.txt Datei](media/cmake-cmakelists.png "CMakeLists.txt-Datei bearbeiten")


Sobald Sie die Datei speichern, die Konfigurationsschritte automatisch erneut ausgeführt und zeigt Informationen auf der **Ausgabe** Fenster. Fehler und Warnungen werden angezeigt, der **Fehlerliste** oder **Ausgabe** Fenster. Doppelklicken Sie auf einen Fehler in der **Fehlerliste** zur problematischen Zeile im CMakeLists.txt navigieren.

   ![Fehler in der CMakeLists.txt](media/cmake-cmakelists-error.png "CMakeLists.txt Fehler")

## <a name="cmake_settings"></a> CMake-Einstellungen und benutzerdefinierte Konfigurationen

Visual Studio bietet standardmäßig sechs CMake Standardkonfigurationen ("X86-Debug", "X86-Version", "X64-Debug", "X64-Version", "Linux-Debug" und "Linux-Version"). Diese Konfigurationen definieren, wie CMake.exe aufgerufen wird, um den Cache CMake für ein angegebenes Projekt zu erstellen. Um diese Konfigurationen zu ändern oder eine neue benutzerdefinierte Konfiguration erstellen, wählen Sie **CMake | Ändern der Einstellungen CMake**, und wählen Sie dann die CMakeLists.txt-Datei, die die Einstellungen für gelten. Die **CMake Änderungseinstellungen** Befehl steht auch auf dem Dateikontextmenü im **Projektmappen-Explorer**. Dieser Befehl erstellt eine CMakeSettings.json-Datei im Projektordner. Diese Datei wird verwendet, um die Cachedatei CMake, z. B. nach dem Neuerstellen einer **Bereinigen** Vorgang. 

   ![CMake Hauptmenü-Befehl für die änderungseinstellungen](media/cmake-change-settings.png)


JSON-IntelliSense hilft Ihnen das Bearbeiten der Datei CMakeSettings.json:

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png "CMake JSON-IntelliSense")

Das folgende Beispiel zeigt eine Beispielkonfiguration mit, die Sie als Ausgangspunkt zum Erstellen eigener in CMakeSettings.json verwenden können:

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

1. **Namen**: der Name, der in der Dropdownliste der C++-Konfiguration angezeigt wird. Dieser Wert kann auch verwendet werden, als Makro, `${name}`, um andere Eigenschaftswerte anzugeben. Ein Beispiel finden Sie die **BuildRoot** -Definition in CMakeSettings.json.
1. **Generator**: Ordnet die **- G** wechseln, und gibt an, der Generator verwendet werden. Diese Eigenschaft kann auch verwendet werden, als Makro, `${generator}`, damit die Eigenschaftswerte angeben. Visual Studio unterstützt derzeit die folgenden CMake Generatoren:


    - "Ninja"
    - "Visual Studio 14 2015"
    - "Visual Studio 14 2015 ARM"
    - "Visual Studio 14 2015 Win64"
    - "Visual Studio 15 2017"
    - "Visual Studio 15 2017 ARM"
    - "Visual Studio 15 2017 Win64"

Da Ninja für schnelle Builds Geschwindigkeiten anstelle von Flexibilität und die Funktion entwickelt wurde, wird dieser als Standard festgelegt. Allerdings möglicherweise einige CMake Projekte ordnungsgemäß erstellt mit Ninja werden konnte. In diesem Fall können Sie CMake stattdessen ein Visual Studio-Projekt generiert anweisen.

Um ein Visual Studio-Generator angeben möchten, öffnen Sie die CMakeSettings.json über das Hauptmenü auswählen **CMake | Ändern der Einstellungen CMake**. Löschen Sie "Ninja", und geben Sie "V". Dadurch wird IntelliSense, können Sie den Generator wählen Sie die gewünschte aktiviert.

1. **BuildRoot**: ordnet **-DCMAKE_BINARY_DIR** wechseln, und gibt an, in dem die CMake Cache erstellt wird. Wenn der Ordner nicht vorhanden ist, wird er erstellt.
1. **Variablen**: enthält ein Name / Wert-Paar von CMake-Variablen, die als übergeben wird **-D**_Namen_**=**_Wert_ auf CMake. Wenn Ihre CMake Projekt Buildanweisungen das Hinzufügen von Variablen direkt an die CMake Cache-Datei angeben, wird empfohlen, dass Sie diese hier stattdessen hinzufügen.
1. **CmakeCommandArgs**: Gibt an, zusätzlichen Schalter an CMake.exe übergeben werden sollen.
1. **ConfigurationType**: definiert den Typ des Build-Konfiguration für den ausgewählten-Generator. Derzeit unterstützte Werte sind "Debug", "MinSizeRel", "Release" und "RelWithDebInfo".

### <a name="environment-variables"></a>Umgebungsvariablen

CMakeSettings.json unterstützt auch verbrauchende Umgebungsvariablen in einem der oben genannten Eigenschaften. Die zu verwendende Syntax wird `${env.FOO}` Umgebung Variable "% FOO" erweitern.
Sie haben außerdem Zugriff auf vordefinierte Makros in dieser Datei:

- `${workspaceRoot}` – Stellt den vollständigen Pfad des Arbeitsbereichsordners
- `${workspaceHash}` – Hash des Arbeitsbereichs %Location; nützlich zum Erstellen von eines eindeutigen Bezeichner für den aktuellen Arbeitsbereich (z. B. zur Verwendung in Ordnerpfaden)
- `${projectFile}` – der vollständige Pfad der Datei CMakeLists.txt Stamm
- `${projectDir}` – der vollständige Pfad des Ordners, der die Stammdatei CMakeLists.txt
- `${thisFile}` – der vollständige Pfad der Datei CMakeSettings.json
- `${name}` – der Name der Konfiguration
- `${generator}` – der Name des in dieser Konfiguration verwendete CMake-Generators

### <a name="ninja-command-line-arguments"></a>Ninja-Befehlszeilenargumente

Falls nicht angegeben sind, erstellt das Ziel 'Default' (finden Sie unter "manuell").

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|Option|Beschreibung|
|--------------|------------|
| --Version  | Drucken von Ninja-Version ("1.7.1")|
|   -C DIR   | Ändern Sie vor dem Ausführen anderer DIR|
|   -f-Datei  | Geben Sie die Eingabe Builddatei (default=build.ninja)|
|   -j N     | N-Aufträge parallel ausgeführt werden (Standardeinstellung = 14, verfügbaren CPUs abgeleitet)|
|   -k N     | Versuchen Sie es weiter bis N Fail Aufträge (Standardwert = 1)|
|   -l N     | neue Aufträge können nicht gestartet werden, wenn die durchschnittliche Auslastung größer als N ist|
|   -n      | Trocknen ausführen (führen Sie Befehle nicht, aber fungieren, wie sie erfolgreich ausgeführt wurde)|
|   -v       | Zeigen Sie aller Zeilen während der Erstellung an|
|   -d-Modus  | Aktivieren des Debuggens (-d Liste in Verwendungsmodi)|
|   -t-TOOL  | Führen Sie eine Subtool (mit t - Liste in zu weiteren Tools). beendet die Toplevel Optionen; Weitere Flags an das Tool übergeben werden.| 
|   -w-FLAG  | Anpassen von Warnungen (Verwendung -w Liste in Warnungen)|

### <a name="inherited-environments-visual-studio-2017-version-155"></a>Geerbte Umgebungen (Visual Studio 2017 Version 15.5)
CMakeSettings.json unterstützt jetzt die geerbte Umgebungen. Dieses Feature ermöglicht Ihnen, (1) erben standardmäßig Umgebungen und (2) erstellen Sie benutzerdefinierte Umgebungsvariablen, die an CMake.exe übergeben werden, wenn er ausgeführt wird.

```json
  "inheritEnvironments": [ "msvc_x64_x64" ]
```

Im obigen Beispiel entspricht dem Ausführen der **Developer-Eingabeaufforderung für VS 2017** mit der **-Arch = amd64-Host_arch = amd64** Argumente.

Die folgende Tabelle zeigt die Standardwerte und deren Entsprechungen Befehlszeile:

|Kontextname|Beschreibung|
|-----------|-----------------|
|vsdev|Der standardmäßige Visual Studio-Umgebung|
|msvc_x86|Kompilieren für X86 X86 mit Tools|
|msvc_arm| Kompilieren für ARM X86 mit Tools|
|msvc_arm64|Kompilieren für ARM64 X86 mit Tools|
|msvc_x86_x64|Kompilieren für AMD64 X86 mit Tools|
|msvc_x64_x64|Für AMD64 Kompilieren mithilfe von 64-Bit-tools|
|msvc_arm_x64|Kompilieren Sie für ARM mit 64-Bit-tools|
|msvc_arm64_x64|Für ARM64 Kompilieren mithilfe von 64-Bit-tools|

### <a name="custom-environment-variables"></a>Benutzerdefinierte Umgebungsvariablen
In CMakeSettings.json, können Sie Global benutzerdefinierten Umgebungsvariablen definieren oder pro-Konfiguration in der **Umgebungen** Eigenschaft. Das folgende Beispiel definiert eine globale Variable **BuildDir**, die in die X86-Debug- und die X64-Debug-Konfigurationen geerbt wird. Jede Konfiguration verwendet die Variable zum Angeben des Werts für die **BuildRoot** Eigenschaft für diese Konfiguration. Beachten Sie auch, wie jede Konfiguration verwendet die **InheritEnvironments** Eigenschaft, um eine Variable anzugeben, die nur für diese Konfiguration gilt.

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

Im nächsten Beispiel definiert die X86-Debug-Konfiguration einen eigenen Wert für die **BuildDir** -Eigenschaft, und dieser Wert überschreibt den Wert festlegen, indem die globale **BuildDir** Eigenschaft, damit  **BuildRoot** ergibt `D:\custom-builddir\x86-Debug`.

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

## <a name="cmake-configure-step"></a>CMake konfigurieren Schritt

Wichtige Änderungen in die CMakeSettings.json oder CMakeLists.txt Dateien, Visual Studio automatisch ausgeführt werden konfigurieren Schritt der CMake dann erneut ausgeführt. Wenn Schritt konfigurieren ohne Fehler abgeschlossen ist, die gesammelten Informationen steht im C++-IntelliSense und Dienste für Sprachen auch im build und zu debuggen Vorgänge.

Wenn mehrere CMake Projekte CMake Konfiguration gleichnamigen (z. B. X86-Debug) verwenden, werden alle von ihnen konfiguriert und erstellt (im eigenen Build-Stammordner) Wenn diese Konfiguration aktiviert ist. Sie können die Ziele aus allen Projekten CMake Debuggen, die in dieser Konfiguration CMake beteiligt sind.

   ![Nur Build CMake Menüelement](media/cmake-build-only.png "CMake erstellen nur Menüelement")

Erstellen Sie eine neue Konfiguration mit einem eindeutigen Namen in der Datei CMakeSettings.json, und auf diese Projekte nur angewendet, um Builds begrenzen und zu debuggen Sitzungen auf eine Teilmenge der Projekte in den Arbeitsbereich. Wenn die Konfiguration ausgewählt ist, sind IntelliSense "und" Build "und" Debug-Befehle nur für die angegebenen Projekte aktiviert.

## <a name="troubleshooting-cmake-cache-errors"></a>Problembehandlung bei der CMake-cache

Wenn Sie weitere Informationen über den Status des Caches CMake zum Diagnostizieren eines Problems benötigen, öffnen Sie die **CMake** Hauptmenü oder **CMakeLists.txt** Kontextmenü in **Projektmappen-Explorer**einen der folgenden Befehle ausführen:

- **Anzeigen von Cache** die CMakeCache.txt-Datei im Stammordner Build im Editor geöffnet. (Alle Änderungen, die Sie hier CMakeCache.txt vornehmen, werden zurückgesetzt Wenn Sie den Cache nicht bereinigen. Um Änderungen vorzunehmen, die beibehalten werden, nachdem der Cache bereinigt wird, finden Sie unter [CMake Clienteinstellungen und Konfigurationen für benutzerdefinierte](#cmake_settings) weiter oben in diesem Artikel.)
- **Öffnen Sie Cacheordner** öffnet ein Explorer-Fenster in den Stammordner erstellen.  
- **Bereinigen von Cache** löscht den Stammordner erstellen, damit der nächste CMake konfigurieren Schritt beginnt mit einem Löschcache.
- **Generieren von Cache** erzwingt das Generieren Schritt ausgeführt wird, auch wenn Visual Studio die Umgebung auf dem neuesten Stand hält.
