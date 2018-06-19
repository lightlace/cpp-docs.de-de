---
title: 'Windows Sockets: Verwenden der CAsyncSocket | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CAsyncSocket
dev_langs:
- C++
helpviewer_keywords:
- CAsyncSocket class [MFC], programming model
- Windows Sockets [MFC], asynchronous
- sockets [MFC], converting between Unicode and MBCS strings
- SOCKET handle
- sockets [MFC], asynchronous operation
- Windows Sockets [MFC], converting Unicode and MBCS strings
ms.assetid: 825dae17-7c1b-4b86-8d6c-da7f1afb5d8d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a96ccdd4ce5c49f18c12aa85060954fc97a3408b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385179"
---
# <a name="windows-sockets-using-class-casyncsocket"></a>Windows Sockets: Verwenden der Klasse CAsyncSocket
In diesem Artikel wird erläutert, wie Klasse [CAsyncSocket](../mfc/reference/casyncsocket-class.md). Denken Sie daran, dass diese Klasse der Windows Sockets-API auf einer sehr niedrigen Ebene kapselt. `CAsyncSocket` ist für die Verwendung durch den Programmierer, die Netzwerkkommunikation detailliert kennen jedoch die Vorteile von Rückrufen für die Benachrichtigung über Netzwerkereignisse werden soll. Dieser Artikel bietet basierend auf diese Annahme, nur grundlegende Anweisung. Möglicherweise sollten Sie mit `CAsyncSocket` Wenn Sie Windows-Sockets erleichterte Umgang mit mehreren Netzwerkprotokollen in einer MFC_Anwendung jedoch nicht die Flexibilität zu verzichten möchten. Sie können darüber hinaus können, Sie eine bessere Effizienz abrufen können, indem Sie programmieren, direkt selbst als konnte das Modell der allgemeinere alternative Klasse mithilfe `CSocket`.  
  
 `CAsyncSocket` finden Sie der *MFC-Referenz*. Visual C++ bietet auch die Windows Sockets-Spezifikation im Windows SDK. Die Details werden Ihnen überlassen. Visual C++ stellt keine beispielanwendung für `CAsyncSocket`.  
  
 Wenn Sie kein Netzwerkkommunikation hoch Durcharbeitung und eine einfache Lösung möchten, verwenden Sie die Klasse [CSocket](../mfc/reference/csocket-class.md) mit einem `CArchive` Objekt. Finden Sie unter [Windows Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md) für Weitere Informationen.  
  
 Dieser Artikel behandelt Folgendes:  
  
-   Erstellen und Verwenden einer `CAsyncSocket` Objekt.  
  
