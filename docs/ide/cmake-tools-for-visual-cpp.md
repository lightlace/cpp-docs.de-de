---
title: CMake Projekte in Visual C++ | Microsoft Docs
ms.custom: 
ms.date: 08/08/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 770b7f70e52859b1489b984d8aef3c3876a9ca83
ms.sourcegitcommit: 1b480aa74886930b3bd0435d71cfcc3ccda36424
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="cmake-projects-in-visual-c"></a>CMake Projekte in Visual C++
In diesem Artikel wird davon ausgegangen, dass Sie mit CMake ein plattformübergreifende Open-Source-Tool zum Definieren von Buildprozesse, die auf mehreren Plattformen ausgeführt vertraut sind.  

Erst vor kurzem konnte Visual Studio-Benutzer CMake verwenden, um MSBuild-Projektdateien zu generieren, die die IDE dann für IntelliSense verwendet, durchsuchen und Kompilierung. Ab Visual Studio 2017 die **Visual C++-Tools für CMake** -Komponente verwendet das Feature "Open Folder" So aktivieren Sie die IDE CMake-Projektdateien (z. B. CMakeLists.txt) nutzen, direkt zum Zweck der IntelliSense-Unterstützung und durchsuchen. Wenn Sie einen Visual Studio-Generator verwenden, wird eine temporäre Projektdatei wird generiert und an msbuild.exe übergeben, wird jedoch nie für IntelliSense oder Durchsuchen Zwecke geladen werden. 

**Visual Studio 2017 Version 15.3**: Unterstützung für Ninja und Visual Studio-Generatoren angeboten wird.

**Visual Studio 2017 Version 15.4**: Unterstützung für CMake unter Linux hinzugefügt wird. Weitere Informationen finden Sie unter [Konfigurieren eines Linux-Projekts CMake](../linux/cmake-linux-project.md).

## <a name="installing"></a>Installation
Visual C++-Tools für CMake wird als Teil der Desktopentwicklung Arbeitslast C++ standardmäßig installiert.

![CMake-Komponente in C++-Desktop-arbeitsauslastung](media/cmake-install.png)
 
## <a name="ide-integration"></a>Integration von IDE
Bei Auswahl **Datei | Open | Ordner** um einen Ordner mit einer CMakeLists.txt-Datei zu öffnen, werden die folgenden Aufgaben durchgeführt:
- Visual Studio fügt eine **CMake** Menüelement im Hauptmenü mit Befehlen zum Anzeigen und Bearbeiten von CMake-Skripts. 
- **Projektmappen-Explorer** zeigt die Ordnerstruktur und die Dateien. 
- Visual Studio CMake.exe ausgeführt und erzeugt die CMake Cache für den standardmäßigen *Konfiguration*, also X86 Debuggen. Die Befehlszeile CMake wird angezeigt, der **Fenster "Ausgabe"**, zusammen mit zusätzlichen Ausgabe CMake.
- Indizieren die Quelldateien zum Aktivieren von IntelliSense, Informationen zum Durchsuchen, Umgestaltung usw. startet Visual Studio das im Hintergrund. Bei der Arbeit überwacht Visual Studio Änderungen im Editor angezeigt und auch auf dem Datenträger auf ihren Index mit den Datenquellen synchronisiert werden. Sie können Ordner mit der eine beliebige Anzahl von CMake Projekte öffnen. Visual Studio erkennt und alle "Root" CMakeLists.txt Dateien in Ihrem Arbeitsbereich konfiguriert. CMake Vorgänge (konfigurieren, erstellen, Debuggen) sowie als C++ IntelliSense und Durchsuchen von allen CMake Projekte in Ihrem Arbeitsbereich zur Verfügung stehen.

![CMake-Projekt mit mehreren Stammelementen](media/cmake-multiple-roots.png) 

