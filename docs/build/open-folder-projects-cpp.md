---
title: „Ordner öffnen“-Unterstützung für C++-Buildsysteme in Visual Studio
ms.date: 12/02/2019
helpviewer_keywords:
- Open Folder Projects in Visual Studio
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
ms.openlocfilehash: 8342060e7286c1089312874199bf341ec36bed62
ms.sourcegitcommit: 6c1960089b92d007fc28c32af1e4bef0f85fdf0c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2019
ms.locfileid: "75556692"
---
# <a name="open-folder-support-for-c-build-systems-in-visual-studio"></a>„Ordner öffnen“-Unterstützung für C++-Buildsysteme in Visual Studio

::: moniker range="vs-2015"

Die Funktion "Ordner öffnen" ist in Visual Studio 2017 und höher verfügbar.

::: moniker-end

::: moniker range=">=vs-2017"

In Visual Studio 2017 und höher können Sie das Feature „Ordner öffnen“ verwenden, um einen Ordner mit Quelldateien öffnen und sofort mit dem Programmieren beginnen zu können. Dabei wird unter anderem IntelliSense, das Durchsuchen, Refactoring und Debuggen unterstützt. Während Sie Dateien bearbeiten, erstellen, verschieben und löschen, verfolgt Visual Studio die Änderungen automatisch nach und aktualisiert den IntelliSense-Index kontinuierlich. Es werden keine SLN- oder VCXPROJ-Dateien geladen. Bei Bedarf können Sie benutzerdefinierte Tasks sowie Build- und Startparameter über einfache JSON-Dateien angeben. Mit dieser Funktion können Sie ein beliebiges Drittanbieter-Buildsystem in Visual Studio integrieren. Allgemeine Informationen zu „Ordner öffnen“ finden Sie unter [Entwickeln von Code in Visual Studio ohne Projekte oder Projektmappen](/visualstudio/ide/develop-code-in-visual-studio-without-projects-or-solutions).

## <a name="cmake-and-qt"></a>Cmake und Qt

