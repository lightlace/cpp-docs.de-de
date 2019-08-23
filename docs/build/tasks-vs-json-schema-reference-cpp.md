---
title: Schema Referenz zu "Tasks. vs. JSON" (C++)
ms.date: 08/20/2019
helpviewer_keywords:
- tasks.vs.json file [C++]
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
ms.openlocfilehash: 1e533babafad554e8f7413d2bc1a88933a6eca42
ms.sourcegitcommit: ace42fa67e704d56d03c03745b0b17d2a5afeba4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69975916"
---
# <a name="tasksvsjson-schema-reference-c"></a>Schema Referenz zu "Tasks. vs. JSON" (C++)

Fügen Sie die Datei " *Tasks. vs. JSON* " hinzu, um Visual Studio mitzuteilen, wie der Quellcode in einem geöffneten Ordner Projekt erstellt werden soll. Sie können hier beliebig eine beliebige Aufgabe definieren und Sie dann über das Kontextmenü **Projektmappen-Explorer** aufrufen. Cmake-Projekte verwenden diese Datei nicht, da alle Buildbefehle in " *CMakeLists. txt*" angegeben sind. Für andere Buildsysteme als cmake können Sie mit " *Tasks. vs. JSON* " Buildbefehle angeben und Buildskripts aufrufen. Allgemeine Informationen zur Verwendung von " *Tasks. vs. JSON*" finden Sie unter [Anpassen von Build-und Debugaufgaben für die Entwicklung "Ordner öffnen"](/visualstudio/ide/customize-build-and-debug-tasks-in-visual-studio).

Eine Aufgabe verfügt über `type` eine Eigenschaft, die einen von vier Werten aufweisen `default`kann `launch`: `remote`,, `msbuild`oder. Die meisten Tasks sollten `launch` verwenden, es sei denn, eine Remote Verbindung ist erforderlich.

## <a name="default-properties"></a>Standardeigenschaften

Die Standardeigenschaften sind für alle Arten von Tasks verfügbar:

||||
|-|-|-|
|**Eigenschaft**|**Typ**|**Beschreibung**|
|`taskLabel`|string| (Erforderlich.) Gibt die in der Benutzeroberfläche verwendete Aufgaben Bezeichnung an.|
|`appliesTo`|string| (Erforderlich.) Gibt an, für welche Dateien der Befehl ausgeführt werden kann. Die Verwendung von Platzhaltern wird unterstützt, z. b.: " *", "* . cpp", "/*. txt".|
|`contextType`|string| Zulässige Werte: "Custom", "Build", "Clean", "Rebuild". Bestimmt, wo im Kontextmenü die Aufgabe angezeigt wird. Der Standardwert ist "Custom".|
|`output`|string| Gibt ein Ausgabetag für Ihre Aufgabe an.|
|`inheritEnvironments`|array| Gibt einen Satz von Umgebungsvariablen an, die von mehreren Quellen geerbt werden. Sie können Variablen in Dateien wie " *cmakesettings. JSON* " oder " *cppproperties. JSON* " definieren und für den Aufgaben Kontext verfügbar machen.|
|`passEnvVars`|boolean| Gibt an, ob zusätzliche Umgebungsvariablen in den Task Kontext eingeschlossen werden sollen. Diese Variablen unterscheiden sich von denen, die mithilfe `envVars` der-Eigenschaft definiert wurden. Der Standardwert ist "true".|

## <a name="launch-properties"></a>Starteigenschaften

Wenn der Aufgabentyp `launch`lautet, sind folgende Eigenschaften verfügbar:

||||
|-|-|-|
|**Eigenschaft**|**Typ**|**Beschreibung**|
|`command`|string| Gibt den vollständigen Pfad des zu startenden Prozesses oder Skripts an.|
|`args`|array| Gibt eine durch Trennzeichen getrennte Liste von Argumenten an, die an den Befehl übermittelt werden.|
|`launchOption`|string| Zulässige Werte: "None", "ContinueOnError", "IgnoreError". Gibt an, wie der Befehl beim Auftreten von Fehlern fortgesetzt wird.|
|`workingDirectory`|string| Gibt das Verzeichnis an, in dem der Befehl ausgeführt wird. Der Standardwert ist das aktuelle Arbeitsverzeichnis des Projekts.|
|`customLaunchCommand`|string| Gibt eine globale Bereichs Anpassung an, die angewendet werden soll, bevor der Befehl ausgeführt wird. Nützlich für das Festlegen von Umgebungsvariablen wie% Path%.|
|`customLaunchCommandArgs`|string| Gibt Argumente für "customlaunchcommand" an. (Erfordert `customLaunchCommand`.)|
 `env`| Gibt eine Schlüssel-Wert-Liste von benutzerdefinierten Umgebungsvariablen an. Beispiel: "mytv": "myVal"|
|`commands`|array| Gibt eine Liste der Befehle an, die in der Reihenfolge aufgerufen werden.|

### <a name="example"></a>Beispiel

