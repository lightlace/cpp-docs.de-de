---
title: "Öffnen Sie Ordner Projekte in Visual C++ | Microsoft Docs"
ms.custom: 
ms.date: 08/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Open Folder Projects in Visual C++
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 72106bd363987d39fb11c9ec1a6d3fd0ceb5665d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="open-folder-projects-in-visual-c"></a>Öffnen Sie Ordner Projekte in Visual C++
Visual Studio-2017 führt die Funktion "Ordner geöffnet" ermöglicht es Ihnen, öffnen Sie einen Ordner für Quelldateien und sofort Codieren mit Unterstützung für IntelliSense, durchsuchen, Umgestaltung, Debuggen, beginnen und so weiter. Keine sln oder vcxproj-Dateien werden geladen. bei Bedarf können Sie benutzerdefinierte Tasks angeben sowie erstellen und starten Sie die Parameter durch einfache JSON-Dateien. Unterstützt von Ordner öffnen, kann Visual C++ jetzt nicht nur lose Sammlungen von Dateien, sondern auch nahezu alle Buildsystem, darunter CMake, Ninja, QMake (für unbedingt Projekte), Gyp, SCons, Gradle, Buck, stellen und vieles mehr unterstützen. 

Wählen Sie zum Ordner öffnen zu verwenden, über das Hauptmenü *Datei | Open | Ordner* oder drücken Sie *Strg + Umschalt + Alt + O*. Projektmappen-Explorer zeigt sofort alle Dateien im Ordner "". Sie können auf eine beliebige Datei aus, um mit der Bearbeitung anfangen klicken. Im Hintergrund startet Visual Studio, indizieren Sie die Dateien, um IntelliSense, Navigation und Umgestaltung Funktionen zu aktivieren. Wie bearbeiten, erstellen, verschieben oder Löschen von Dateien wird von Visual Studio die Änderungen automatisch nachverfolgt und kontinuierlich aktualisiert seinen IntelliSense-Index. 
  
## <a name="cmake-projects"></a>CMake-Projekte
CMake ist in der Visual Studio-IDE als CMake-Tools für Visual C++ ist eine Komponente von der C++-desktop-arbeitsauslastung integriert. Weitere Informationen finden Sie unter [CMake-Tools für Visual C++](cmake-tools-for-visual-cpp.md).
 
