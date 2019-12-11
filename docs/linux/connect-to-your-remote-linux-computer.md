---
title: Herstellen einer Verbindung mit dem Linux-Zielsystem in Visual Studio
description: Informationen zum Herstellen einer Verbindung mit einem Linux-Remotecomputer oder einem Windows-Subsystem für Linux über ein Visual Studio C++-Projekt
ms.date: 11/09/2019
ms.assetid: 5eeaa683-4e63-4c46-99ef-2d5f294040d4
ms.openlocfilehash: 4069979100c3b71a32e90ad72fb334d21a226e64
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755277"
---
# <a name="connect-to-your-target-linux-system-in-visual-studio"></a>Herstellen einer Verbindung mit dem Linux-Zielsystem in Visual Studio

::: moniker range="vs-2015"

Die Unterstützung für Linux ist in Visual Studio 2017 und höher verfügbar.

::: moniker-end

::: moniker range=">=vs-2017"

Sie können ein Linux-Projekt für einen Remotecomputer oder ein Windows-Subsystem für Linux (WSL) konfigurieren. Für Remotecomputer und WSL in Visual Studio 2017 müssen Sie eine Remoteverbindung einrichten.

## <a name="connect-to-a-remote-linux-computer"></a>Herstellen einer Verbindung mit einem Linux-Remotecomputer

Beim Erstellen eines C++-Linux-Projekts für ein Linux-Remotesystem (virtueller oder physischer Computer) wird Linux-Quellcode auf Ihren Linux-Remotecomputer kopiert. Anschließend wird er entsprechend der in Visual Studio ausgewählten Einstellungen kompiliert.

So richten Sie die Remoteverbindung ein:

1. Erstellen Sie das Projekt zum ersten Mal. Sie können stattdessen aber auch manuell einen neuen Eintrag erstellen. Klicken Sie auf **Extras > Optionen**, öffnen Sie den Knoten **Plattformübergreifend > Verbindungs-Manager**, und klicken Sie dann auf die Schaltfläche **Hinzufügen**.

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

   1. Erstellen Sie mit `ssh-keygen -t rsa` ein SSH-Schlüsselpaar auf dem Windows-Computer. Mit diesem Befehl wird ein öffentlicher und einer privater Schlüssel erstellt. Standardmäßig wird der Schlüssel unter `C:\Users\%USERNAME%\.ssh` platziert, wobei die Namen `id_rsa.pub` und `id_rsa` verwendet werden.

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

   Sie können die Ausgabe in eine Datei oder in den Bereich **Plattformübergreifende Protokollierung** im Ausgabefenster konfigurieren. Bei MSBuild-basierten Linux-Projekten werden MSBuild-Befehle, die an den Remotecomputer gesendet werden, nicht an das **Ausgabefenster** weitergeleitet, weil sie prozessextern gesendet werden. Stattdessen werden sie in eine Datei mit dem Präfix „msbuild_“ protokolliert.

## <a name="tcp-port-forwarding"></a>TCP-Portweiterleitung

