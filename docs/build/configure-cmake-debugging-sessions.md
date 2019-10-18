---
title: Konfigurieren von CMake-Debugsitzungen in Visual Studio
ms.date: 03/21/2019
helpviewer_keywords:
- CMake debugging
ms.openlocfilehash: 41f53c0c3ea46a8a1aa11215968aaee6c13c2dea
ms.sourcegitcommit: e33126222c418daf977533ea9e2819d99e0d7b8d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72534108"
---
# <a name="configure-cmake-debugging-sessions"></a>Konfigurieren von CMake-Debugsitzungen

Alle ausführbaren CMake-Ziele werden in der Dropdownliste **Startelement** auf der Symbolleiste **Allgemein** angezeigt. Wählen Sie eines aus, und starten Sie den Debugger, um eine Debugsitzung zu starten.

![Dropdown für cmake-Start Element](media/cmake-startup-item-dropdown.png "Dropdown für cmake-Start Element")

Sie können auch eine Debugsitzung aus Projektmappen-Explorer starten. Wechseln Sie zunächst in das Fenster **Projektmappen-Explorer** in die **Ansicht cmake-Ziele** .

![Cmake-Ziel Ansicht](media/cmake-targets-view.png  "Cmake-Ziel Ansicht (Menü Element)")

Klicken Sie dann mit der rechten Maustaste auf eine beliebige ausführbare Datei, und wählen Sie **Debuggen** , **Debug und Start** **Debuggen** beginnt automatisch mit dem Debuggen des ausgewählten Ziels, basierend auf Ihrer aktiven Konfiguration. Die **Einstellungen zum Debuggen und starten** öffnen die Datei " *Launch. vs. JSON* " und fügen eine neue Debugkonfiguration für das ausgewählte Ziel hinzu.

## <a name="customize-debugger-settings"></a>Anpassen von Debuggereinstellungen

Wenn Sie die Debugeinstellungen für ein beliebiges ausführbares CMake-Ziel in Ihrem Projekt anpassen möchten, klicken Sie mit der rechten Maustaste auf die entsprechende CMakeLists.txt-Datei, und wählen Sie **Debug- und Starteinstellungen** aus. (Oder wählen Sie in **Projektmappen-Explorer**ein Ziel in der **Ansicht Ziele** aus.) Wenn Sie ein cmake-Ziel im Untermenü auswählen, wird eine Datei mit dem Namen " **Launch. vs. JSON** " erstellt. Die Datei wird vorab mit Informationen zum ausgewählten CMake-Ziel aufgefüllt, und Sie können zusätzliche Parameter wie Programmargumente oder den Debuggertyp angeben. Um einen Verweis auf einen beliebigen Schlüssel in einer **cmakesettings. JSON** -Datei zu erhalten, weisen Sie ihm `cmake.` in " **Launch. vs. JSON**" zu. Das folgende Beispiel zeigt eine einfache Datei " **Launch. vs. JSON** ", die den Wert des `remoteCopySources` Schlüssels in der Datei " **cmakesettings. JSON** " für die aktuell ausgewählte Konfiguration abruft:

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

Sobald Sie die Datei " **Launch. vs. JSON** " speichern, wird ein Eintrag in der Dropdown Liste **Start Element** mit dem neuen Namen erstellt. Durch Bearbeiten der Datei " **Launch. vs. JSON** " können Sie beliebig viele Debugkonfigurationen für beliebig viele cmake-Ziele erstellen.

## <a name="support-for-cmakesettings-variables"></a>Unterstützung für CMakeSettings-Variablen

 " **Launch. vs. JSON** " unterstützt Variablen, die in " **cmakesettings. JSON** " deklariert sind (siehe unten) und die auf die derzeit ausgewählte Konfiguration anwendbar sind. Es verfügt außerdem über einen Schlüssel mit dem Namen `currentDir`, mit dem das aktuelle Verzeichnis der Start-App für ein lokales Projekt festgelegt wird:

```json
{
  "type": "default",
  "project": "CMakeLists.txt",
  "projectTarget": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
  "name": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
  "currentDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}"
}
```

Wenn Sie die App ausführen, entspricht der Wert von `currentDir` etwa Folgendem:

```cmd
C:\Users\satyan\7f14809a-2626-873e-952e-cdf038211175\
```

Mit dem Schlüssel "CWD" wird das aktuelle Verzeichnis der Start-App für ein Remote Projekt festgelegt. Der Standardwert ist "$ {Debuginfo. defaultworkingdirectory}", der ergibt. 

```cmd
/var/tmp/src/bfc6f7f4-4f0f-8b35-80d7-9198fa973fb9/Linux-Debug
```

## <a name="see-also"></a>Siehe auch

[CMake Projects in Visual Studio (CMake-Projekte in Visual Studio)](cmake-projects-in-visual-studio.md)<br/>
[Konfigurieren eines Linux CMake-Projekts](../linux/cmake-linux-project.md)<br/>
[Herstellen einer Verbindung mit Ihrem Linux-Remotecomputer](../linux/connect-to-your-remote-linux-computer.md)<br/>
[Anpassen von CMake-Buildeinstellungen](customize-cmake-settings.md)<br/>
[Konfigurieren von CMake-Debugsitzungen](configure-cmake-debugging-sessions.md)<br/>
[Bereitstellen, Ausführen und Debuggen Ihres Linux-Projekts](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake predefined configuration reference (Referenz für vordefinierte CMake-Konfigurationen)](cmake-predefined-configuration-reference.md)<br/>
