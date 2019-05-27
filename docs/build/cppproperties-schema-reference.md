---
title: CppProperties.json-Schemareferenz
ms.date: 05/16/2019
helpviewer_keywords:
- CMake in Visual Studio
ms.openlocfilehash: e80f4e8a189510a9a3e8860609d74121b7cbb0ef
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837061"
---
# <a name="cpppropertiesjson-schema-reference"></a>CppProperties.json-Schemareferenz

„Ordner öffnen“-Projekte, die CMake nicht verwenden, können Projektkonfigurationseinstellungen in einer `CppProperties.json`-Datei speichern. (CMake-Projekte verwenden eine [CMakeSettings.json](customize-cmake-settings.md)-Datei.) Die Visual Studio-IDE verwendet `CppProperties.json` für IntelliSense und Codenavigation. Eine Konfiguration besteht aus Name/Wert-Paaren und definiert #include-Pfade, Compileroptionen und andere Parameter. 


## <a name="default-configurations"></a>Standardkonfigurationen

Visual Studio bietet vordefinierte Konfigurationen für x86 und x64 Debug sowie Release. Standardmäßig verfügt das Projekt in `CppProperties.json` über eine x86-Debug-Konfiguration. Klicken Sie zum Hinzufügen einer neuen Konfiguration mit der rechten Maustaste im **Projektmappen-Explorer** auf die Datei `CppProperties.json`, und wählen Sie **Konfiguration hinzufügen** aus:

![„Ordner öffnen“: „Konfiguration hinzufügen“](media/open-folder-add-config.png "„Ordner öffnen“: „Konfiguration hinzufügen“")

Hier werden die Standardkonfigurationen gezeigt:

```json
{
  "configurations": [
    {
      "inheritEnvironments": [
        "msvc_x86"
      ],
      "name": "x86-Debug",
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
      "intelliSenseMode": "windows-msvc-x86"
    },
    {
      "inheritEnvironments": [
        "msvc_x86"
      ],
      "name": "x86-Release",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "defines": [
        "WIN32",
        "NDEBUG",
        "UNICODE",
        "_UNICODE"
      ],
      "intelliSenseMode": "windows-msvc-x86"
    },
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
    },
    {
      "inheritEnvironments": [
        "msvc_x64"
      ],
      "name": "x64-Release",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "defines": [
        "WIN32",
        "NDEBUG",
        "UNICODE",
        "_UNICODE"
      ],
      "intelliSenseMode": "windows-msvc-x64"
    }
  ]
}
```
Bei Eigenschaften, die mehrere zulässige Werte aufweisen, zeigt der Code-Editor die verfügbaren Optionen an, wenn Sie mit dem Tippen beginnen:

![„Ordner öffnen“ IntelliSense](media/open-folder-intellisense-mode.png "„Ordner öffnen“ IntelliSense")



## <a name="configuration-properties"></a>Konfigurationseigenschaften

Eine Konfiguration kann folgende Eigenschaften aufweisen:

|||
|-|-|
|`name`|Den Konfigurationsnamen, der in der Dropdownliste für die C++-Konfiguration angezeigt wird|
|`includePath`|Die Ordnerliste, die im Includepfad angegeben sein sollte (entspricht bei den meisten Compilern /I)|
|`defines`|Die Liste der Makros, die definiert sein sollten (entspricht bei den meisten Compilern /D)|
|`compilerSwitches`|Eine oder mehrere zusätzliche Optionen, die das Verhalten von IntelliSense beeinflussen können|
|`forcedInclude`|Ein Header, der automatisch in jede Kompilierungseinheit eingefügt wird (entspricht /FI bei MSVC oder -include bei Clang)|
|`undefines`|Die Liste der Makros, die nicht definiert sind (entspricht /U bei MSVC)|
|`intelliSenseMode`|Die zu verwendende IntelliSense-Engine Sie können architekturspezifische Varianten für MSVC, gcc oder Clang angeben:<br/><br/>– windows-msvc-x86 (Standard)<br/>– windows-msvc-x64<br/>– msvc-arm<br/>– windows-clang-x86<br/>– windows-clang-x64<br/>– windows-clang-arm<br/>– Linux-x64<br/>– Linux-x86<br/>– Linux-arm<br/>– gccarm|

Hinweis: Die Werte `msvc-x86` und `msvc-x64` werden nur aus Legacygründen unterstützt. Verwenden Sie die `windows-msvc*`-Varianten.

## <a name="custom-configurations"></a>Benutzerdefinierte Konfigurationen


Sie können jede Standardkonfiguration in `CppProperties.json` anpassen oder neue Konfigurationen erstellen. Jede davon wird in der Dropdownliste für Konfigurationen angezeigt:

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