## <a name="qmake-projects-that-target-the-qt-framework"></a>QMake-Projekten, die unbedingt Framework abzielen
Können CMake-Tools für Visual C++ Ziel unbedingt zum Erstellen von Projekten unbedingt oder können Sie die unbedingt-Erweiterung für Visual Studio. Hinweis: Ab August 2017 die [unbedingt-Erweiterung für Visual Studio-Unterstützung für Visual Studio-2017](https://download.qt.io/development_releases/vsaddin/) ist als eine Betaversion verfügbar.

## <a name="gyp-cons-scons-buck-etc"></a>Gyp, Nachteile, SCons, Buck usw.
Sie können alle Buildsystem in Visual C++ verwenden und weiterhin nutzen der Vorteile der Visual C++-IDE und des Debuggers. Wenn Sie den Stammordner des Projekts öffnen, verwendet Visual C++ Heuristik, um die Quelldateien für IntelliSense und das Durchsuchen zu indizieren. Sie können Hinweise zur Struktur des Codes durch Bearbeiten der Datei CppProperties.json bereitstellen. Auf ähnliche Weise können Sie das Build-Programm durch Bearbeiten der Datei launch.vs.json konfigurieren. 

## <a name="configuring-open-folder-projects"></a>Konfigurieren von Projekten Ordner öffnen
Sie können über drei JSON-Dateien einen Ordner öffnen-Projekt anpassen:
|||
|-|-|
|CppProperties.json|Geben Sie für das Durchsuchen von benutzerdefinierten Konfigurationsinformationen. Erstellen Sie diese Datei, die ggf. im Stammordner des Projekts.|
|Launch.VS.JSON|Geben Sie die Befehlszeilenargumente. Über die **Projektmappen-Explorer** Kontextmenüelement **Debug- und Starteinstellungen**.|
|Tasks.VS.JSON|Geben Sie benutzerdefinierte Buildbefehle und Compilerschalter. Über die **Projektmappen-Explorer** Kontextmenüelement **Tasks konfigurieren**.|

### <a name="configure-intellisense-with-cpppropertiesjson"></a>Konfigurieren von IntelliSense mit CppProperties.json
IntelliSense und Durchsuchen das Verhalten teilweise hängt von der aktiven Buildkonfiguration, die definiert #include Bereichspfade, Compilerschalter sowie anderen Parametern. Visual Studio bietet standardmäßig Debug- und Releasekonfigurationen. Bei einigen Projekten müssen Sie zum Erstellen einer benutzerdefinierten Konfigurations in der Reihenfolge von IntelliSense und Suchfunktionen zu Ihrem Code vollständig zu verstehen. Um eine neue Konfiguration zu definieren, erstellen Sie eine Datei namens CppProperties.json im Stammordner. Im Folgenden ein Beispiel:

```json
{
  "configurations": [
    {
      "name": "Windows x64",
      "includePath": [ "include" ],
      "defines": [ "_DEBUG" ],
      "compilerSwitches": "/std:c++17",
      "intelliSenseMode": "msvc-x64",
      "forcedInclude": [ "pch.h" ],
      "undefines": []
    }
  ]
}
```
Eine Konfiguration kann die folgenden Eigenschaften aufweisen:

|||  
|-|-| 
|`name`|der Konfigurationsname, der in der Dropdownliste der C++-Konfiguration angezeigt wird.|
|`includePath`|die Liste der Ordner, die im Includepfad (Maps Sie für die meisten Compiler/i) angegeben werden:|
|`defines`|die Liste der Makros, die sollten definiert (Maps, / d für die meisten Compiler)|
|`compilerSwitches`|eine oder mehrere zusätzliche Switches, die das Verhalten von IntelliSense beeinflussen können|
|`forcedInclude`|Header, automatisch in jeder Kompilierungseinheit eingeschlossen werden sollen (ordnet/Fi für MSVC oder - umfassen für Clang)|
|`undefines`|die Liste der Makros undefiniert (ergibt/u für MSVC) sein|
|`intelliSenseMode`|das IntelliSense-Modul verwendet werden. Sie können die Architektur spezifischen Varianten für MSVC, die erforderlichen gcc- und Clang angeben:
- MSVC-X86 (Standard)
- MSVC x64
- MSVC arm
- Windows-Clang-x86
- Windows-Clang-x64
- Windows-Clang-arm
- Linux-x64
- Linux-x86
- Linux-arm
- gccarm

CppProperties.json unterstützt umgebungsvariablenerweiterung für gehören Pfade und andere Eigenschaftswerte. Die Syntax lautet `${env.FOODIR}` erweitert eine Umgebungsvariable `%FOODIR%`.

Sie haben außerdem Zugriff auf die folgenden vordefinierten Makros in dieser Datei:
|||
|-|-|
|`${workspaceRoot}`| den vollständigen Pfad zu dem Arbeitsbereichsordner im|
|`${projectRoot}`| den vollständigen Pfad zu dem Ordner, in dem CppProperties.json platziert wird|
|`${vsInstallDir}`| den vollständigen Pfad zu dem Ordner, in dem die ausgeführte Instanz von Visual Studio 2017 installiert ist|

Z. B. wenn das Projekt verfügt über einen Ordner einschließen und auch windows.h und andere allgemeine Header aus dem Windows SDK enthält, können Sie Ihre CppProperties.json aktualisieren möchten Konfigurationsdatei mit diesen enthält:

```json
{
  "configurations": [
    {
      "name": "Windows",
      "includePath": [
        // local include folder
        "${workspaceRoot}\\include",
        // Windows SDK and CRT headers
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\ucrt",
        "${env.NETFXSDKDir}\\include\\um",
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\um",
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\shared",
        "${env.VCToolsInstallDir}include"
      ]
    }
  ]
}
```

**Hinweis:** `%WindowsSdkDir%` und `%VCToolsInstallDir%` sind nicht festgelegt werden, wie die globalen Umgebungsvariablen Achten Sie darauf, Sie starten devenv.exe aus "Developer-Eingabeaufforderung für VS 2017", der diesen Variablen definiert.

Problembehandlung von IntelliSense Fehler aufgrund fehlender Includepfaden, öffnen Sie die **Fehlerliste** und Filtern Sie seine Ausgabe an "Nur IntelliSense" und Fehlercode E1696 "kann nicht geöffnet werden... Quelldatei". 

Sie können eine beliebige Anzahl von Konfigurationen in CppProperties.json erstellen. Jede erscheint in der Dropdownliste für die Konfiguration:

```json
{
  "configurations": [
    {
      "name": "Windows",
      ...
    },
    {
      "name": "with EXTERNAL_CODECS",
      ...
    }
  ]
}
```
### <a name="define-tasks-with-tasksvsjson"></a>Definieren Sie Aufgaben im Zusammenhang mit tasks.vs.json
Sie können automatisieren Buildskripts oder andere externe Vorgänge auf die Dateien, die Sie in Ihrem aktuellen Arbeitsbereich verfügen, indem Sie sie als direkt in der IDE Aufgaben ausführen. Sie können einen neuen Task konfigurieren, indem Sie mit der rechten Maustaste auf eine Datei oder einen Ordner, und wählen **Tasks konfigurieren**. 

![Tasks für Ordner öffnen konfigurieren](media/open-folder-config-tasks.png)

Dies erstellt (oder geöffnet) der `tasks.vs.json` Datei im Ordner "VS" die Visual Studio im Stammordner des Projekts erstellt. Sie können jede beliebige Aufgabe in dieser Datei zu definieren und dann aus der **Projektmappen-Explorer** Kontextmenü. Das folgende Beispiel zeigt eine tasks.vs.json-Datei, die eine einzelne Aufgabe definiert. `taskName`definiert den angezeigten Namen im Kontextmenü an. `appliesTo`definiert, welche Dateien für der Befehl ausgeführt werden kann. Die `command` Eigenschaft bezieht sich auf die PATHEXT für die Umgebung, die den Pfad für die Konsole (cmd.exe unter Windows) identifiziert. Die `args` Eigenschaft gibt die Befehlszeile aufgerufen werden. Die `${file}` Makro ruft die ausgewählte Datei in **Projektmappen-Explorer**. Im folgende Beispiel wird der Dateiname der aktuell ausgewählten cpp-Datei angezeigt.

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskName": "Echo filename",
      "appliesTo": "*.cpp",
      "type": "command",
      "command": "${env.COMSPEC}",
      "args": ["echo ${file}"]
    }
  ]
}
```
Nach dem Speichern tasks.vs.json, können Sie mit der rechten Maustaste alle cpp-Datei im Ordner "", wählen Sie **Echo Filename** aus dem Kontextmenü, und finden Sie unter der Dateinamen im Ausgabefenster angezeigt.

#### <a name="appliesto"></a>appliesTo
Sie können Aufgaben für alle Dateien oder Ordner erstellen, indem Sie ihren Namen in der `appliesTo` Feld, z. B. `"appliesTo" : "hello.cpp"`. Die folgenden Dateimasken können als Werte verwendet werden:
|||
|-|-|
|`"*"`| Task ist für alle Dateien und Ordner im Arbeitsbereich verfügbar|
|`"*/"`| Task ist für alle Ordner im Arbeitsbereich verfügbar|
|`"*.cpp"`| Task ist für alle Dateien mit der Erweiterung .cpp im Arbeitsbereich verfügbar|
|`"/*.cpp"`| Aufgabe ist verfügbar, um alle Dateien mit der Erweiterung .cpp im Stammverzeichnis des Arbeitsbereichs|
|`"src/*/"`| Aufgabe ist verfügbar, um alle Unterordner des Ordners "Src"|
|`"makefile"`| Task ist für alle Makefile-Dateien im Arbeitsbereich verfügbar|
|`"/makefile"`| Aufgabe steht nur für die Makefile im Stammverzeichnis des Arbeitsbereichs|

#### <a name="output"></a>Ausgabe
Verwenden der `output` Eigenschaft, um die ausführbare Datei anzugeben, die gestartet wird, wenn Sie drücken **F5**. Zum Beispiel:

```json
      "output": "${workspaceRoot}\\bin\\hellomake.exe" 
