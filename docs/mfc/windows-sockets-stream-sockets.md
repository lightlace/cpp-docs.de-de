---
title: 'Windows Sockets: Streamen von Sockets | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Windows Sockets [MFC], stream sockets
- sockets [MFC], stream sockets
- stream sockets [MFC]
ms.assetid: 31faaa34-a995-493f-a30b-b8115293d619
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bc112bd3cfbf1194a2898afecb513edcbc456747
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="windows-sockets-stream-sockets"></a>Windows Sockets: Blockieren
Dieser Artikel beschreibt Streamsockets, einer der zwei Windows Socket-Typen. (Der andere Typ ist der [Datagrammsocket](../mfc/windows-sockets-datagram-sockets.md).)  
  
 Streamsockets sorgen für einen Datenfluss ohne datensatzbegrenzungen: einen Datenstrom von Bytes, die bidirektionalen sein können (die Anwendung wird im Vollduplexmodus: Es kann sowohl Übertragung oder den Empfang durch das Socket). Datenströme können zurückgegriffen werden, um Sequenzierte, nicht duplizierter Daten. ("Sequenziert" bedeutet, dass Pakete in der gesendeten Reihenfolge zugestellt werden. "Keine Duplikate" bedeutet, dass Sie ein bestimmtes Paket nur einmal erhalten.) Empfang von Nachrichten Stream wird garantiert, und Streams eignen sich gut für die Verarbeitung großer Datenmengen.  
  
 Die Netzwerktransportschicht zusammensetzen oder Gruppieren von Daten in einer vernünftigen Größe Pakete. Die `CSocket` Klasse wird die Komprimierung und Entpacken Sie behandeln.  
  
 Streams basieren auf explizite Verbindungen: Socket A fordert eine Verbindung mit Socket B; Socket B zugelassen oder die Verbindung abgelehnt.  
  
 Ein Telefonanruf bietet eine gute Analogie für einen Datenstrom. Unter normalen Umständen hört die empfangende Partei an, was in der Reihenfolge sagen, dass Sie es, ohne Duplikate oder Verlust angegeben werden. Streamsockets sind geeignet, z. B. für Implementierungen, z. B. das Protokoll FTP (File Transfer), das die Übertragung von ASCII oder Binärdateien beliebiger Größe vereinfacht.  
  
 Streamsockets sind Datagrammsockets vorzuziehen, wenn die Daten gewährleistet werden müssen, auf das eingehen und Daten sehr groß ist. Weitere Informationen zu Streamsockets finden Sie unter der Windows Sockets-Spezifikation. Die Spezifikation ist im Windows SDK verfügbar.  
  
 Die Verwendung von Streamsockets kann von Anwendungen entwickelt, um einen Datagrammsocket verwenden, für die Übertragung an alle empfangenden Sockets im Netzwerk, da überlegen sein  
  
-   Broadcast Modell unterliegt Netzwerkprobleme geleiteten (oder "Storm").  
  
-   Anschließend übernommen Client / Server-Modell ist jedoch effizienter.  
  
-   Das Stream-Modell liefert zuverlässige Datenübertragungen, in dem das Datagramm-Modell nicht der Fall ist.  
  
-   Das fertige Modell nutzt die Möglichkeit für die Kommunikation zwischen Unicode und ANSI Socketanwendungen mit dieser Klasse, die CArchive CSocket-Klasse zu nutzen.  
  
    > [!NOTE]
    >  Bei Verwendung von Klasse `CSocket`, müssen Sie einen Datenstrom verwenden. MFC-Assertion schlägt fehl, wenn Sie angeben, dass den Sockettyp als **SOCK_DGRAM**.  
  
## <a name="see-also"></a>Siehe auch  
 [Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)   
 [Windows-Sockets: Hintergrund](../mfc/windows-sockets-background.md)