Cmake ist in der Visual Studio C++ -IDE als Komponente der Desktop-Arbeitsauslastung integriert. Der Workflow für cmake ist nicht mit dem in diesem Artikel beschriebenen Workflow identisch. Wenn Sie cmake verwenden, finden Sie weitere Informationen unter [cmake-Projekte in Visual Studio](cmake-projects-in-visual-studio.md). Sie können auch cmake verwenden, um Qt-Projekte zu erstellen, oder Sie können die [Visual Studio-Erweiterung](https://download.qt.io/development_releases/vsaddin/) für Visual Studio 2015 oder Visual Studio 2017 verwenden.

## <a name="other-build-systems"></a>Andere Buildsysteme

Wenn Sie die Visual Studio-IDE mit einem Buildsystem oder einem Compilertoolset verwenden möchten, das nicht direkt im Hauptmenü unterstützt wird, wählen Sie **Datei | Öffnen | Ordner** oder drücken Sie **STRG + UMSCHALT + ALT + O**. Navigieren Sie zu dem Ordner, der die Quell Code Dateien enthält. Um das Projekt zu erstellen, konfigurieren Sie IntelliSense, und legen Sie Debugparameter fest. Fügen Sie drei JSON-Dateien hinzu:

| | |
|-|-|
|CppProperties.json|Geben Sie benutzerdefinierte Konfigurationsinformationen für das Durchsuchen an. Erstellen Sie diese Datei bei Bedarf im Stammordner des Projekts. (Wird in CMake-Projekten nicht verwendet.)|
|tasks.vs.json|Benutzerdefinierte Buildbefehle angeben. Der Zugriff erfolgt über das Kontextmenüelement **Tasks konfigurieren** im **Projektmappen-Explorer**.|
|launch.vs.json|Geben Sie Befehlszeilenargumente für den Debugger an. Der Zugriff erfolgt über das Kontextmenüelement **Einstellungen für Debuggen und Starten** im **Projektmappen-Explorer**.|

## <a name="configure-code-navigation-with-cpppropertiesjson"></a>Konfigurieren der Code Navigation mit cppproperties. JSON

Damit IntelliSense und das Browser Verhalten wie " **Gehe zu Definition** " ordnungsgemäß funktionieren, muss Visual Studio wissen, welcher Compiler Sie verwenden, wo sich die System Header befinden und wo sich weitere Includedateien befinden, wenn Sie sich nicht direkt im geöffneten Ordner (Arbeitsbereichs Ordner) befinden. Zum Angeben einer Konfiguration können Sie in der Dropdown Liste der Hauptsymbol Leiste die Option **Konfigurationen verwalten** auswählen:

![Dropdown Menü "Konfigurationen verwalten"](media/manage-configurations-dropdown.png)

Visual Studio bietet die folgenden Standardkonfigurationen:

![Standardkonfigurationen](media/default-configurations.png)

Wenn Sie z. b. **x64-Debug**auswählen, erstellt Visual Studio eine Datei mit dem Namen *cppproperties. JSON* im Stamm Projektordner:

```json
{
  "configurations": [
    {
      "inheritEnvironments": [
        "msvc_x64"
      ],
      "name": "x64-Debug",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "defines": [
        "WIN32",
        "_DEBUG",
        "UNICODE",
        "_UNICODE"
      ],
      "intelliSenseMode": "windows-msvc-x64"
    }
  ]
}
```

Diese Konfiguration erbt die Umgebungsvariablen der Visual Studio [x64-Developer-Eingabeaufforderung](building-on-the-command-line.md). Eine dieser Variablen ist `INCLUDE`, und Sie können hier mithilfe des `${env.INCLUDE}`-Makros darauf verweisen. Die `includePath`-Eigenschaft teilt Visual Studio mit, wo nach allen Quellen gesucht werden soll, die für IntelliSense benötigt werden. In diesem Fall wird Folgendes angezeigt: "alle Verzeichnisse, die von der INCLUDE-Umgebungsvariablen angegeben werden, und auch alle Verzeichnisse in der aktuellen Arbeitsordner Struktur." Die `name`-Eigenschaft ist der Name, der in der Dropdown Liste angezeigt wird, und Sie können beliebig sein. Die `defines`-Eigenschaft bietet Hinweise für IntelliSense, wenn Sie bedingte Kompilierungs Blöcke erkennen. Die `intelliSenseMode`-Eigenschaft bietet einige zusätzliche Hinweise auf der Grundlage des compilertyps. Für MSVC, gcc und clang stehen mehrere Optionen zur Verfügung.

> [!NOTE]
> Wenn Visual Studio die Einstellungen in " *cppproperties. JSON*" ignoriert, versuchen Sie, eine Ausnahme zu Ihrer *gitignore* -Datei hinzuzufügen, wie im folgenden Beispiel: `!/CppProperties.json`.

## <a name="default-configuration-for-mingw-w64"></a>Standardkonfiguration für MinGW-W64

Wenn Sie die MinGW-W64-Konfiguration hinzufügen, sieht der JSON-Code Folgendes aus:

```json
{
  {
      "inheritEnvironments": [
        "mingw_64"
      ],
      "name": "Mingw64",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "intelliSenseMode": "linux-gcc-x64",
      "environments": [
        {
          "MINGW64_ROOT": "C:\\msys64\\mingw64",
          "BIN_ROOT": "${env.MINGW64_ROOT}\\bin",
          "FLAVOR": "x86_64-w64-mingw32",
          "TOOLSET_VERSION": "9.1.0",
          "PATH": "${env.BIN_ROOT};${env.MINGW64_ROOT}\\..\\usr\\local\\bin;${env.MINGW64_ROOT}\\..\\usr\\bin;${env.MINGW64_ROOT}\\..\\bin;${env.PATH}",
          "INCLUDE": "${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION};${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION}\\tr1;${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION}\\${env.FLAVOR}",
          "environment": "mingw_64"
        }
      ]
    }
}
```

Beachten Sie den `environments`-Block. Es definiert Eigenschaften, die sich wie Umgebungsvariablen Verhalten und nicht nur in der *cppproperties. JSON* -Datei verfügbar sind, sondern auch in den anderen Konfigurationsdateien " *Task. vs. JSON* " und " *Launch. vs. JSON*". Die `Mingw64` Konfiguration erbt die `mingw_w64` Umgebung und verwendet deren `INCLUDE`-Eigenschaft, um den Wert für `includePath`anzugeben. Sie können dieser Array Eigenschaft nach Bedarf weitere Pfade hinzufügen.

Die `intelliSenseMode`-Eigenschaft ist auf einen Wert festgelegt, der für gcc geeignet ist. Weitere Informationen zu diesen Eigenschaften finden Sie unter [cppproperties Schema Reference](cppproperties-schema-reference.md).

Wenn alles ordnungsgemäß funktioniert, wird IntelliSense aus den gcc-Headern angezeigt, wenn Sie mit dem Mauszeiger auf einen Typ zeigen:

![GCC-IntelliSense](media/gcc-intellisense.png)

## <a name="enable-intellisense-diagnostics"></a>IntelliSense-Diagnose aktivieren

Wenn die erwartete IntelliSense-Funktion nicht angezeigt wird, können Sie Probleme **beheben, indem** Sie zu Extras > **Optionen** > **Text-Editor** > **CC++ /**  > **erweitert** wechseln und **Protokollierung aktivieren** auf **wahr**festlegen. Legen Sie zunächst den **Protokolliergrad** auf 5 fest, und **Protokollieren** Sie die Filter auf 8.

![Diagnoseprotokollierung](media/diagnostic-logging.png)

Die Ausgabe wird an den **Ausgabefenster** weitergeleitet und ist sichtbar, wenn Sie **Ausgabe anzeigen von: C++ visuelles Protokoll*auswählen. Die Ausgabe enthält unter anderem die Liste der tatsächlichen Includepfade, die IntelliSense zu verwenden versucht. Wenn die Pfade nicht mit denen in " *cppproperties. JSON*" identisch sind, schließen Sie den Ordner, und löschen Sie den Unterordner " *. vs* ", der zwischengespeicherte Browserdaten enthält.

### <a name="define-build-tasks-with-tasksvsjson"></a>Definieren von Buildtasks mit „tasks.vs.json“

Sie können Buildskripts oder andere externe Vorgänge in den Dateien automatisieren, die sich in Ihrem aktuellen Arbeitsbereich befinden, indem Sie sie direkt in der IDE als Tasks ausführen. Sie können einen neuen Task konfigurieren, indem Sie mit der rechten Maustaste auf eine Datei oder einen Ordner klicken und **Tasks konfigurieren** auswählen.

![Konfigurieren von Tasks für „Ordner öffnen“](media/configure-tasks.png)

Dadurch wird die Datei " *Tasks. vs. JSON* " im Ordner ". vs" erstellt (oder geöffnet), der von Visual Studio im Stamm Projektordner erstellt wird. Sie können in dieser Datei einen beliebigen Task definieren und diesen dann über das Kontextmenü des **Projektmappen-Explorers** aufrufen. Um das gcc-Beispiel fortzusetzen, zeigt der folgende Code Ausschnitt eine komplette Datei " *Tasks. vs. JSON* " mit einer einzigen Aufgabe an, die zum Erstellen eines Projekts " *g + +. exe* " aufruft. Angenommen, das Projekt enthält eine einzelne Datei mit dem Namen *Hello. cpp*.

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskLabel": "build hello",
      "appliesTo": "/",
      "type": "default",
      "command": "g++",
      "args": [
        "-g",
        "-o",
        "hello",
        "hello.cpp"
      ]
    }
  ]
}

```

Die JSON-Datei wird im *vs* -Unterordner abgelegt. Um diesen Ordner anzuzeigen, klicken Sie oben auf der **Projektmappen-Explorer**auf die Schaltfläche **alle Dateien anzeigen** . Sie können diesen Task ausführen, indem Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf den Stamm Knoten klicken und dann die Option **Build Hello**auswählen. Wenn die Aufgabe abgeschlossen ist, sollte die neue Datei " *Hello. exe* " in **Projektmappen-Explorer**angezeigt werden.

Sie können viele Arten von Aufgaben definieren. Das folgende Beispiel zeigt eine *Datei "Tasks. vs. JSON* ", die eine einzelne Aufgabe definiert. `taskLabel` definiert den Namen, der im Kontextmenü angezeigt wird. `appliesTo` definiert, für welche Dateien der Befehl ausgeführt werden kann. Die `command`-Eigenschaft verweist auf die COMSPEC-Umgebungsvariable, die den Pfad für die-Konsole ("*cmd. exe* " unter Windows) identifiziert. Sie können ebenfalls auf Umgebungsvariablen verweisen, die in „CppProperties.json“ oder „CMakeSettings.json“ definiert sind. Die `args`-Eigenschaft gibt die Befehlszeile an, die aufgerufen werden soll. Das `${file}`-Makro ruft die ausgewählte Datei im **Projektmappen-Explorer** ab. Im folgenden Beispiel wird der Dateiname der aktuell ausgewählten CPP-Datei angezeigt.

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskLabel": "Echo filename",
      "appliesTo": "*.cpp",
      "type": "command",
      "command": "${env.COMSPEC}",
      "args": ["echo ${file}"]
    }
  ]
}
```

Nachdem Sie " *Tasks. vs. JSON*" gespeichert haben, können Sie im Ordner mit der rechten Maustaste auf eine beliebige *cpp* -Datei klicken, im Kontextmenü **Echo filename** auswählen und den Dateinamen im Ausgabefenster anzeigen.

Weitere Informationen finden Sie unter [Tasks.vs.json schema reference (Tasks.vs.json-Schemareferenz)](tasks-vs-json-schema-reference-cpp.md).

### <a name="configure-debugging-parameters-with-launchvsjson"></a>Konfigurieren von Parametern für das Debuggen mithilfe von „launch.vs.json“

Um die Befehlszeilenargumente des Programms und die Debuganweisungen anzupassen, klicken Sie in **Projektmappen-Explorer** mit der rechten Maustaste auf die ausführbare Datei, und wählen Sie **Debuggen und Start** Dadurch wird eine vorhandene Datei " *Launch. vs. JSON* " geöffnet, oder wenn keine vorhanden ist, wird eine neue Datei mit einem Satz minimaler Start Einstellungen erstellt. Zuerst haben Sie die Wahl, welche Art von Debugsitzung Sie konfigurieren möchten. Zum Debuggen eines MinGW-W64-Projekts wählen wir **CC++ /Launch für MinGW/Cygwin (gdb)** aus. Dadurch wird eine Startkonfiguration für die Verwendung von " *gdb. exe* " mit einigen fundierten Schätz Werten zu Standardwerten erstellt. Einer dieser Standardwerte ist `MINGW_PREFIX`. Sie können den literalpfad ersetzen (wie unten gezeigt), oder Sie können eine `MINGW_PREFIX`-Eigenschaft in " *cppproperties. JSON*" definieren:

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "cppdbg",
      "name": "hello.exe",
      "project": "hello.exe",
      "cwd": "${workspaceRoot}",
      "program": "${debugInfo.target}",
      "MIMode": "gdb",
      "miDebuggerPath": "c:\\msys64\\usr\\bin\\gdb.exe",
      "externalConsole": true
    }
  ]
}

```

Um das Debuggen zu starten, wählen Sie die ausführbare Datei in der Dropdown Liste Debuggen aus, und klicken Sie

![Debugger starten](media/launch-debugger-gdb.png)

Das Dialogfeld **Initialisierungs Debugger** und ein externes Konsolenfenster, in dem das Programm ausgeführt wird, sollten angezeigt werden.

Weitere Informationen finden Sie unter " [Launch. vs. JSON Schema Reference](launch-vs-schema-reference-cpp.md)".

## <a name="launching-other-executables"></a>Starten anderer ausführbarer Dateien

Sie können Start Einstellungen für beliebige ausführbare Dateien auf dem Computer definieren. Im folgenden Beispiel wird *7za* gestartet und zusätzliche Argumente angegeben, indem Sie dem JSON-Array `args` hinzugefügt werden:

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

::: moniker-end