-   [Ihre Zuständigkeiten mit CAsyncSocket](#_core_your_responsibilities_with_casyncsocket).  
  
##  <a name="_core_creating_and_using_a_casyncsocket_object"></a> Erstellen und Verwenden eines CAsyncSocket-Objekts  
  
#### <a name="to-use-casyncsocket"></a>Verwenden der CAsyncSocket  
  
1.  Erstellen einer [CAsyncSocket](../mfc/reference/casyncsocket-class.md) Objekt, und verwenden Sie das Objekt zum Erstellen des zugrunde liegenden **SOCKET** behandeln.  
  
     Ein Socket folgt das Muster MFC zweistufige Konstruktion.  
  
     Zum Beispiel:  
  
     [!code-cpp[NVC_MFCSimpleSocket#3](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_1.cpp)]  
  
     - oder -   
  
     [!code-cpp[NVC_MFCSimpleSocket#4](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_2.cpp)]  
  
     Der erste Konstruktor oben erstellt ein `CAsyncSocket` Objekt auf dem Stapel. Der zweite Konstruktor erstellt ein `CAsyncSocket` auf dem Heap. Die erste [erstellen](../mfc/reference/casyncsocket-class.md#create) Aufruf oben die Standardparameter verwendet, um ein Streamsocket zu erstellen. Die zweite **erstellen** Aufruf erstellt einen Datagrammsocket mit einem angegebenen Port und Adresse. (Verwenden Sie entweder **erstellen** Version bei beiden Erstellungsmethoden zur.)  
  
     Die Parameter für **erstellen** sind:  
  
    -   Eine "Port": eine kurze ganze Zahl.  
  
         Für eine Serversocket müssen Sie einen Port angeben. Für eine Clientsocket akzeptieren Sie in der Regel der Standardwert für diesen Parameter, der Windows-Sockets, die einen Port auswählen kann.  
  
    -   Ein Sockeltyp: **SOCK_STREAM** (Standard) oder **SOCK_DGRAM**.  
  
    -   Ein Socket "Address", z. B. "ftp.microsoft.com" oder "128.56.22.8".  
  
         Dies ist Ihre Adresse IP (Internet Protocol) im Netzwerk. Sie werden wahrscheinlich immer auf den Standardwert für diesen Parameter verlassen.  
  
     Die Begriffe "Port" und "Socketadresse" in erläutert [Windows Sockets: Ports und Socketadressen](../mfc/windows-sockets-ports-and-socket-addresses.md).  
  
2.  Das Socketobjekt mit einem Server verbinden, wenn der Socket ein Client ist, socket mit [CAsyncSocket:: Connect](../mfc/reference/casyncsocket-class.md#connect).  
  
     - oder -   
  
     Wenn der Socket ein Server ist, legen Sie den Socket überwacht (mit [CAsyncSocket:: Listen](../mfc/reference/casyncsocket-class.md#listen)) verbinden Versuche von einem Client. Nach dem Empfang einer verbindungsanforderung wird, akzeptieren Sie sie mit [CAsyncSocket::Accept](../mfc/reference/casyncsocket-class.md#accept).  
  
     Nach dem Akzeptieren einer Verbindung, können Sie Aufgaben wie das Überprüfen von Kennwörtern ausführen.  
  
    > [!NOTE]
    >  Die **Accept** Member-Funktion akzeptiert einen Verweis auf ein neues, leeres `CSocket` -Objekt als Parameter. Sie müssen dieses Objekt erstellen, vor dem Aufruf **Accept**. Wenn dieses Socketobjekt den Gültigkeitsbereich verlässt, schließt die Verbindung. Rufen Sie nicht **erstellen** für dieses neue Socketobjekt. Ein Beispiel finden Sie im Artikel [Windows Sockets: Reihenfolge der Vorgänge](../mfc/windows-sockets-sequence-of-operations.md).  
  
3.  Führen Sie die Kommunikation mit anderen Sockets, durch Aufrufen der `CAsyncSocket` objektelementfunktionen, die die Windows Sockets-API-Funktionen zu kapseln.  
  
     Finden Sie in der Windows Sockets-Spezifikation und die Klasse [CAsyncSocket](../mfc/reference/casyncsocket-class.md) in der *MFC-Referenz*.  
  
4.  Zerstört das `CAsyncSocket` Objekt.  
  
     Wenn Sie das Socketobjekt auf dem Stapel erstellt, wird sein Destruktor aufgerufen, wenn die enthaltende-Funktion den Gültigkeitsbereich verlässt. Wenn Sie das Socketobjekt auf dem Heap erstellt haben, verwenden die **neue** -Operator, Sie sind verantwortlich für die Verwendung der **löschen** Operator, um das Objekt zu zerstören.  
  
     Ruft der Destruktor des Objekts [schließen](../mfc/reference/casyncsocket-class.md#close) Memberfunktion vor dem Löschen des Objekts.  
  
 Ein Beispiel für diese Sequenz im Code (tatsächlich für eine `CSocket` Objekt), finden Sie unter [Windows Sockets: Reihenfolge der Vorgänge](../mfc/windows-sockets-sequence-of-operations.md).  
  
##  <a name="_core_your_responsibilities_with_casyncsocket"></a> Ihre Zuständigkeiten mit CAsyncSocket  
 Wenn Sie ein Objekt der Klasse erstellen [CAsyncSocket](../mfc/reference/casyncsocket-class.md), das Objekt kapselt eine Windows **SOCKET** behandeln und Vorgänge für dieses Handle bereitstellt. Bei Verwendung von `CAsyncSocket`, müssen Sie alle Probleme, die Sie möglicherweise stoßen, wenn die API direkt verwenden müssen. Zum Beispiel:  
  
-   "Blockierung" Szenarien.  
  
-   Byte-Order-Unterschiede zwischen den sendenden und empfangenden Computer.  
  
-   Legen Sie konvertieren zwischen Unicode- und multibyte-Zeichensätze (MBCS)-Zeichenfolgen.  
  
 Definitionen dieser Begriffe und Weitere Informationen finden Sie unter [Windows Sockets: blockieren](../mfc/windows-sockets-blocking.md), [Windows Sockets: Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md), [Windows Sockets: Konvertieren von Zeichenfolgen](../mfc/windows-sockets-converting-strings.md) .  
  
 Trotz dieser Probleme-Klasse **CAsycnSocket** kann die richtige Wahl für Sie sein, wenn Ihre Anwendung erfordert, alle Flexibilität und Kontrolle, die Sie erhalten. Wenn nicht, Sie berücksichtigen sollten, mit der Klasse `CSocket` stattdessen. `CSocket` Viele der Details von Ihnen ausgeblendet: It Pumps Windows Nachrichten während der blockierenden aufrufen und bietet Ihnen der Zugriff auf `CArchive`, Byte Order Unterschiede und zeichenfolgenkonvertierung für Sie verwaltet.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Windows-Sockets: Hintergrund](../mfc/windows-sockets-background.md)  
  
-   [Windows-Sockets: Blockieren](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows-Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)

