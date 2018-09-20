---
title: 'Windows Sockets: Datagrammsockets | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sockets [MFC], datagram
- Windows Sockets [MFC], bi-directional data flow
- datagram sockets [MFC]
- Windows Sockets [MFC], datagram
- sockets [MFC], bi-directional data flow
ms.assetid: bec16a1c-74c0-4ff9-8c18-c2d87897d264
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a63caa786ce5198fb902b8d48101507fb2b4113
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444215"
---
# <a name="windows-sockets-datagram-sockets"></a>Windows Sockets: Datagrammsockets

Dieser Artikel beschreibt Datagrammsockets, eines der zwei Windows Socket-Typen. (Der andere Typ ist der [Streamsocket](../mfc/windows-sockets-stream-sockets.md).)

Datagrammsockets unterstützen einen bidirektionalen Datenfluss, der nicht sequenziert oder dupliziert werden. Datagramme werden auch nicht unbedingt zuverlässig sein; Sie können nicht eingehen. Datagrammdaten können eintreffen, außerhalb der Reihenfolge oder dupliziert allerdings datensatzbegrenzungen in den Daten werden beibehalten, solange der Datensätze kleiner als interne größenbeschränkung des Empfängers sind. Sie sind verantwortlich für die Verwaltung von sequenzieren und Zuverlässigkeit. (Zuverlässigkeit ist normalerweise in lokalen Netzwerken [LAN] gut, aber weniger usw. Wide-Area networks [WAN], z. B. das Internet.)

Datagramme werden "verbindungsloses", d. h. keine explizite Verbindung hergestellt wird; Sie eine Datagrammnachricht an einen angegebenen Socket senden und Empfangen von Nachrichten von einem angegebenen Socket.

Ein Beispiel für einen Datagrammsocket ist eine Anwendung, die Uhren des Informationssystems im Netzwerk synchronisiert bleibt. Dies ist eine weitere Funktion von Datagrammsockets in zumindest eine gewisse Einstellungen: Übertragen von Nachrichten an eine große Anzahl von Adressen im Netzwerk.

Datagrammsockets sind besser geeignet als Streamsockets für datensatzorientierte Daten. Weitere Informationen zu Datagrammsockets finden Sie unter der Windows Sockets-Spezifikation, die im Windows SDK verfügbar.

## <a name="see-also"></a>Siehe auch

[Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)<br/>
[Windows-Sockets: Hintergrund](../mfc/windows-sockets-background.md)

