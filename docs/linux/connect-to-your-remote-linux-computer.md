---
title: Herstellen einer Verbindung mit Ihrem Linux-Remotecomputer in Visual Studio
description: Informationen zum Herstellen einer Verbindung mit einem Linux-Remotecomputer über ein C++-Projekt in Visual Studio
ms.date: 06/07/2019
ms.assetid: 5eeaa683-4e63-4c46-99ef-2d5f294040d4
ms.openlocfilehash: 6348681ecc8e6f7863b2119810db24879526a1c6
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821608"
---
# <a name="connect-to-your-remote-linux-computer"></a>Herstellen einer Verbindung mit Ihrem Linux-Remotecomputer

::: moniker range="vs-2015"

Die Unterstützung für Linux ist in Visual Studio 2017 und höher verfügbar.

::: moniker-end

::: moniker range="vs-2019"

Wenn auf das Windows-Subsystem für Linux (Windows Subsystem for Linux, WSL) abgezielt wird, interagiert Visual Studio mit Ihrer Linux-Distribution direkt über das Dateisystem. Hierfür ist keine Remoteverbindung erforderlich.

::: moniker-end

Beim Erstellen eines C++-Linux-Projekts für ein Linux-Remotesystem (virtueller oder physischer Computer) wird Linux-Code auf Ihren Linux-Remotecomputer kopiert und entsprechend der in Visual Studio ausgewählten Einstellungen kompiliert. So richten Sie die Remoteverbindung ein:

1. Erstellen Sie das Projekt zum ersten Mal, oder erstellen Sie manuell einen neuen Eintrag durch Auswählen von **Tools > Optionen**. Öffnen Sie anschließend den Knoten unter **Plattformübergreifend > Verbindungs-Manager**, und klicken Sie auf die Schaltfläche **Hinzufügen** .

   ![Verbindungs-Manager](media/settings_connectionmanager.png)

   In beiden Fällen wird das Fenster **Connect to Remote System** (Mit Remotesystem verbinden) angezeigt.

   ![Connect to Remote System (Mit Remotesystem verbinden)](media/connect.png)

1. Geben Sie die folgenden Informationen ein:

   | Eingabe | Beschreibung
   | ----- | ---
   | **Hostname**           | Name oder IP-Adresse des Zielgeräts
   | **Port**                | Port, auf dem der SSH-Dienst ausgeführt wird, in der Regel Port 22
   | **Benutzername**           | Zu authentifizierender Benutzer
   | **Authentifizierungstyp** | Sowohl das Kennwort als auch der private Schlüssel wird unterstützt.
   | **Kennwort**            | Kennwort für den eingegebenen Benutzernamen
   | **Datei für den privaten Schlüssel**    | Für die SSH-Verbindung erstellte private Schlüsseldatei
   | **Passphrase**          | Passphrase mit dem zuvor ausgewählten privaten Schlüssel

1. Klicken Sie auf die Schaltfläche **Verbinden**, um eine Verbindung mit dem Remotecomputer herzustellen.  Wenn die Verbindung fehlschlägt, werden die Textfelder, die geändert werden, rot umrandet.

   ![Fehler des Verbindungs-Manager](media/settings_connectionmanagererror.png)