---
title: „Ordner öffnen“-Unterstützung für C++-Buildsysteme in Visual Studio
ms.date: 03/21/2019
helpviewer_keywords:
- Open Folder Projects in Visual C++
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
ms.openlocfilehash: 2dedd56759b6bb49260221e22218da6f4300a970
ms.sourcegitcommit: 42e65c171aaa17a15c20b155d22e3378e27b4642
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2019
ms.locfileid: "58356087"
---
# <a name="open-folder-projects-for-c"></a>„Ordner öffnen“-Projekte für C++

In Visual Studio 2017 und höher können Sie das Feature „Ordner öffnen“ verwenden, um einen Ordner mit Quelldateien öffnen und sofort mit dem Programmieren beginnen zu können. Dabei wird unter anderem IntelliSense, das Durchsuchen, Refactoring und Debuggen unterstützt. Es werden keine SLN- oder VCXPROJ-Dateien geladen. Bei Bedarf können Sie benutzerdefinierte Tasks sowie Build- und Startparameter über einfache JSON-Dateien angeben. Allgemeine Informationen zu „Ordner öffnen“ finden Sie unter [Entwickeln von Code in Visual Studio ohne Projekte oder Projektmappen](/visualstudio/ide/develop-code-in-visual-studio-without-projects-or-solutions).

CMake ist in die Visual Studio-IDE als „CMake Tools für Visual Studio“ integriert. Dabei handelt es sich um eine Komponente der Workload für C++-Desktopentwicklung. Weitere Informationen finden Sie unter [CMake-Projekte in Visual Studio](cmake-projects-in-visual-studio.md). Für alle anderen Buildsysteme können Sie die Funktion „Ordner öffnen“ verwenden. „Ordner öffnen“ entkoppelt Code-Editor, Debugger und Analysetools effektiv vom Buildsystem und dem Compiler-Toolset. Sie können den C++-Code-Editor mit seinen umfangreichen IntelliSense-Funktionen, die Code-Analysetools und den Visual Studio-Debugger mit praktisch jedem Buildsystem verwenden, darunter CMake, Ninja, QMake (für Qt-Projekte), GYP, SCons, Gradle, Buck, Make und andere. Dies funktioniert sogar ohne Buildsystem mit einer einzelnen Datei oder einer losen Sammlung von Dateien.

Klicken Sie im Hauptmenü auf **Datei > Öffnen > Ordner**, oder drücken Sie **STRG+UMSCHALT+ALT+O**, um „Ordner öffnen“ zu verwenden. Der Projektmappen-Explorer zeigt sofort alle Dateien im Ordner an. Sie können auf eine beliebige Datei klicken, um mit der Bearbeitung zu beginnen. Visual Studio beginnt im Hintergrund damit, die Dateien zu indizieren, um IntelliSense, Navigation und Refactoringfunktionen zu ermöglichen. Während Sie Dateien bearbeiten, erstellen, verschieben und löschen, verfolgt Visual Studio die Änderungen automatisch nach und aktualisiert den IntelliSense-Index kontinuierlich. 

## <a name="qmake-projects-that-target-the-qt-framework"></a>QMake-Projekte für das Qt-Framework

