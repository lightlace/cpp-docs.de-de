---
title: Herstellen einer Verbindung mit dem Linux-Zielsystem in Visual Studio
description: Hier finden Sie Informationen zum Herstellen einer Verbindung mit einem Linux-Remotecomputer oder mit WSL über ein C++-Projekt in Visual Studio.
ms.date: 09/04/2019
ms.assetid: 5eeaa683-4e63-4c46-99ef-2d5f294040d4
ms.openlocfilehash: 75d8b3db64d9b1f3562d6730685b7c29fe4982f4
ms.sourcegitcommit: a42d3b0408f02138dcd6fabcb98d50b0cb159191
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2019
ms.locfileid: "70383404"
---
# <a name="connect-to-your-target-linux-system-in-visual-studio"></a>Herstellen einer Verbindung mit dem Linux-Zielsystem in Visual Studio

::: moniker range="vs-2015"

Die Unterstützung für Linux ist in Visual Studio 2017 und höher verfügbar.

::: moniker-end

::: moniker range=">=vs-2017"

Sie können ein Linux-Projekt für einen Remotecomputer oder ein Windows-Subsystem für Linux (WSL) konfigurieren. Für Remotecomputer und WSL in Visual Studio 2017 müssen Sie eine Remoteverbindung einrichten. 

## <a name="connect-to-a-remote-linux-computer"></a>Herstellen einer Verbindung mit einem Linux-Remotecomputer

Beim Erstellen eines C++-Linux-Projekts für ein Linux-Remotesystem (virtueller oder physischer Computer) wird Linux-Quellcode auf Ihren Linux-Remotecomputer kopiert und entsprechend der in Visual Studio ausgewählten Einstellungen kompiliert.

So richten Sie die Remoteverbindung ein:

1. Erstellen Sie das Projekt zum ersten Mal, oder erstellen Sie manuell einen neuen Eintrag durch Auswählen von **Tools > Optionen**. Öffnen Sie anschließend den Knoten unter **Plattformübergreifend > Verbindungs-Manager**, und klicken Sie auf die Schaltfläche **Hinzufügen** .

   ![Verbindungs-Manager](media/settings_connectionmanager.png)

   In beiden Fällen wird das Fenster **Connect to Remote System** (Mit Remotesystem verbinden) angezeigt.

   ![Connect to Remote System (Mit Remotesystem verbinden)](media/connect.png)

