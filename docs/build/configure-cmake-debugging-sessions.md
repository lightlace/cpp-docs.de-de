---
title: Konfigurieren von CMake-Debugsitzungen in Visual Studio
ms.date: 03/21/2019
helpviewer_keywords:
- CMake debugging
ms.openlocfilehash: 9899f99994935ec419fff400670644b7d78a190a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62195519"
---
# <a name="configure-cmake-debugging-sessions"></a>Konfigurieren von CMake-Debugsitzungen

Alle ausführbaren CMake-Ziele werden in der Dropdownliste **Startelement** auf der Symbolleiste **Allgemein** angezeigt. Wählen Sie eines aus, und starten Sie den Debugger, um eine Debugsitzung zu starten.

![CMake-Dropdownliste „Startelement“](media/cmake-startup-item-dropdown.png "CMake startup item dropdown")

Sie können eine Debugsitzung ebenfalls über die CMake-Menüs starten.

## <a name="customize-debugger-settings"></a>Anpassen von Debuggereinstellungen

Wenn Sie die Debugeinstellungen für ein beliebiges ausführbares CMake-Ziel in Ihrem Projekt anpassen möchten, klicken Sie mit der rechten Maustaste auf die entsprechende CMakeLists.txt-Datei, und wählen Sie **Debug- und Starteinstellungen** aus. (Oder wählen Sie ein Ziel im **Zielansicht** in **Projektmappen-Explorer**.) Wenn Sie ein CMake-Ziel im Untermenü auswählen, wird eine Datei namens **"Launch.VS.JSON"** erstellt wird. Die Datei wird vorab mit Informationen zum ausgewählten CMake-Ziel aufgefüllt, und Sie können zusätzliche Parameter wie Programmargumente oder den Debuggertyp angeben. Auf eine beliebige Taste in einem **"cmakesettings.JSON"** Datei, leiten Sie ihn mit `cmake.` in **"Launch.VS.JSON"**. Das folgende Beispiel zeigt eine einfache **"Launch.VS.JSON"** Datei, die im Wert des bezieht die `remoteCopySources` -Schlüssel in der **"cmakesettings.JSON"** -Datei für die aktuell ausgewählte Konfiguration:

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

Sobald Sie speichern die **"Launch.VS.JSON"** -Datei, in dem ein Eintrag erstellt wird die **Startelement** Dropdownliste mit den neuen Namen. Durch Bearbeiten der **"Launch.VS.JSON"** -Datei können Sie so viele Debugkonfigurationen zu, wie Sie eine beliebige Anzahl von CMake-Ziele erstellen.

## <a name="support-for-cmakesettings-variables"></a>Unterstützung für CMakeSettings-Variablen

 **"Launch.VS.JSON"** unterstützt Variablen die im deklarierten **"cmakesettings.JSON"** (siehe unten) und gilt für die aktuell ausgewählte Konfiguration sind. Es verfügt auch über einen Schlüssel namens `currentDir`, wodurch das aktuelle Verzeichnis der Start-app für ein lokales Projekt festgelegt:

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

Der Schlüssel "Cwd" legt das aktuelle Verzeichnis der Start-app für ein remote-Projekt fest. Der Standardwert ist "${debugInfo.defaultWorkingDirectory}" der ausgewertet wird 

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
