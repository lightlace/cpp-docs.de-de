---
title: 'Windows Sockets: Datagrammsockets | Microsoft Docs'
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
ms.openlocfilehash: 30ad7cab43301ae2cb7ebcb1fb4dfa850090955d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="windows-sockets-datagram-sockets"></a>Windows Sockets: Datagrammsockets
Dieser Artikel beschreibt Datagrammsockets, einer der zwei Windows Socket-Typen. (Der andere Typ ist der [Streamsocket](../mfc/windows-sockets-stream-sockets.md).)  
  
 Datagrammsockets unterstützen einen bidirektionalen Datenfluss, der nicht unbedingt sequenziert oder dupliziert sein kann. Datagramme werden auch nicht absolut zuverlässig; Diese können nicht auf das eingehen. Datagramm-Daten möglicherweise außerhalb der Reihenfolge und möglicherweise doppelte eintreffen, aber datensatzbegrenzungen in den Daten werden beibehalten, solange die Datensätze des Empfängers interne Größenlimit kleiner sind. Sie sind verantwortlich für die Verwaltung von Sequenzierung und Zuverlässigkeit. (Zuverlässigkeit tendenziell gut auf Local Area Networks, LANS] werden jedoch weniger usw. Wide-Area networks [WAN], z. B. im Internet).  
  
 Datagramme werden "verbindungsloses", d. h. keine explizite Verbindung hergestellt wird; Sie eine Datagrammnachricht an einen angegebenen Socket senden und Empfangen von Nachrichten von einem angegebenen Socket.  
  
 Ein Beispiel für einen Datagrammsocket ist eine Anwendung, die Systemuhr im Netzwerk synchronisiert bleiben. Dadurch wird eine weitere Funktion des Datagrammsockets in mindestens einige Einstellungen veranschaulicht: Übertragen von Nachrichten an eine große Anzahl von Netzwerkadressen.  
  
 Datagrammsockets sind besser als Streamsockets für datensatzorientierte Daten. Weitere Informationen zu Datagrammsockets finden Sie unter der Windows Sockets-Spezifikation, die im Windows SDK verfügbar.  
  
## <a name="see-also"></a>Siehe auch  
 [Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)   
 [Windows-Sockets: Hintergrund](../mfc/windows-sockets-background.md)

