---
title: Konfigurieren von CMake-Debugsitzungen in Visual Studio
ms.date: 03/05/2019
helpviewer_keywords:
- CMake debugging
ms.openlocfilehash: 9a4dd009544a4590c336697ba2162eec45718869
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826078"
---
# <a name="configure-cmake-debugging-sessions"></a>Konfigurieren von CMake-Debugsitzungen

Alle ausführbaren CMake-Ziele werden in der Dropdownliste **Startelement** auf der Symbolleiste **Allgemein** angezeigt. Wählen Sie eines aus, und starten Sie den Debugger, um eine Debugsitzung zu starten.

![CMake-Dropdownliste „Startelement“](media/cmake-startup-item-dropdown.png "CMake startup item dropdown")

Sie können eine Debugsitzung ebenfalls über die CMake-Menüs starten.

## <a name="customize-debugger-settings"></a>Anpassen von Debuggereinstellungen

Wenn Sie die Debugeinstellungen für ein beliebiges ausführbares CMake-Ziel in Ihrem Projekt anpassen möchten, klicken Sie mit der rechten Maustaste auf die entsprechende CMakeLists.txt-Datei, und wählen Sie **Debug- und Starteinstellungen** aus. Wenn Sie im Untermenü ein CMake-Ziel auswählen, wird eine Datei namens `launch.vs.json` erstellt. Die Datei wird vorab mit Informationen zum ausgewählten CMake-Ziel aufgefüllt, und Sie können zusätzliche Parameter wie Programmargumente oder den Debuggertyp angeben. Wenn Sie in einer `CMakeSettings.json`-Datei auf einen Schlüssel verweisen möchten, stellen Sie diesem `cmake.` in `launch.vs.json` voran. In folgendem Beispiel wird eine einfache `launch.vs.json`-Datei dargestellt, die den Wert des Schlüssels `remoteCopySources` aus der Datei `CMakeSettings.json` für die derzeit ausgewählte Konfiguration abruft:

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

Sobald Sie die Datei `launch.vs.json` speichern, wird ein Eintrag mit dem neuen Namen in der Dropdownliste **Startelement** erstellt. Indem Sie die Datei `launch.vs.json` bearbeiten, können Sie beliebig viele Debugkonfigurationen für beliebig viele CMake-Ziele erstellen.

## <a name="support-for-cmakesettings-variables"></a>Unterstützung für CMakeSettings-Variablen

 `Launch.vs.json` unterstützt Variablen, die in `CMakeSettings.json` (siehe unten) deklariert werden und auf die aktuell ausgewählte Konfiguration angewendet werden können. Sie verfügt ebenfalls über einen Schlüssel namens `currentDir`, der das aktuelle Verzeichnis der gestarteten App festlegt:

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
## <a name="see-also"></a>Siehe auch

[CMake-Projekte in Visual Studio](cmake-projects-in-visual-studio.md)<br/>
[Konfigurieren eines Linux CMake-Projekts](../linux/cmake-linux-project.md)<br/>
[Herstellen einer Verbindung mit Ihrem Linux-Remotecomputer](../linux/connect-to-your-remote-linux-computer.md)<br/>
[Anpassen von CMake-Buildeinstellungen](customize-cmake-settings.md)<br/>
[Konfigurieren von CMake-Debugsitzungen](configure-cmake-debugging-sessions.md)<br/>
[Bereitstellen, Ausführen und Debuggen Ihres Linux-Projekts](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake predefined configuration reference (Referenz für vordefinierte CMake-Konfigurationen)](cmake-predefined-configuration-reference.md)<br/>