Die folgenden Tasks rufen " *make. exe* " auf, wenn ein Makefile im Ordner bereit `Mingw64` gestellt wird und die Umgebung in " *cppproperties. JSON*" definiert wurde, wie in der [Schema Referenz "cppproperties. JSON](cppproperties-schema-reference.md#user_defined_environments)" gezeigt:

```json
 {
  "version": "0.2.1",
  "tasks": [
    {
      "taskLabel": "gcc make",
      "appliesTo": "*.cpp",
      "type": "launch",
      "contextType": "custom",
      "inheritEnvironments": [
        "Mingw64"
      ],
      "command": "make"
    },
    {
      "taskLabel": "gcc clean",
      "appliesTo": "*.cpp",
      "type": "launch",
      "contextType": "custom",
      "inheritEnvironments": [
        "Mingw64"
      ],
      "command": "make",
      "args": ["clean"]
    }
  ]
}
```

Diese Tasks können über das Kontextmenü aufgerufen werden, wenn Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf eine *cpp* -Datei klicken.

## <a name="remote-properties"></a>Remote Eigenschaften

Remote Aufgaben werden aktiviert, wenn Sie die Linux-Entwicklung C++ mit Arbeitsauslastung installieren und mithilfe des Visual Studio-Verbindungs-Managers eine Verbindung zu einem Remote Computer hinzufügen. Eine Remote Aufgabe führt Befehle auf einem Remote System aus und kann auch Dateien in Sie kopieren.

Wenn der Aufgabentyp `remote`lautet, sind folgende Eigenschaften verfügbar:

||||
|-|-|-|
|**Eigenschaft**|**Typ**|**Beschreibung**|
|`remoteMachineName`|string|Der Name des Remote Computers. Muss mit einem Computernamen im **Verbindungs-Manager**verglichen werden.|
|`command`|string|Der Befehl, der an den Remote Computer gesendet werden soll. Standardmäßig werden Befehle im $Home Verzeichnis auf dem Remote System ausgeführt.|
|`remoteWorkingDirectory`|string|Das aktuelle Arbeitsverzeichnis auf dem Remote Computer.|
|`localCopyDirectory`|string|Das lokale Verzeichnis, das auf den Remote Computer kopiert werden soll. Der Standardwert ist das aktuelle Arbeitsverzeichnis.|
|`remoteCopyDirectory`|string|Das Verzeichnis auf dem Remote Computer, `localCopyDirectory` in das kopiert wird.|
|`remoteCopyMethod`|string| Die Methode, die für den Kopiervorgang verwendet werden soll. Zulässige Werte: "None", "SFTP", "rsync". "rsync" wird für große Projekte empfohlen.|
|`remoteCopySourcesOutputVerbosity`|string| Zulässige Werte: "Normal", "ausführlich", "Diagnose".|
|`rsyncCommandArgs`|string|Der Standardwert ist "-t--delete".|
|`remoteCopyExclusionList`|array|Durch Trennzeichen getrennte Liste von Dateien `localCopyDirectory` in, die von Kopier Vorgängen ausgeschlossen werden sollen.|

### <a name="example"></a>Beispiel

Die folgende Aufgabe wird im Kontextmenü angezeigt, wenn Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf " *Main. cpp* " klicken. Dies hängt von einem Remote Computer mit `ubuntu` dem Namen im **Verbindungs-Manager**ab. Der Task kopiert den aktuell geöffneten Ordner in Visual Studio in das `sample` Verzeichnis auf dem Remote Computer und ruft dann g + + auf, um das Programm zu erstellen.

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskLabel": "Build",
      "appliesTo": "main.cpp",
      "type": "remote",
      "contextType": "build",
      "command": "g++ main.cpp",
      "remoteMachineName": "ubuntu",
      "remoteCopyDirectory": "~/sample",
      "remoteCopyMethod": "sftp",
      "remoteWorkingDirectory": "~/sample/hello",
      "remoteCopySourcesOutputVerbosity": "Verbose"
    }
  ]
}
```

## <a name="msbuild-properties"></a>MSBuild-Eigenschaften

Wenn der Aufgabentyp `msbuild`lautet, sind folgende Eigenschaften verfügbar:

||||
|-|-|-|
|**Eigenschaft**|**Typ**|**Beschreibung**|
|`verbosity`|string| Gibt die Werte für die Buildausgabe des MSBuild-Projekts an: "Quiet", "Minimum", "Normal", "detailliert", "Diagnose".|
|`toolsVersion`|string| Gibt die Toolsetversion zum Erstellen des Projekts an, z. b. "2,0", "3,5", "4,0", "Current". Der Standardwert ist "Current".|
|`globalProperties`|Objekt|Gibt eine Schlüssel-Wert-Liste der globalen Eigenschaften an, die an das Projekt übergeben werden sollen, z. b. "Configuration": "Release"|
|`properties`|Objekt| Gibt eine Schlüssel-Wert-Liste mit zusätzlichen Projekteigenschaften an.|
|`targets`|array| Gibt die Liste der Ziele an, die für das Projekt in der richtigen Reihenfolge aufgerufen werden. Wenn keine Angabe erfolgt, wird das Standardziel des Projekts verwendet.|