Sie können CMake Tools für Visual Studio verwenden, um Qt für das Erstellen von Qt-Projekten anzuzielen. Alternativ können Sie für Visual Studio 2015 oder Visual Studio 2017 die [Qt-Erweiterung für Visual Studio](https://download.qt.io/development_releases/vsaddin/) verwenden.

## <a name="gyp-cons-scons-buck-etc"></a>gyp, Cons, SCons, Buck usw.

Sie können ein beliebiges Buildsystem in Visual Studio verwenden und trotzdem die Vorteile der C++-IDE und des C++-Debuggers nutzen. Wenn Sie den Stammordner Ihres Projekts öffnen, verwendet der C++-Code-Editor Heuristiken, um die Quelldateien für IntelliSense und das Durchsuchen zu indizieren. Sie können Hinweise zur Struktur Ihres Codes einfügen, indem Sie die Datei „CppProperties.json“ bearbeiten. Auf ähnliche Weise können Sie Ihr Buildprogramm konfigurieren und aufrufen, indem Sie die Datei „launch.vs.json“ bearbeiten.

## <a name="configuring-open-folder-projects"></a>Konfigurieren von Projekten, bei denen „Ordner öffnen“ verwendet wird

Sie können ein Projekt, bei dem „Ordner öffnen“ verwendet wird, über drei JSON-Dateien anpassen:

| | |
|-|-|
|CppProperties.json|Geben Sie benutzerdefinierte Konfigurationsinformationen für das Durchsuchen an. Erstellen Sie diese Datei bei Bedarf im Stammordner des Projekts. (Wird in CMake-Projekten nicht verwendet.)|
|tasks.vs.json|Geben Sie benutzerdefinierte Buildbefehle und Compileroptionen an. Der Zugriff erfolgt über das Kontextmenüelement **Tasks konfigurieren** im **Projektmappen-Explorer**.|
|launch.vs.json|Geben Sie Befehlszeilenargumente für den Debugger an. Der Zugriff erfolgt über das Kontextmenüelement **Einstellungen für Debuggen und Starten** im **Projektmappen-Explorer**.|

### <a name="configure-intellisense-and-browsing-hints-with-cpppropertiesjson"></a>Konfigurieren von IntelliSense und Durchsuchen von Hinweisen mit „CppProperties.json“

IntelliSense und das Verhalten beim Durchsuchen hängen teilweise von der aktiven Buildkonfiguration ab, die #include-Pfade, Compileroptionen und andere Parameter definiert. Standardmäßig stellt Visual Studio Debug- und Releasekonfigurationen bereit. CMake-Projekte verwenden dafür die „CMakeSettings.json“-Datei und die „CMakeLists.txt“-Dateien. Für andere Arten von „Ordner öffnen“-Projekten müssen Sie möglicherweise eine benutzerdefinierte Konfiguration erstellen, damit IntelliSense und die Suchfunktionen Ihren Code vollständig verstehen. Erstellen Sie eine Datei namens „CppProperties.json“ im Stammordner, um eine neue Konfiguration zu definieren. Im Folgenden ein Beispiel:

```json
{
  "configurations": [
    {
      "name": "Windows x64",
      "includePath": [ "include" ],
      "defines": [ "_DEBUG" ],
      "compilerSwitches": "/std:c++17",
      "intelliSenseMode": "windows-msvc-x64",
      "forcedInclude": [ "pch.h" ],
      "undefines": []
    }
  ]
}
```
Weitere Informationen finden Sie unter [CppProperties schema reference (CppProperties.json-Schemareferenz)](cppproperties-schema-reference.md).

### <a name="define-build-tasks-with-tasksvsjson"></a>Definieren von Buildtasks mit „tasks.vs.json“

Sie können Buildskripts oder andere externe Vorgänge in den Dateien automatisieren, die sich in Ihrem aktuellen Arbeitsbereich befinden, indem Sie sie direkt in der IDE als Tasks ausführen. Sie können einen neuen Task konfigurieren, indem Sie mit der rechten Maustaste auf eine Datei oder einen Ordner klicken und **Tasks konfigurieren** auswählen.

![Konfigurieren von Tasks für „Ordner öffnen“](media/open-folder-config-tasks.png)

Dies erstellt (oder geöffnet) die **"Tasks.VS.JSON"** Datei im VS-Ordner die Visual Studio im Stammordner des Projekts erstellt. Sie können in dieser Datei einen beliebigen Task definieren und diesen dann über das Kontextmenü des **Projektmappen-Explorers** aufrufen. Das folgende Beispiel zeigt eine tasks.vs.json-Datei, die einen einzelnen Task definiert. `taskName` definiert den Namen, der im Kontextmenü angezeigt wird. `appliesTo` definiert, für welche Dateien der Befehl ausgeführt werden kann. Die `command`-Eigenschaft bezieht sich auf die Umgebungsvariable „COMSPEC“, die den Pfad für die Konsole („cmd.exe“ unter Windows) identifiziert. Sie können ebenfalls auf Umgebungsvariablen verweisen, die in „CppProperties.json“ oder „CMakeSettings.json“ definiert sind. Die `args`-Eigenschaft gibt die Befehlszeile an, die aufgerufen werden soll. Das `${file}`-Makro ruft die ausgewählte Datei im **Projektmappen-Explorer** ab. Im folgenden Beispiel wird der Dateiname der aktuell ausgewählten CPP-Datei angezeigt.

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

Wenn Sie „tasks.vs.json“ gespeichert haben, können Sie mit der rechten Maustaste auf eine beliebige CPP-Datei im Ordner klicken und im Kontextmenü **Echo filename** auswählen. Anschließend wird der Dateiname im Ausgabefenster angezeigt.

Weitere Informationen finden Sie unter [Tasks.vs.json schema reference (Tasks.vs.json-Schemareferenz)](tasks-vs-json-schema-reference-cpp.md).

### <a name="configure-debugging-parameters-with-launchvsjson"></a>Konfigurieren von Parametern für das Debuggen mithilfe von „launch.vs.json“

Wenn Sie die Befehlszeilenargumente Ihres Programms anpassen möchten, klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die ausführbare Datei, und wählen Sie **Debug- und Starteinstellungen** aus. Dies öffnet ein vorhandenes **"Launch.VS.JSON"** -Datei, oder wenn keiner vorhanden ist, erstellen Sie eine neue Datei, die bereits mit den Informationen über das Programm, das Sie ausgewählt haben.

Wenn Sie zusätzliche Argumente hinzufügen möchten, fügen Sie diese wie im folgenden Beispiel dargestellt im JSON-Array `args` hinzu:

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

Wenn Sie diese Datei speichern, wird die neue Konfiguration in der Dropdownliste der Debugziele angezeigt, und Sie können auf diese klicken, um den Debugger zu starten. Sie können beliebig viele Debugkonfigurationen für beliebig viele ausführbare Dateien erstellen. Wenn Sie nun auf **F5** drücken, wird der Debugger gestartet. Dieser hält an jedem Breakpoint an, den Sie bereits festgelegt haben. Die bekannten Debuggerfenster und deren Funktionalitäten sind nun verfügbar.

## <a name="see-also"></a>Siehe auch