```

#### <a name="macros-for-tasksvsjson"></a>Makros für die tasks.vs.json

|||
|-|-|
|`${env.<VARIABLE>}`| Gibt jede Umgebungsvariable (z. B. ${Env. Pfad} ${env.COMSPEC} "und" usw.), die für die Developer-Eingabeaufforderung festgelegt. Weitere Informationen finden Sie unter [Developer-Eingabeaufforderung für Visual Studio](/dotnet/framework/tools/developer-command-prompt-for-vs).|
|`${workspaceRoot}`| den vollständigen Pfad zu den Arbeitsbereichsordner (beispielsweise "C:\sources\hello")|
|`${file}`| der vollständige Pfad der Datei oder Ordner ausgewählt haben, führen Sie diesen Task für (z. B. "C:\sources\hello\src\hello.cpp")|
|`${relativeFile}`| der relative Pfad der Datei oder Ordner (z. B. "src\hello.cpp")|
|`${fileBasename}`| der Name der Datei ohne Pfad oder eine Erweiterung (z. B. "Hello")|
|`${fileDirname}`| der vollständige Pfad zur Datei, mit Ausnahme der Dateiname (z. B. "C:\sources\hello\src")|
|`${fileExtname}`| die Erweiterung der ausgewählten Datei (z. B. ".cpp")|

#### <a name="custom-macros"></a>Benutzerdefinierte Makros
Fügen Sie ein benutzerdefiniertes Makro in tasks.vs.json definieren, eine Name-Wert-Paar vor der Aufgabe blockiert. Das folgende Beispiel definiert ein Makro mit dem Namen `outDir` der belegt wurde der `args` Eigenschaft:

```json
{
"version": "0.2.1",
  "outDir": "${workspaceRoot}\\bin",
  "tasks": [
    {
      "taskName": "List outputs",
      "*",
      "type": "command",
      "command": "${env.COMSPEC}",
      "args": [
        "dir ${outDir}"
      ]
    }
  ]
```

### <a name="configure-debugging-parameters-with-launchvsjson"></a>Konfigurieren Sie die Parameter von debugging mit launch.vs.json
Um Befehlszeilenargumente für das Programm anzupassen, mit der Maustaste, auf die ausführbare Datei in **Projektmappen-Explorer** , und wählen Sie **Debug- und Starteinstellungen**. Dies öffnet ein vorhandenes `launch.vs.json` Datei, oder falls keiner vorhanden ist, erstellen Sie eine neue Datei mit den Informationen zum ausgewählten Programm aufgefüllt. 

Um zusätzliche Argumente anzugeben, fügen Sie einfach in die `args` JSON-Array, wie im folgenden Beispiel gezeigt:

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "default",
      "project": "CPP\\7zip\\Bundles\\Alone\\O\\7za.exe",
      "name": "7za.exe list content of helloworld.zip",
      "args": [ "l", "d:\\sources\\helloworld.zip" ]
    }
  ]
}
```

Wenn Sie diese Datei zu speichern, die neue Konfiguration wird in der Dropdownliste für die Debug-Ziele angezeigt und können Sie auswählen, für den Debugger zu starten. Sie können beliebig viele Konfigurationen wie, für eine beliebige Anzahl von ausführbaren Dateien gewünscht zu debuggen, erstellen. Wenn Sie drücken **F5** nun der Debugger starten und erreicht alle Breakpoints, die Sie möglicherweise bereits festgelegt. Alle vertraut Debuggerfenster und ihre Funktionen sind jetzt verfügbar.

## <a name="see-also"></a>Siehe auch
[IDE und Tools für Visual C++-Entwicklung](ide-and-tools-for-visual-cpp-development.md)

