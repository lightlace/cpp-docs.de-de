---
title: Verwenden von „Ordner öffnen“ mit Projekten in Visual C++ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/01/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Open Folder Projects in Visual C++
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d4444e70ec158d7afa35c3955bbef9af4bfa12f2
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43758877"
---
# <a name="open-folder-projects-in-visual-c"></a>Verwenden von „Ordner öffnen“ mit Projekten in Visual C++

In Visual Studio 2017 und höher können Sie das Feature „Ordner öffnen“ verwenden, um einen Ordner mit Quelldateien öffnen und sofort mit dem Programmieren beginnen zu können. Dabei wird unter anderem IntelliSense, das Durchsuchen, Refactoring und Debuggen unterstützt. Es werden keine SLN- oder VCXPROJ-Dateien geladen. Bei Bedarf können Sie benutzerdefinierte Tasks sowie Build- und Startparameter über einfache JSON-Dateien angeben. Durch „Ordner öffnen“ kann Visual C++ nun nicht nur lose Dateisammlungen unterstützen, sondern auch nahezu jedes Buildsystem, z.B. CMake, Ninja, QMake (für Qt-Projekte), gyp, SCons, Gradle und Buck. 

Klicken Sie im Hauptmenü auf *Datei > Öffnen > Ordner*, oder drücken Sie *STRG+UMSCHALT+ALT+O*, um „Ordner öffnen“ zu verwenden. Der Projektmappen-Explorer zeigt sofort alle Dateien im Ordner an. Sie können auf eine beliebige Datei klicken, um mit der Bearbeitung zu beginnen. Visual Studio beginnt im Hintergrund damit, die Dateien zu indizieren, um IntelliSense, Navigation und Refactoringfunktionen zu ermöglichen. Während Sie Dateien bearbeiten, erstellen, verschieben und löschen, verfolgt Visual Studio die Änderungen automatisch nach und aktualisiert den IntelliSense-Index kontinuierlich. 
  
## <a name="cmake-projects"></a>CMake-Projekte
CMake ist in die Visual Studio-IDE als „CMake-Tools für Visual C++“ integriert. Dabei handelt es sich um eine Komponente der Workload für C++-Desktopentwicklung. Weitere Informationen finden Sie unter [CMake-Tools für Visual C++](cmake-tools-for-visual-cpp.md).
 
