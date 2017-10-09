---
title: Aufbauen einer Verbindung mit Ihrem Linux-Remotecomputer | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-linux
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5eeaa683-4e63-4c46-99ef-2d5f294040d4
author: BrianPeek
ms.author: brpeek
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: dd817a7d9fad4946cd0aa9f641f9e8f495f1be9a
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---

# <a name="connect-to-your-remote-linux-computer"></a>Aufbauen einer Verbindung mit Ihrem Linux-Remotecomputer

Beim Erstellen wird Linux-Code auf Ihren Linux-Remotecomputer kopiert und dann auf diesem System entsprechend den in Visual Studio ausgewählten Einstellungen kompiliert.  So richten Sie die Remoteverbindung ein:

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
   | **Datei für den privaten Schlüssel**    | Für die SSH-Verbindung erstellter privater Schlüssel
   | **Passphrase**          | Passphrase mit dem zuvor ausgewählten privaten Schlüssel

1. Klicken Sie auf die Schaltfläche **Verbinden**, um eine Verbindung mit dem Remotecomputer herzustellen.  Wenn die Verbindung fehlschlägt, werden die Textfelder, die geändert werden, rot umrandet.

   ![Fehler des Verbindungs-Manager](media/settings_connectionmanagererror.png)