1. Geben Sie die folgenden Informationen ein:

   | Eingabe | BESCHREIBUNG
   | ----- | ---
   | **Hostname**           | Name oder IP-Adresse des Zielgeräts
   | **Port**                | Port, auf dem der SSH-Dienst ausgeführt wird, in der Regel Port 22
   | **Benutzername**           | Zu authentifizierender Benutzer
   | **Authentifizierungstyp** | Sowohl das Kennwort als auch der private Schlüssel wird unterstützt.
   | **Kennwort**            | Kennwort für den eingegebenen Benutzernamen
   | **Datei für den privaten Schlüssel**    | Für die SSH-Verbindung erstellte private Schlüsseldatei
   | **Passphrase**          | Passphrase mit dem zuvor ausgewählten privaten Schlüssel

   Sie können entweder ein Kennwort oder eine Schlüsseldatei und eine Passphrase zur Authentifizierung verwenden. In vielen Entwicklungsszenarien ist die Kennwortauthentifizierung ausreichend. Wenn Sie lieber eine öffentliche/private Schlüsseldatei verwenden möchten, können Sie eine neue Datei erstellen oder [eine vorhandene wiederverwenden](https://security.stackexchange.com/questions/10203/reusing-private-public-keys). Derzeit werden nur RSA- und DSA-Schlüssel unterstützt. 
   
   Mit den folgenden Schritten können Sie eine private RSA-Schlüsseldatei erstellen:

    1. Erstellen Sie mit `ssh-keygen -t rsa` ein SSH-Schlüsselpaar auf dem Windows-Computer. Damit wird ein öffentlicher und einer privater Schlüssel erstellt. Standardmäßig werden die Schlüssel mit den Namen `id_rsa.pub` und `id_rsa` unter `C:\Users\%USERNAME%\.ssh` platziert.

    1. Kopieren Sie den öffentlichen Schlüssel von Windows auf den Linux-Computer: `scp -p C:\Users\%USERNAME%\.ssh\id_rsa.pub user@hostname`.

    1. Fügen Sie den Schlüssel auf dem Linux-System zur Liste der autorisierten Schlüssel hinzu (und stellen Sie sicher, dass die Datei die richtigen Berechtigungen besitzt): `cat ~/id_rsa.pub >> ~/.ssh/authorized_keys; chmod 600 ~/.ssh/authorized_keys`

1. Klicken Sie auf die Schaltfläche **Verbinden**, um eine Verbindung mit dem Remotecomputer herzustellen. 

   Wenn die Verbindung erfolgreich hergestellt wird, beginnt Visual Studio damit, IntelliSense zur Verwendung der Remoteheader zu konfigurieren. Weitere Informationen finden Sie unter [IntelliSense für Header auf Remotesystemen](configure-a-linux-project.md#remote_intellisense).

   Wenn die Verbindung nicht erfolgreich hergestellt wird, werden die Eintragsfelder, die geändert werden müssen, rot umrandet.

   ![Fehler des Verbindungs-Manager](media/settings_connectionmanagererror.png)

   Wenn Sie Schlüsseldateien zur Authentifizierung verwenden, stellen Sie sicher, dass der SSH-Server des Zielcomputers ausgeführt wird und ordnungsgemäß konfiguriert ist.

   ::: moniker-end

   ::: moniker range="vs-2019"

   Navigieren Sie zu **Tools > Optionen > Plattformübergreifend > Protokollierung**, um zur Unterstützung der Fehlerbehebung bei Verbindungsproblemen die Protokollierung zu aktivieren:

   ![Remoteprotokollierung](media/remote-logging-vs2019.png)

   Protokolle enthalten Verbindungen, alle an den Remotecomputer gesendeten Befehle (Text, Exitcode und Ausführungszeit) sowie die gesamte Ausgabe von Visual Studio an die Shell. Die Protokollierung funktioniert für alle plattformübergreifenden CMake-Projekte oder MSBuild-basierten Linux-Projekte in Visual Studio.

   Sie können die Ausgabe in eine Datei oder in den Bereich **Plattformübergreifende Protokollierung** im Ausgabefenster konfigurieren. Bei MSBuild-basierten Linux-Projekten werden Befehle, die von MSBuild an den Remotecomputer ausgegeben werden, nicht an das **Ausgabefenster** weitergeleitet, weil sie prozessextern gesendet werden. Stattdessen werden sie in eine Datei mit dem Präfix „msbuild_“ protokolliert.

   ::: moniker-end

## <a name="connect-to-wsl"></a>Herstellen einer Verbindung mit WSL

::: moniker range="vs-2017"

In Visual Studio 2017 stellen Sie eine Verbindung mit WSL her, indem Sie die gleichen Schritte durchführen wie beim Herstellen einer Verbindung mit einem Linux-Remotecomputer, wie weiter oben in diesem Artikel beschrieben. Verwenden Sie **localhost** als **Hostnamen**.

::: moniker-end

::: moniker range="vs-2019"

In Version 16.1 von Visual Studio 2019 wurde native Unterstützung für die Verwendung von C++ mit dem [Windows-Subsystem für Linux (WSL)](https://docs.microsoft.com/windows/wsl/about) hinzugefügt.  Das bedeutet, dass Sie keine Remoteverbindung mehr herstellen oder SSH konfigurieren müssen, um auf Ihrer lokalen WSL-Installation Projekte zu erstellen und zu debuggen. Weitere Informationen zur [Installation von WSL](https://docs.microsoft.com/windows/wsl/install-win10) finden Sie hier.

Sie müssen die Tools gcc, gdb, make, rsync und zip installieren, um die WSL-Installation so zu konfigurieren, dass sie mit Visual Studio verwendet werden kann. Diese können Sie auf Distributionen installieren, die „apt“ mit folgendem Befehl verwenden: 

```bash
sudo apt install g++ gdb make rsync zip
```

Informationen zum Konfigurieren Ihres Projekts für WSL finden Sie unter [Konfigurieren eines Linux-Projekts](configure-a-linux-project.md) oder [Konfigurieren eines Linux CMake-Projekts](cmake-linux-project.md), je nachdem, mit welcher Art von Projekt Sie arbeiten. Eine ausführliche Anleitung für das Erstellen einer einfachen Konsolenanwendung mit WSL finden Sie in diesem Blogbeitrag zur Einführung in [C++ mit Visual Studio 2019 und dem Windows-Subsystem für Linux (WSL)](https://devblogs.microsoft.com/cppblog/c-with-visual-studio-2019-and-windows-subsystem-for-linux-wsl/).

::: moniker-end

## <a name="see-also"></a>Siehe auch

[Konfigurieren eines Linux-Projekts](configure-a-linux-project.md)<br />
[Konfigurieren eines Linux CMake-Projekts](cmake-linux-project.md)<br />
[Bereitstellen, Ausführen und Debuggen Ihres Linux-Projekts](deploy-run-and-debug-your-linux-project.md)<br />
[Konfigurieren von CMake-Debugsitzungen](../build/configure-cmake-debugging-sessions.md)
