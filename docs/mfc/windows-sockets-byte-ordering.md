---
title: 'Windows Sockets: Bytereihenfolge | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- byte order issues in sockets programming
- sockets [MFC], byte order issues
- Windows Sockets [MFC], byte order issues
ms.assetid: 8a787a65-f9f4-4002-a02f-ac25a5dace5d
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5c25a7b2c8240531e1d778d6a119f857032423db
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="windows-sockets-byte-ordering"></a>Windows Sockets: Bytereihenfolge
In diesem Artikel sowie zwei Begleit-Artikel wird erläutert, mehrere Probleme bei der Windows Sockets-Programmierung. Dieser Artikel behandelt die Bytereihenfolge. Die anderen Probleme werden in den Artikeln behandelt: [Windows Sockets: blockieren](../mfc/windows-sockets-blocking.md) und [Windows Sockets: Konvertieren von Zeichenfolgen](../mfc/windows-sockets-converting-strings.md).  
  
 Wenn Sie verwenden oder eine von der Klasse Ableitung [CAsyncSocket](../mfc/reference/casyncsocket-class.md), müssen Sie diese Probleme selbst verwalten. Wenn Sie verwenden oder eine von der Klasse Ableitung [CSocket](../mfc/reference/csocket-class.md), MFC für Sie verwaltet.  
  
## <a name="byte-ordering"></a>Die Bytereihenfolge  
 Abweichender Architektur werden manchmal Daten, die mit verschiedenen Bytereihenfolgen gespeichert. Intel-basierte Computer z. B. Datenspeicher in umgekehrter Reihenfolge (Motorola)-Macintosh-Computer an. Bytereihenfolge von Intel, "little-Endian," aufgerufen wird auch das Gegenteil von die standardmäßige "big-Endian-Reihenfolge. In der folgenden Tabelle werden diese Begriffe erläutert.  
  
### <a name="big--and-little-endian-byte-ordering"></a>Groß - und Little-Endian-Bytereihenfolge  
  
|Die Bytereihenfolge|Bedeutung|  
|-------------------|-------------|  
|Big-Endian|Das höchstwertige Byte wird am linken Ende eines Worts.|  
|Little-Endian|Das höchstwertige Byte ist am rechten Ende eines Worts.|  
  
 In der Regel werden Sie keine Bytereihenfolge-Konvertierung für Daten kümmern, die Sie senden und empfangen, die über das Netzwerk, aber es gibt Situationen, in denen Sie Bytereihenfolgen konvertieren müssen.  
  
## <a name="when-you-must-convert-byte-orders"></a>Wenn müssen Sie Bytereihenfolgen konvertieren.  
 In diesem Fall müssen Sie eine Bytereihenfolgen in den folgenden Situationen konvertieren:  
  
-   Übergeben Sie Informationen, die durch das Netzwerk, im Gegensatz zu den Daten interpretiert werden, die Sie mit einem anderen Computer gesendet werden muss. Sie können z. B. übergeben Ports und Adressen, die im Netzwerk kennen muss.  
  
-   Die Server-Anwendung, mit der Sie kommunizieren, ist eine MFC-Anwendung (und Sie haben keinen Quellcode dafür). Dies ruft Bytereihenfolge konvertiert, wenn die beiden Computer nicht die gleiche Bytereihenfolge gemeinsam verwenden.  
  
## <a name="when-you-do-not-have-to-convert-byte-orders"></a>Wenn Sie keine Bytereihenfolge konvertieren  
 Sie können die Arbeit der Konvertierung Bytereihenfolgen in den folgenden Situationen vermeiden:  
  
-   Die Computer auf beiden Seiten können nicht zum Austauschen von Bytes stimmen, und verwenden Sie beide Computer die gleiche Bytereihenfolge.  
  
-   Der Server, mit dem Sie kommunizieren, ist eine MFC-Anwendung.  
  
-   Sie haben Quellcode für den Server, dem Sie mit dem Sie kommunizieren, sodass Sie nicht explizit erkennen können, ob Sie Bytereihenfolgen oder nicht konvertieren, müssen.  
  
-   Sie können den Server mit MFC portieren. Dies ist recht einfach, und das Ergebnis ist in der Regel kleiner, schneller Code.  
  
 Arbeiten mit [CAsyncSocket](../mfc/reference/casyncsocket-class.md), Sie müssen alle erforderlichen Bytereihenfolge Konvertierungen selbst verwalten. Windows Sockets standardisiert "big-Endian-Bytereihenfolge-Modell und bietet Funktionen zum Konvertieren zwischen diesen Auftrag und andere. [CArchive](../mfc/reference/carchive-class.md), allerdings mit [CSocket](../mfc/reference/csocket-class.md), verwendet den umgekehrten Reihenfolge der ("little-Endian"), aber `CArchive` die Details der Bytereihenfolge-Konvertierungen für Sie übernimmt. Mithilfe dieser standard Anordnung in Ihren Anwendungen oder mithilfe von Windows-Sockets Bytereihenfolge Konvertierungsfunktionen können Sie Code besser portierbar vornehmen.  
  
 Das ideale Argument für die Verwendung von MFC-Sockets ist, wenn Sie beide Enden der Kommunikation schreiben und dabei eine MFC-Bibliothek an beiden Enden verwenden. Wenn Sie eine Anwendung, die mit nicht-MFC-Anwendungen, z. B. ein FTP-Server kommunizieren müssen Sie wahrscheinlich verwalten schreiben-Byteaustausch selbst, bevor Sie Daten in das Archivobjekt übergeben mithilfe der Windows Sockets-Konvertierungsroutinen **Ntohs**, **Ntohl**, **Htons**, und **Htonl**. Ein Beispiel für diese Funktionen bei der Kommunikation mit einer nicht-MFC-Anwendung verwendet, die weiter unten in diesem Artikel wird angezeigt.  
  