## <a name="qmake-projects-that-target-the-qt-framework"></a>QMake-Projekte für das Qt-Framework
Sie können CMake-Tools für Visual C++ verwenden, um Qt für das Erstellen von Qt-Projekten anzuzielen. Alternativ können Sie für Visual Studio 2015 oder 2017 die [Qt-Erweiterung für Visual Studio](https://download.qt.io/development_releases/vsaddin/) verwenden.

## <a name="gyp-cons-scons-buck-etc"></a>gyp, Cons, SCons, Buck usw.
Sie können ein beliebiges Buildsystem in Visual C++ verwenden und trotzdem die Vorteile der Visual C++-IDE und des Visual C++-Debuggers nutzen. Wenn Sie den Stammordner Ihres Projekts öffnen, verwendet Visual C++ Heuristiken, um die Quelldateien für IntelliSense und das Durchsuchen zu indizieren. Sie können Hinweise zur Struktur Ihres Codes einfügen, indem Sie die Datei „CppProperties.json“ bearbeiten. Auf ähnliche Weise können Sie Ihr Buildprogramm konfigurieren, indem Sie die Datei „launch.vs.json“ bearbeiten. 

## <a name="configuring-open-folder-projects"></a>Konfigurieren von Projekten, bei denen „Ordner öffnen“ verwendet wird
Sie können ein Projekt, bei dem „Ordner öffnen“ verwendet wird, über drei JSON-Dateien anpassen:
|||
|-|-|
|CppProperties.json|Geben Sie benutzerdefinierte Konfigurationsinformationen für das Durchsuchen an. Erstellen Sie diese Datei bei Bedarf im Stammordner des Projekts.|
|launch.vs.json|Geben Sie Befehlszeilenargumente an. Der Zugriff erfolgt über das Kontextmenüelement **Einstellungen für Debuggen und Starten** im **Projektmappen-Explorer**.|
|tasks.vs.json|Geben Sie benutzerdefinierte Buildbefehle und Compileroptionen an. Der Zugriff erfolgt über das Kontextmenüelement **Tasks konfigurieren** im **Projektmappen-Explorer**.|

### <a name="configure-intellisense-with-cpppropertiesjson"></a>Konfigurieren von IntelliSense mit „CppProperties.json“
IntelliSense und das Verhalten beim Durchsuchen hängen teilweise von der aktiven Buildkonfiguration ab, die #include-Pfade, Compileroptionen und andere Parameter definiert. Standardmäßig stellt Visual Studio Debug- und Releasekonfigurationen bereit. Bei einigen Projekten müssen Sie möglicherweise benutzerdefinierte Konfigurationen erstellen, damit IntelliSense und die Suchfunktionen Ihren Code vollständig verstehen. Erstellen Sie eine Datei namens „CppProperties.json“ im Stammordner, um eine neue Konfiguration zu definieren. Im Folgenden ein Beispiel:

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
Eine Konfiguration kann folgende Eigenschaften aufweisen:

|||  
|-|-| 
|`name`|den Konfigurationsnamen, der in der Dropdownliste für die C++-Konfiguration angezeigt wird|
|`includePath`|die Ordnerliste, die im Includepfad (entspricht bei den meisten Compilern /I) angegeben sein sollte|
|`defines`|die Liste der Makros, die definiert sein sollten (entspricht bei den meisten Compilern /D)|
|`compilerSwitches`|eine oder mehrere zusätzliche Optionen, die das Verhalten von IntelliSense beeinflussen können|
|`forcedInclude`|ein Header, der in jeder Kompilierungseinheit automatisch eingefügt wird (entspricht /F bei MSVC oder -include bei Clang)|
|`undefines`|die Liste der Makros, die nicht definiert sind (entspricht /U bei MSVC)|
|`intelliSenseMode`|die zu verwendende IntelliSense-Engine. Sie können architekturspezifische Varianten für MSVC, gcc oder Clang angeben:
- msvc-x86 (Standard)
- msvc-x64
- msvc-arm
- windows-clang-x86
- windows-clang-x64
- windows-clang-arm
- Linux-x64
- Linux-x86
- Linux-arm
- gccarm

#### <a name="environment-variables"></a>Umgebungsvariablen
„CppProperties.json“ unterstützt die Erweiterung von Systemumgebungsvariablen zum Einfügen von Pfaden und anderen Eigenschaftswerten. Die Syntax zum Erweitern einer Umgebungsvariable (`%FOODIR%`) lautet `${env.FOODIR}`. Folgende vom System definierte Variablen werden ebenfalls unterstützt:

|Variablenname|Beschreibung |  
|-----------|-----------------|
|vsdev|Die Standardumgebung von Visual Studio|
|msvc_x86|Kompiliert mithilfe von x86-Tools für x86|
|msvc_arm|Kompiliert mithilfe von x86-Tools für ARM|
|msvc_arm64|Kompiliert mithilfe von x86-Tools für ARM64|
|msvc_x86_x64|Kompiliert mithilfe von x86-Tools für AMD64|
|msvc_x64_x64|Kompiliert mithilfe von 64-Bit-Tools für AMD64|
|msvc_arm_x64|Kompiliert mithilfe von 64-Bit-Tools für ARM|
|msvc_arm64_x64|Kompiliert mithilfe von 64-Bit-Tools für ARM64|

Wenn die Linux-Workload installiert ist, können folgende Umgebungen verwendet werden, um Linux und WSL remote anzuzielen:

|Variablenname|Beschreibung |  
|-----------|-----------------|
|linux_x86|Hiermit wird x86 Linux als Remotezielversion festgelegt.|
|linux_x64|Hiermit wird x64 Linux als Remotezielversion festgelegt.|
|linux_arm|Hiermit wird ARM Linux als Remotezielversion festgelegt.|

Sie können benutzerdefinierte Umgebungsvariablen in „CppProperties.json“ entweder global oder pro Konfiguration definieren. Im folgenden Beispiel wird veranschaulicht, wie Standardumgebungsvariablen und benutzerdefinierte Umgebungsvariablen deklariert und verwendet werden können. Die globale Eigenschaft **environments** deklariert eine Variable namens **INCLUDE**, die von jeder Konfiguration verwendet werden kann:

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "INCLUDE": "${workspaceRoot}\\src\\includes"
    }
  ],
 
  "configurations": [
    {
      "inheritEnvironments": [
        // Inherit the MSVC 32-bit environment and toolchain.
        "msvc_x86"
      ],
      "name": "x86",
      "includePath": [
        // Use the include path defined above.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "msvc-x86"
    },
    {
      "inheritEnvironments": [
        // Inherit the MSVC 64-bit environment and toolchain.
        "msvc_x64"
      ],
      "name": "x64",
      "includePath": [
        // Use the include path defined above.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "msvc-x64"
    }
  ]
}
```
Sie können eine **environments**-Eigenschaft ebenfalls innerhalb einer Konfiguration definieren, sodass sie nur für diese Konfiguration gilt und alle globalen Variablen mit gleichem Namen überschreibt. Im folgenden Beispiel definiert die x64-Konfiguration eine lokale **INCLUDE**-Variable, die den globalen Wert überschreibt:

```json
{
  "environments": [
    {
      "INCLUDE": "${workspaceRoot}\\src\\includes"
    }
  ],
 
  "configurations": [
    {
      "inheritEnvironments": [
        "msvc_x86"
      ],
      "name": "x86",
      "includePath": [
        // Use the include path defined in the global environments property.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "msvc-x86"
    },
    {
      "environments": [
        {
          // Append 64-bit specific include path to env.INCLUDE.
          "INCLUDE": "${env.INCLUDE};${workspaceRoot}\\src\\includes64"
        }
      ],
 
      "inheritEnvironments": [
        "msvc_x64"
      ],
      "name": "x64",
      "includePath": [
        // Use the include path defined in the local environments property.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "msvc-x64"
    }
  ]
}
```

Alle Standardumgebungsvariablen und benutzerdefinierten Umgebungsvariablen sind ebenfalls in „tasks.vs.json“ und „launch.vs.json“ verfügbar.

#### <a name="macros"></a>Makros
Sie können innerhalb von „CppProperties.json“ auf folgende integrierte Makros zugreifen:
|||
|-|-|
|`${workspaceRoot}`| den vollständigen Pfad zum Arbeitsbereichordner|
|`${projectRoot}`| den vollständigen Pfad zum Ordner von „CppProperties.json“|
|`${vsInstallDir}`| den vollständigen Pfad zum Ordner, indem die ausgeführte Instanz von Visual Studio 2017 installiert ist|

Wenn in Ihrem Projekt beispielsweise ein Includeordner sowie „windows.h“ und andere allgemeine Header des Windows SDK vorhanden sind, sollten Sie die Konfigurationsdatei „CppProperties.json“ mit folgenden Includeelementen aktualisieren:

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

**Hinweis:** `%WindowsSdkDir%` und `%VCToolsInstallDir%` werden nicht als globale Umgebungsvariablen festgelegt, um sicherzustellen, dass „devenv.exe“ über eine Developer-Eingabeaufforderung für Visual Studio 2017 ausgeführt wird, die diese Variablen definiert.

Wenn Sie IntelliSense-Fehler beheben möchten, die von fehlenden Includepfaden verursacht wurden, öffnen Sie die **Fehlerliste**, und filtern Sie deren Ausgabe nach „Nur IntelliSense“ und dem Fehlercode E1696 „Die Datei ‚Dateiname‘ kann nicht geöffnet werden“. 

Sie können eine beliebige Anzahl von Konfigurationen in „CppProperties.json“ erstellen. Jede davon wird in der Dropdownliste für Konfigurationen angezeigt:

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
### <a name="define-tasks-with-tasksvsjson"></a>Definieren von Tasks mit „tasks.vs.json“
Sie können Buildskripts oder andere externe Vorgänge in den Dateien automatisieren, die sich in Ihrem aktuellen Arbeitsbereich befinden, indem Sie sie direkt in der IDE als Tasks ausführen. Sie können einen neuen Task konfigurieren, indem Sie mit der rechten Maustaste auf eine Datei oder einen Ordner klicken und **Tasks konfigurieren** auswählen. 

![Konfigurieren von Tasks für „Ordner öffnen“](media/open-folder-config-tasks.png)

Dadurch wird die `tasks.vs.json`-Datei im Ordner „.vs“ erstellt oder geöffnet, die Visual Studio im Stammordner des Projekts erstellt. Sie können in dieser Datei einen beliebigen Task definieren und diesen dann über das Kontextmenü des **Projektmappen-Explorers** aufrufen. Das folgende Beispiel zeigt eine tasks.vs.json-Datei, die einen einzelnen Task definiert. `taskName` definiert den Namen, der im Kontextmenü angezeigt wird. `appliesTo` definiert, für welche Dateien der Befehl ausgeführt werden kann. Die `command`-Eigenschaft bezieht sich auf die Umgebungsvariable „COMSPEC“, die den Pfad für die Konsole („cmd.exe“ unter Windows) identifiziert. Sie können ebenfalls auf Umgebungsvariablen verweisen, die in „CppProperties.json“ oder „CMakeSettings.json“ definiert sind. Die `args`-Eigenschaft gibt die Befehlszeile an, die aufgerufen werden soll. Das `${file}`-Makro ruft die ausgewählte Datei im **Projektmappen-Explorer** ab. Im folgenden Beispiel wird der Dateiname der aktuell ausgewählten CPP-Datei angezeigt.

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



#### <a name="appliesto"></a>appliesTo
Sie können Tasks für jede Datei und jeden Ordner erstellen, indem Sie den Namen der Datei bzw. des Ordners im Feld `appliesTo` angeben. Beispiel: `"appliesTo" : "hello.cpp"`. Die folgenden Dateimasken können als Werte verwendet werden:
|||
|-|-|
|`"*"`| Der Task ist für alle Dateien und Ordner im Arbeitsbereich verfügbar.|
|`"*/"`| Der Task ist für alle Ordner im Arbeitsbereich verfügbar.|
|`"*.cpp"`| Der Task ist für alle Dateien mit der Erweiterung „.cpp“ im Arbeitsbereich verfügbar.|
|`"/*.cpp"`| Der Task ist für alle Dateien mit der Erweiterung „.cpp“ im Stammverzeichnis des Arbeitsbereichs verfügbar.|
|`"src/*/"`| Der Task ist für alle Unterordner des Ordners „src“ verfügbar.|
|`"makefile"`| Der Task ist für alle makefile-Dateien im Arbeitsbereich verfügbar.|
|`"/makefile"`| Der Task ist nur für die makefile-Datei im Stammverzeichnis des Arbeitsbereichs verfügbar.|

#### <a name="output"></a>Ausgabe
Verwenden Sie die `output`-Eigenschaft, um die ausführbare Datei anzugeben, die gestartet wird, wenn Sie **F5** drücken. Zum Beispiel:

```json
      "output": "${workspaceRoot}\\bin\\hellomake.exe" 
```

#### <a name="macros-for-tasksvsjson"></a>Makros für „tasks.vs.json“

|||
|-|-|
|`${env.<VARIABLE>}`| Gibt jede Umgebungsvariable an (z.B. ${env.PATH}, ${env.COMSPEC} usw.), die für die Developer-Eingabeaufforderung festgelegt ist. Weitere Informationen finden Sie unter [Developer-Eingabeaufforderung für Visual Studio](/dotnet/framework/tools/developer-command-prompt-for-vs).|
|`${workspaceRoot}`| Der vollständige Pfad zum Arbeitsbereichsordner (z.B. C:\sources\hello).|
|`${file}`| Der vollständige Pfad zur Datei oder zum Ordner, für die bzw. den dieser Task ausgeführt werden soll (z.B. C:\sources\hello\src\hello.cpp).|
|`${relativeFile}`| Der relative Pfad zur Datei oder zum Ordner (z.B. src\hello.cpp).|
|`${fileBasename}`| Der Name der Datei ohne Pfad oder Erweiterung (z.B. „hello“).|
|`${fileDirname}`| Der vollständige Pfad zur Datei ohne den Dateinamen (z.B. C:\sources\hello\src).|
|`${fileExtname}`| Die Erweiterung der ausgewählten Datei (z.B. „.cpp“).|

#### <a name="custom-macros"></a>Benutzerdefinierte Makros
Fügen Sie ein Name/Wert-Paar zu den Codeblöcken des Tasks hinzu, um ein benutzerdefiniertes Makro in „tasks.vs.json“ zu definieren. Im folgenden Beispiel wird ein Makro namens `outDir` definiert, das in der Eigenschaft `args` verwendet wird:

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

### <a name="configure-debugging-parameters-with-launchvsjson"></a>Konfigurieren von Parametern für das Debuggen mithilfe von „launch.vs.json“
Wenn Sie die Befehlszeilenargumente Ihres Programms anpassen möchten, klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die ausführbare Datei, und wählen Sie **Debug- und Starteinstellungen** aus. Dadurch wird eine vorhandene `launch.vs.json`-Datei geöffnet. Wenn keine vorhanden ist, wird eine neue Datei erstellt, die mit vorab mit den von Ihnen festgelegten Informationen zum Programm aufgefüllt wird. 

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
[IDE und Tools für Visual C++-Entwicklung](ide-and-tools-for-visual-cpp-development.md)

