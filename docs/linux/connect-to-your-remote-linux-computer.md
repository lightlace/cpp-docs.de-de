---
title: Herstellen einer Verbindung mit dem Linux-Zielsystem in Visual Studio
description: Hier finden Sie Informationen zum Herstellen einer Verbindung mit einem Linux-Remotecomputer oder mit WSL über ein C++-Projekt in Visual Studio.
ms.date: 06/19/2019
ms.assetid: 5eeaa683-4e63-4c46-99ef-2d5f294040d4
ms.openlocfilehash: 7fa09c49df3da39084edb6735a7a2ccc724c34d3
ms.sourcegitcommit: 3ae8025df7fd50f5f56a0a2b5396533218bcc7dc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2019
ms.locfileid: "67285261"
---
# <a name="connect-to-your-target-linux-system-in-visual-studio"></a>Herstellen einer Verbindung mit dem Linux-Zielsystem in Visual Studio

::: moniker range="vs-2015"

Die Unterstützung für Linux ist in Visual Studio 2017 und höher verfügbar.

::: moniker-end

::: moniker range=">=vs-2017"

Sie können ein Linux-Projekt so konfigurieren, dass dieses auf einen Remotecomputer oder das Windows-Subsystem für Linux (WSL) abzielt. Für Remotecomputer und WSL in Visual Studio 2017 müssen Sie eine Verbindung einrichten. 

## <a name="connect-to-a-remote-linux-computer"></a>Herstellen einer Verbindung mit einem Linux-Remotecomputer

Beim Erstellen eines C++-Linux-Projekts für ein Linux-Remotesystem (virtueller oder physischer Computer) wird Linux-Code auf Ihren Linux-Remotecomputer kopiert und entsprechend der in Visual Studio ausgewählten Einstellungen kompiliert.

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

In Visual Studio 2019, Version 16.1, ist es nicht erforderlich, eine Remoteverbindung hinzuzufügen oder SSH zu konfigurieren, wenn Sie WSL als Ziel verwenden. Auf dem Linux-System benötigen Sie nur „gcc“, „gdb“, „make“, „rsync“ und „zip“. Visual Studio benötigt „rsync“ und „zip“ nur, um bei der ersten Verwendung Headerdateien von Ihrer WSL-Instanz zu dem Windows-Dateisystem zu extrahieren, das für IntelliSense verwendet werden soll. In Visual Studio 2019, Version 16.1, basiert die WSL-Unterstützung auf Windows Version 1809. Sie können eine höhere Version von Windows ausführen, aber Visual Studio nutzt die neuen WSL-Funktionen noch nicht.

Wenn Ihre Distribution „apt“ unterstützt, können Sie die erforderlichen Pakete mit folgendem Befehl installieren:

```bash
sudo apt install g++ gdb make rsync zip
```

Informationen zum Konfigurieren Ihres Projekts für WSL finden Sie unter [Konfigurieren eines Linux-Projekts](configure-a-linux-project.md) oder [Konfigurieren eines Linux CMake-Projekts](cmake-linux-project.md), je nachdem, mit welcher Art von Projekt Sie arbeiten.

::: moniker-end

## <a name="see-also"></a>Siehe auch

[Konfigurieren eines Linux-Projekts](configure-a-linux-project.md)<br />
[Konfigurieren eines Linux CMake-Projekts](cmake-linux-project.md)<br />
[Bereitstellen, Ausführen und Debuggen Ihres Linux-Projekts](deploy-run-and-debug-your-linux-project.md)<br />