> [!NOTE]
>  Das andere Ende der Kommunikation keine MFC-Anwendung ist, Sie auch müssen vermeiden Sie beim streaming von C++-Objekte, die von abgeleiteten `CObject` in Ihrem Archiv, da der Empfänger nicht handhaben kann. Siehe den Hinweis in [Windows Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md).  
  
 Weitere Informationen zu Bytereihenfolgen finden Sie unter der Windows Sockets-Spezifikation, die im Windows SDK verfügbar.  
  
## <a name="a-byte-order-conversion-example"></a>Eine Bytereihenfolge-Konvertierungsbeispiel  
 Das folgende Beispiel zeigt eine Serialisierungsfunktion für eine `CSocket` -Objekt, ein Archiv verwendet. Darüber hinaus veranschaulicht er die Bytereihenfolge-Konvertierungsfunktionen in der Windows Sockets-API verwenden.  
  
 Dieses Beispiel zeigt ein Szenario, in dem Sie einen Client, mit der eine MFC-fremde Serveranwendung kommuniziert schreiben, für die Sie keinen Zugriff auf den Quellcode haben. In diesem Szenario müssen Sie davon ausgehen, dass der Server für die MFC-fremde Standardnetzwerk-Bytereihenfolge verwendet. Im Gegensatz dazu die MFC-Clientanwendung verwendet ein `CArchive` -Objekt mit einer `CSocket` -Objekt, und `CArchive` "little-Endian-Bytereihenfolge, das Gegenteil des standard-Netzwerks verwendet.  
  
 Angenommen Sie, die MFC-fremde-Server, mit dem Sie kommunizieren möchten, ein eingerichteten-Protokoll für ein Nachrichtenpaket wie folgt:  
  
 [!code-cpp[NVC_MFCSimpleSocket#5](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_1.cpp)]  
  
 MFC-Begriffen würde dies wie folgt ausgedrückt werden:  
  
 [!code-cpp[NVC_MFCSimpleSocket#6](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_2.cpp)]  
  
 In C++ ist eine `struct` ist im Wesentlichen identisch mit einer Klasse. Die `Message` Struktur kann verfügen über Memberfunktionen, z. B. die `Serialize` Memberfunktion oben deklariert. Die `Serialize` Memberfunktion kann wie folgt aussehen:  
  
 [!code-cpp[NVC_MFCSimpleSocket#7](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_3.cpp)]  
  
 Dieses Beispiel ruft für die Bytereihenfolge-Konvertierungen von Daten, da es ein klarer Konflikt gibt zwischen Bytereihenfolge der MFC-fremde Server-Anwendung an einem Ende und das `CArchive` in der MFC-Clientanwendung am anderen Ende verwendet. Das Beispiel zeigt mehrere die Bytereihenfolge-Konvertierungsfunktionen, die Windows-Sockets bereitstellt. In der folgenden Tabelle werden diese Funktionen beschrieben.  
  
### <a name="windows-sockets-byte-order-conversion-functions"></a>Windows Sockets-Byte-Order-Konvertierungsfunktionen  
  
|Funktion|Zweck|  
|--------------|-------------|  
|**ntohs**|Konvertieren Sie eine 16-Bit-Menge von netzwerkbyte-Reihenfolge, in die Host-Bytereihenfolge (von big-Endian in little-Endian).|  
|**ntohl**|Konvertieren Sie eine 32-Bit-Menge von netzwerkbyte-Reihenfolge, in die Host-Bytereihenfolge (von big-Endian in little-Endian).|  
|**Htons**|Konvertieren Sie eine 16-Bit-Menge von Host-Bytereihenfolge, in der netzwerkbyte-Reihenfolge (von little-Endian in big-Endian).|  
|**Htonl**|Konvertieren Sie eine 32-Bit-Menge von Host-Bytereihenfolge, in der netzwerkbyte-Reihenfolge (von little-Endian in big-Endian).|  
  
 Einem anderen Punkt in diesem Beispiel wird, wenn die Socket-Anwendung am anderen Ende der Kommunikation über eine MFC-fremde Anwendung ist, zu vermeiden müssen, etwa wie folgt ausführen:  
  
 `ar << pMsg;`  
  
 wobei `pMsg` ist ein Zeiger auf ein C++-Objekt, das von der Klasse abgeleitet `CObject`. Es wird, dass MFC Zusatzinformationen zugeordneten Objekte und der Server, die sie nicht versteht, als würde es sich um eine MFC-Anwendung gesendet.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Windows-Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows-Sockets: Hintergrund](../mfc/windows-sockets-background.md)  
  
-   [Windows-Sockets: Blockieren](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows-Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)