## <a name="building-cmake-projects"></a>Erstellen von CMake-Projekten
Um ein CMake-Projekt erstellen, müssen Sie diese Optionen aus:
1. Wählen Sie in der Debug-Dropdownliste, und drücken Sie die **F5** oder klicken Sie auf die Schaltfläche "Ausführen". Das Projekt wird automatisch Build zuerst, wie mit Visual Studio-Projektmappen.
2.  Klicken Sie mit der rechten Maustaste auf die CMakeLists.txt und wählen Sie Build aus dem Kontextmenü aus. Wenn Sie mehrere Ziele in der Ordnerstruktur verfügen, können Sie auswählen, um alle oder nur ein bestimmtes Ziel zu erstellen oder
  
3. Wählen Sie im Hauptmenü **erstellen | Projektmappe** (**F7** oder **STRG + UMSCHALT + B**) (Stellen Sie sicher, dass ein Ziel CMake bereits, in ausgewählt ist der **Startelement** Dropdownliste in der **Allgemeine** Symbolleiste).

![CMake Build Menübefehl](media/cmake-build-menu.png) 
 
Wenn ein Visual Studio-Generator für die aktive Konfiguration aktiviert ist, wird mit MSBuild.exe aufgerufen `-m -v:minimal` Argumente. Anpassen des Builds, in der Datei CMakeSettings.json können Sie angeben, zusätzliche befehlzeilenargumente über das Buildsystem übergeben werden die `buildCommandArgs` Eigenschaft:

```json
"buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
```
Wie zu erwarten, werden Buildergebnissen angezeigt, der **Fenster "Ausgabe"** und **Fehlerliste**.
 
![CMake Buildfehler](media/cmake-build-errors.png)

In einem Ordner mit mehreren Buildzielen können Sie das Build-Element im Menü CMake oder im Kontextmenü CMakeLists.txt, an welchen CMake erstellen auswählen. Drücken **STRG + UMSCHALT + B** in einem CMake Projektbuilds das aktuelle Dokument. 

## <a name="debugging-the-project"></a>Debuggen des Projekts
Um ein CMake-Projekt debuggen, wählen Sie die gewünschte Konfiguration, und drücken Sie **F5**, oder drücken Sie die Schaltfläche "ausführen" in der Symbolleiste. Wenn die Schaltfläche "ausführen" den Text "Start-Element auswählen", klicken Sie auf den Pfeil nach unten, und wählen Sie das Ziel, das Sie ausführen möchten. (In einem Projekt auf CMake "aktuellen Dokument" Option ist nur gültig für cpp-Dateien.) 

 ![Führen Sie CMake-Schaltfläche](media/cmake-run-button.png)

 Drücken **F5** ersten Build des Projekts wird, wenn Änderungen seit der vorherigen Build vorgenommen wurden.

## <a name="configuring-cmake-debugging-sessions"></a>Konfigurieren von CMake Debugsitzungen
Alle ausführbaren CMake Ziele werden in der Dropdownliste Startelement in der allgemeinen Symbolleiste angezeigt. Um eine Debugsitzung zu starten, wählen Sie eine, und starten Sie des Debuggers.

 ![CMake Startup-Element-Dropdownliste](media/cmake-startup-item-dropdown.png)

Sie können auch eine Debugsitzung in den Menüs CMake starten.

Klicken Sie zum Anpassen der Debuggereinstellungen für jedes beliebige ausführbare CMake Ziel in Ihrem Projekt mit der rechten Maustaste auf das bestimmte CMakeLists.txt-Datei, und wählen Sie **Debug- und Starteinstellungen**, wenn Sie in den Untermenüs, eine Datei namens CMake Ziel auswählen Launch.VS.JSON wird erstellt. Diese Datei wird mit Informationen zu Ziel-CMake gewähltem vorab aufgefüllt und können Sie zusätzliche Parameter wie z. B. Programmargumente oder Debuggertyp angeben. Um eine beliebige Taste in einer Datei CMakeSettings.json zu verweisen, leiten Sie ihn mit "Cmake." in launch.vs.json. Das folgende Beispiel zeigt eine einfache launch.vs.json-Datei, die abruft, den Wert des Schlüssels "RemoteCopySources" in der Datei CMakeSettings.json für die ausgewählte Konfiguration:

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
Sobald Sie die launch.vs.json-Datei speichern, wird ein Eintrag in der Dropdownliste Startelement mit dem neuen Namen erstellt. Durch Bearbeiten der launch.vs.json-Datei, können Sie erstellen, wie viele Konfigurationen Debuggen, wie Sie für eine beliebige Anzahl von CMake Ziele wie folgt aussehen.