Die Linux-Unterstützung von Visual Studio verfügt über eine Abhängigkeit von der TCP-Portweiterleitung. Wenn die TCP-Portweiterleitung in Ihrem Remotesystem deaktiviert wird, wirkt sich dies auf **rsync** und **gdbserver** aus. Wenn Sie von dieser Abhängigkeit betroffen sind, können Sie in der Entwicklercommunity für dieses [Vorschlagsticket](https://developercommunity.visualstudio.com/idea/840265/dont-rely-on-ssh-tcp-port-forwarding-for-c-remote.html) abstimmen.

Sowohl MSBuild-basierte Linux-Projekte als auch CMake-Projekte verwenden „rsync“, um [Header aus Ihrem Remotesystem zur Verwendung für IntelliSense in Windows zu kopieren](configure-a-linux-project.md#remote_intellisense). Wenn Sie die TCP-Portweiterleitung nicht aktivieren können, deaktivieren Sie den automatischen Download von Remoteheadern. Navigieren Sie zum Deaktivieren zu **Extras > Optionen > Plattformübergreifend > Verbindungs-Manager > IntelliSense-Manager für Remoteheader**. Wenn im Remotesystem die TCP-Portweiterleitung nicht aktiviert ist, wird der folgende Fehler angezeigt, wenn der Download von Remoteheadern für IntelliSense startet:

![Fehler bei Headern](media/port-forwarding-headers-error.png)

Die CMake-Unterstützung von Visual Studio verwendet „rsync“ ebenfalls, um Quelldateien in das Remotesystem zu kopieren. Wenn Sie die TCP-Portweiterleitung nicht aktivieren können, können Sie SFTP als Methode zum Kopieren von Remotequellen verwenden. SFTP ist häufig langsamer als „rsync“, weist aber keine Abhängigkeit von der TCP-Portweiterleitung auf. Sie können Ihre Methode zum Kopieren von Remotequellen mit der **remoteCopySourcesMethod**-Eigenschaft im [CMake-Einstellungs-Editor](../build/cmakesettings-reference.md#additional-settings-for-cmake-linux-projects) verwalten. Wenn die TCP-Portweiterleitung in Ihrem Remotesystem deaktiviert ist, wird beim ersten Aufrufen von „rsync“ ein Fehler im CMake-Ausgabefenster angezeigt.

![rsync-Fehler](media/port-forwarding-copy-error.png)

„gdbserver“ kann zum Debuggen auf eingebetteten Geräten verwendet werden. Wenn Sie die TCP-Portweiterleitung nicht aktivieren können, müssen Sie „gdb“ für alle Remotedebuggingszenarios verwenden. Beim Debuggen von Projekten in einem Remotesystem wird standardmäßig „gdb“ verwendet.

::: moniker-end

## <a name="connect-to-wsl"></a>Herstellen einer Verbindung mit WSL

::: moniker range="vs-2017"

In Visual Studio 2017 verwenden Sie die gleichen Schritte, um eine Verbindung mit WSL herzustellen, wie Sie für einen Linux-Remotecomputer verwenden würden. Verwenden Sie **localhost** als **Hostnamen**.

::: moniker-end

::: moniker range="vs-2019"

In Version 16.1 von Visual Studio 2019 wurde native Unterstützung für die Verwendung von C++ mit dem [Windows-Subsystem für Linux (WSL)](/windows/wsl/about) hinzugefügt. Das bedeutet, dass Sie den Erstellungs- und den Debugvorgang direkt für Ihre lokale WSL-Installation durchführen können. Es ist nicht mehr erforderlich, eine Remoteverbindung hinzuzufügen oder SSH zu konfigurieren. Weitere Informationen zur [Installation von WSL](/windows/wsl/install-win10) finden Sie hier.

Sie müssen die Tools „gcc „oder „clang“, „gdb“, „make“, „rsync“ und „zip“ installieren, um die WSL-Installation so zu konfigurieren, dass sie mit Visual Studio verwendet werden kann. Sie können sie für Distributionen installieren, die apt verwenden, indem Sie diesen Befehl verwenden, der auch den g++-Compiler installiert:

```bash
sudo apt install g++ gdb make rsync zip
```

Weitere Informationen finden Sie unter [Herunterladen, Installieren und Einrichten der Linux-Workload](download-install-and-setup-the-linux-development-workload.md).

Informationen zum Konfigurieren eines MSBuild-Projekts für WSL finden Sie unter [Konfigurieren eines Linux-Projekts](configure-a-linux-project.md). Informationen zum Konfigurieren eines CMake-Projekts für WSL finden Sie unter [Konfigurieren eines Linux CMake-Projekts](cmake-linux-project.md). Eine ausführliche Anleitung für das Erstellen einer einfachen Konsolenanwendung mit WSL finden Sie in diesem Blogbeitrag zur Einführung in [C++ mit Visual Studio 2019 und dem Windows-Subsystem für Linux (WSL)](https://devblogs.microsoft.com/cppblog/c-with-visual-studio-2019-and-windows-subsystem-for-linux-wsl/).

::: moniker-end

## <a name="see-also"></a>Siehe auch

[Konfigurieren eines Linux-Projekts](configure-a-linux-project.md)\
[Konfigurieren eines Linux CMake-Projekts](cmake-linux-project.md)\
[Bereitstellen, Ausführen und Debuggen Ihres Linux-Projekts](deploy-run-and-debug-your-linux-project.md)\
[Konfigurieren von CMake-Debugsitzungen](../build/configure-cmake-debugging-sessions.md)