## <a name="system-environment-variables"></a>Systemumgebungsvariablen 

 `CppProperties.json` unterstützt die Erweiterung von Systemumgebungsvariablen für Includepfade und andere Eigenschaftswerte. Die Syntax zum Erweitern einer Umgebungsvariable (`%FOODIR%`) lautet `${env.FOODIR}`. Folgende vom System definierte Variablen werden ebenfalls unterstützt:

|Variablenname|Beschreibung|
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

|Variablenname|Beschreibung|
|-----------|-----------------|
|linux_x86|Hiermit wird x86 Linux als Remotezielversion festgelegt.|
|linux_x64|Hiermit wird x64 Linux als Remotezielversion festgelegt.|
|linux_arm|Hiermit wird ARM Linux als Remotezielversion festgelegt.|

## <a name="custom-environment-variables"></a>Benutzerdefinierte Umgebungsvariablen

Sie können benutzerdefinierte Umgebungsvariablen in `CppProperties.json` entweder global oder pro Konfiguration definieren. Im folgenden Beispiel wird veranschaulicht, wie Standardumgebungsvariablen und benutzerdefinierte Umgebungsvariablen deklariert und verwendet werden können. Die globale Eigenschaft **environments** deklariert eine Variable namens **INCLUDE**, die von jeder Konfiguration verwendet werden kann:

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "INCLUDE": "${workspaceRoot}\src\includes"
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
      "intelliSenseMode": "windows-msvc-x86"
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
      "intelliSenseMode": "windows-msvc-x64"
    }
  ]
}
```
## <a name="per-configuration-environment-variables"></a>Konfigurationsspezifische Umgebungsvariablen

Sie können eine **environments**-Eigenschaft ebenfalls innerhalb einer Konfiguration definieren, sodass sie nur für diese Konfiguration gilt und alle globalen Variablen mit gleichem Namen überschreibt. Im folgenden Beispiel definiert die x64-Konfiguration eine lokale **INCLUDE**-Variable, die den globalen Wert überschreibt:

```json
{
  "environments": [
    {
      "INCLUDE": "${workspaceRoot}\src\includes"
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
      "intelliSenseMode": "windows-msvc-x86"
    },
    {
      "environments": [
        {
          // Append 64-bit specific include path to env.INCLUDE.
          "INCLUDE": "${env.INCLUDE};${workspaceRoot}\src\includes64"
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
      "intelliSenseMode": "windows-msvc-x64"
    }
  ]
}
```

Alle Standardumgebungsvariablen und benutzerdefinierten Umgebungsvariablen sind ebenfalls in `tasks.vs.json` und `launch.vs.json` verfügbar.

#### <a name="build-in-macros"></a>Integrierte Makros

Sie können innerhalb von `CppProperties.json` auf folgende integrierte Makros zugreifen:

|||
|-|-|
|`${workspaceRoot}`| den vollständigen Pfad zum Arbeitsbereichordner|
|`${projectRoot}`| den vollständigen Pfad zum Ordner von `CppProperties.json`|
|`${vsInstallDir}`| den vollständigen Pfad zum Ordner, indem die ausgeführte Instanz von Visual Studio installiert ist|

Wenn in Ihrem Projekt beispielsweise ein Includeordner sowie „windows.h“ und andere allgemeine Header des Windows SDK vorhanden sind, sollten Sie die Konfigurationsdatei `CppProperties.json` mit folgenden Includeelementen aktualisieren:

```json
{
  "configurations": [
    {
      "name": "Windows",
      "includePath": [
        // local include folder
        "${workspaceRoot}\include",
        // Windows SDK and CRT headers
        "${env.WindowsSdkDir}\include\${env.WindowsSDKVersion}\ucrt",
        "${env.NETFXSDKDir}\include\um",
        "${env.WindowsSdkDir}\include\${env.WindowsSDKVersion}\um",
        "${env.WindowsSdkDir}\include\${env.WindowsSDKVersion}\shared",
        "${env.VCToolsInstallDir}\include"
      ]
    }
  ]
}
```

> [!Note]
> `%WindowsSdkDir%`und `%VCToolsInstallDir%` werden nicht als globale Umgebungsvariablen festgelegt, um sicherzustellen, dass „devenv.exe“ über eine Developer-Eingabeaufforderung ausgeführt wird, die diese Variablen definiert. (Geben Sie "developer" im Windows-Startmenü ein.)

## <a name="troubleshoot-intellisense-errors"></a>Problembehandlung für IntelliSense-Fehler

Wenn Sie IntelliSense-Fehler beheben möchten, die von fehlenden Includepfaden verursacht wurden, öffnen Sie die **Fehlerliste**, und filtern Sie deren Ausgabe nach „Nur IntelliSense“ und dem Fehlercode E1696 „Die Datei ‚Dateiname‘ kann nicht geöffnet werden“.