**Visual Studio 2017 Version 15.4**: Launch.vs.json unterstützt die deklarierten Variablen in CMakeSettings.json (siehe unten). Es verfügt auch über ein Konzept von der "CurrentDir", die als das aktuelle Verzeichnis der Anwendung startet app festgelegt werden:

```json
{
"type": "default",
"project": "CMakeLists.txt",
"projectTarget": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
"name": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
"currentDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}"
}
```
Wenn Sie die Anwendung ausführen, den Wert des `currentDir` ist 

```cmd
C:\Users\satyan\7f14809a-2626-873e-952e-cdf038211175\
```
 

## <a name="editing-cmakeliststxt-files"></a>Bearbeiten von CMakeLists.txt-Dateien
Um eine CMakeLists.txt-Datei zu bearbeiten, klicken Sie mit der rechten Maustaste auf die Datei im **Projektmappen-Explorer** , und wählen Sie **öffnen**. Wenn Sie Änderungen an der Datei vornehmen, wird eine gelbe Statusleiste wird angezeigt und informiert, dass IntelliSense aktualisiert, und Ihnen eine Möglichkeit zum Update-Vorgang "Abbrechen bietet". Informationen zu CMakeLists.txt finden Sie unter der [CMake Dokumentation](https://cmake.org/documentation/).

  ![CMakeLists.txt-Datei bearbeiten](media/cmake-cmakelists.png)

Sobald Sie die Datei speichern, die Konfigurationsschritte automatisch führen Sie erneut aus und Informationen in das Fenster "Ausgabe" angezeigt. Fehler und Warnungen werden in der Fehlerliste oder das Fenster "Ausgabe" angezeigt. Doppelklicken Sie auf einen Fehler in der Fehlerliste zur problematischen Zeile im CMakeLists.txt navigieren.

  ![CMakeLists.txt Fehler](media/cmake-cmakelists-error.png)
 
## <a name="cmake_settings"></a>CMake-Einstellungen und benutzerdefinierte Konfigurationen
Visual Studio bietet standardmäßig sechs CMake Standardkonfigurationen ("X86-Debug", "X86-Version", "X64-Debug", "X64-Version", "Linux-Debug" und "Linux-Version"). Diese Konfigurationen definieren, wie CMake.exe aufgerufen wird, um den Cache CMake für ein angegebenes Projekt zu erstellen. Um diese Konfigurationen zu ändern oder eine neue benutzerdefinierte Konfiguration erstellen, wählen Sie **CMake | Ändern der Einstellung CMake**, und wählen Sie dann die CMakeLists.txt-Datei, die die Einstellungen für gelten. Die CMake-Einstellungen ändern steht auch auf dem Dateikontextmenü im **Projektmappen-Explorer**. Dieser Befehl erstellt eine CMakeSettings.json-Datei im Projektordner. Diese Datei dient zum Erstellen der CMake Cache-Datei, z. B. erneut nach einem "Sauberen"-Vorgang. 

  ![CMake Hauptmenü-Befehl für die änderungseinstellungen](media/cmake-change-settings.png)
 
JSON-IntelliSense hilft Ihnen das Bearbeiten der Datei CMakeSettings.json:

   ![CMake JSON-IntelliSense](media/cmake-json-intellisense.png)

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
1.  Name: der Name wird in der C++-Konfiguration-Dropdownliste angezeigt. Wert dieser Eigenschaft kann auch verwendet werden, als Makro `${name}` Eigenschaftswerte angeben. Ein Beispiel finden Sie unter der Definition "BuildRoot" CMakeSettings.json.
2.  Generator: mit dem Switch -G zugeordnet und gibt an, der Generator verwendet werden. Diese Eigenschaft kann auch verwendet werden, als Makro `${generator}` kann andere Eigenschaftswerte festgelegt. Visual Studio unterstützt derzeit die folgenden CMake Generatoren:
    - "Ninja"
    - "Visual Studio 2015 14"
    - "Visual Studio 2015 14 ARM"
    - "Visual Studio 2015 14 Win64"
    - "Visual Studio 15 2017"
    - "Visual Studio 15 2017 ARM"
    - "Visual Studio 15 2017 Win64"
    - 
Da Ninja für schnelle Builds Geschwindigkeiten anstelle von Flexibilität und die Funktion entwickelt wurde, wird dieser als Standard festgelegt. Allerdings möglicherweise einige CMake Projekte ordnungsgemäß erstellt mit Ninja werden konnte. In diesem Fall können Sie CMake stattdessen ein Visual Studio-Projekt generiert anweisen. 

Um ein Visual Studio-Generator angeben möchten, öffnen Sie die CMakeSettings.json über das Hauptmenü auswählen **CMake | Ändern der Einstellungen CMake**. Löschen Sie "Ninja", und geben Sie "V". Dadurch wird IntelliSense, können Sie den Generator wählen Sie die gewünschte aktiviert.
3.  BuildRoot: Ordnet - DCMAKE_BINARY_DIR Switch, und gibt an, in dem die CMake Cache erstellt wird. Wenn der Ordner nicht vorhanden ist, wird sie erstellt.
4.  Variablen: enthält ein Name-Wertpaar von CMake-Variablen, die als Dname - übergeben wird = Wert CMake. Wenn Ihre CMake Projekt Buildanweisungen aller Variablen direkt an die CMake Cache-Datei hinzufügen angeben, wird empfohlen, dass Sie diese hier stattdessen hinzufügen.
5.  CmakeCommandArgs: Gibt an, zusätzlichen Schalter an CMake.exe übergeben werden sollen.
6.  ConfigurationType: definiert den Typ des Build-Konfiguration für den ausgewählten-Generator. Derzeit unterstützte Werte sind "Debug", "MinSizeRel", "Release" und "RelWithDebInfo".

### <a name="environment-variables"></a>Umgebungsvariablen
CMakeSettings.json unterstützt auch verbrauchende Umgebungsvariablen in einem der oben genannten Eigenschaften. Die zu verwendende Syntax wird `${env.FOO}` Umgebung Variable "% FOO" erweitern.
Sie haben außerdem Zugriff auf vordefinierte Makros in dieser Datei:
- `${workspaceRoot}`– Stellt den vollständigen Pfad des Arbeitsbereichsordners
- `${workspaceHash}`– Hash des Arbeitsbereichs %Location; nützlich zum Erstellen von eines eindeutigen Bezeichner für den aktuellen Arbeitsbereich (z. B. zur Verwendung in Ordnerpfaden)
- `${projectFile}`– der vollständige Pfad der Datei CMakeLists.txt Stamm
- `${projectDir}`– der vollständige Pfad des Ordners, der die Stammdatei CMakeLists.txt
- `${thisFile}`– der vollständige Pfad der Datei CMakeSettings.json
- `${name}`– der Name der Konfiguration
- `${generator}`– der Name des in dieser Konfiguration verwendete CMake-Generators

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
|   C# - DIR   | Ändern Sie vor dem Ausführen anderer DIR| 
|   -f-Datei  | Geben Sie Eingabe Builddatei [default=build.ninja]| 
|   + j N     | N-Aufträge parallel ausgeführt werden [Standard = 14, abgeleitet aus verfügbaren CPUs]| 
|   -k N     | Versuchen Sie es weiter bis N Fail Aufträge [Standard = 1]| 
|   -l N     | neue Aufträge können nicht gestartet werden, wenn die durchschnittliche Auslastung größer als N ist| 
|   -n      | Trocknen ausführen (führen Sie Befehle nicht, aber fungieren, wie sie erfolgreich ausgeführt wurde)| 
|   -v       | Zeigen Sie aller Zeilen während der Erstellung an| 
|   -d-Modus  | Aktivieren des Debuggens (-d Liste in Verwendungsmodi)| 
|   -t-TOOL  | Führen Sie eine Subtool (mit t - Liste in zu weiteren Tools). beendet die Toplevel Optionen; Weitere Flags an das Tool übergeben werden.| 
|   -w-FLAG  | Anpassen von Warnungen (Verwendung -w Liste in Warnungen)| 


### <a name="inherited-environments-visual-studio-2017-version-155"></a>Geerbte Umgebungen (Visual Studio 2017 Version 15.5)

CmakeSettings.json unterstützt jetzt Inherted Umgebungen. Dieses Feature ermöglicht es Ihnen, eine benutzerdefinierte Variable zu erstellen, die:

```json
  "inheritEnvironments": [ "msvc_x64_x64" ]
```

Dieses Feld richtet Variablen, die automatisch an CMake.exe übergeben werden, wenn er ausgeführt wird. Das obige Beispiel ist dasselbe wie das Ausführen von "Developer-Eingabeaufforderung für VS 2017" mit der `-arch=amd64 -host_arch=amd64` Argumente.

Die folgende Tabelle zeigt die unterstützten Werte und deren Entsprechungen in der Befehlszeile:

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


Wichtige Änderungen in die CMakeSettings.json oder CMakeLists.txt Dateien, Visual Studio automatisch ausgeführt werden konfigurieren Schritt der CMake dann erneut ausgeführt. Wenn Schritt konfigurieren ohne Fehler abgeschlossen ist, wird die gesammelten Informationen stehen in C++ IntelliSense und Language Services sowie in den Build und Debuggen Sie Vorgänge.

Wenn mehrere CMake Projekte CMake Konfiguration gleichnamigen (z. B. X86-Debug) verwenden, werden alle von ihnen konfiguriert und erstellt (im eigenen Build-Stammordner) Wenn diese Konfiguration aktiviert ist. Sie können die Ziele aus allen Projekten CMake Debuggen, die in dieser Konfiguration CMake beteiligt sind.

   ![Nur Build CMake Menüelement](media/cmake-build-only.png)

Erstellen Sie eine neue Konfiguration mit einem eindeutigen Namen in der Datei CMakeSettings.json, und auf diese Projekte nur angewendet, um Builds begrenzen und zu debuggen Sitzungen auf eine Teilmenge der Projekte in den Arbeitsbereich. Wenn diese Konfiguration wird ausgewählt, IntelliSense, erstellen und Debuggen, wird aktiviert werden, nur für solche Projekte angegeben.

## <a name="troubleshooting-cmake-cache-errors"></a>Problembehandlung bei der CMake-cache
Wenn Sie weitere Informationen über den Status des Caches CMake zum Diagnostizieren eines Problems benötigen, öffnen Sie im Hauptmenü CMake oder im Kontextmenü CMakeLists.txt in **Projektmappen-Explorer** einen der folgenden Befehle ausführen:
- **Anzeigen von Cache** die CMakeCache.txt-Datei im Stammordner Build im Editor geöffnet. (Alle Änderungen, die Sie hier CMakeCache.txt vornehmen, werden zurückgesetzt Wenn Sie den Cache nicht bereinigen. Um Änderungen vorzunehmen, die beibehalten werden, nachdem der Cache bereinigt wird, finden Sie unter [CMake Clienteinstellungen und Konfigurationen für benutzerdefinierte](#cmake_settings) weiter oben in diesem Artikel.)
- **Öffnen Sie Cacheordner** öffnet ein Explorer-Fenster in den Stammordner erstellen.  
- **Bereinigen von Cache** löscht den Stammordner erstellen, damit der nächste CMake konfigurieren Schritt beginnt mit einem Löschcache.
- **Generieren von Cache** erzwingt das Generieren Schritt ausgeführt wird, auch wenn Visual Studio die Umgebung auf dem neuesten Stand hält.

