---
title: Herstellen einer Verbindung mit Ihrem Linux-Remotecomputer in Visual Studio | Microsoft-Dokumentation
description: Informationen zum Herstellen einer Verbindung mit einem Linux-Remotecomputer über ein C++-Projekt in Visual Studio
ms.custom: ''
ms.date: 07/20/2018
ms.technology:
- cpp-linux
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: 5eeaa683-4e63-4c46-99ef-2d5f294040d4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: bba17549abc9f747d93299cf22c39ae7c3e8f4d6
ms.sourcegitcommit: 87d317ac62620c606464d860aaa9e375a91f4c99
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45601443"
---
# <a name="connect-to-your-remote-linux-computer"></a>Herstellen einer Verbindung mit Ihrem Linux-Remotecomputer

Beim Erstellen eines C++-Linux-Projekts in Visual Studio wird Linux-Code auf Ihren Linux-Remotecomputer kopiert und entsprechend den in Visual Studio ausgewählten Einstellungen kompiliert. So richten Sie die Remoteverbindung ein:

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