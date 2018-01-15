---
title: "Windows Sockets: Beispiel für Sockets mit Archiven | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- sockets [MFC], with archives
- examples [MFC], Windows Sockets
- Windows Sockets [MFC], with archives
ms.assetid: 2e3c9bb2-7e7b-4f28-8dc5-6cb7a484edac
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e0e70e8ecc14496b03bc758d91f078a926f33532
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="windows-sockets-example-of-sockets-using-archives"></a>Windows Sockets: Beispiel für Sockets mithilfe der Archive
In diesem Artikel zeigt ein Beispiel zur Verwendung der Klasse [CSocket](../mfc/reference/csocket-class.md). Das Beispiel setzt `CArchive` Objekte zum Serialisieren von Daten über ein Socket. Beachten Sie, dass dies nicht Dokumentserialisierung zu bzw. aus einer Datei ist.  
  
 Im folgende Beispiel wird veranschaulicht, wie das Archiv zum Senden und Empfangen von Daten über `CSocket` Objekte. Im Beispiel wird entwickelt, sodass zwei Instanzen der Anwendung (auf demselben Computer oder auf verschiedenen Computern im Netzwerk) Daten austauschen. Eine Instanz sendet Daten, die andere Instanz empfängt und bestätigt. Entweder Anwendung kann einen Austausch initiieren, und kann entweder als Server oder Client auf die andere Anwendung fungieren. Die folgende Funktion ist in der Ansichtsklasse der Anwendung definiert:  
  
 [!code-cpp[NVC_MFCSimpleSocket#1](../mfc/codesnippet/cpp/windows-sockets-example-of-sockets-using-archives_1.cpp)]  
  
 Der wichtigste Vorteil in diesem Beispiel ist, dass seine Struktur, die von einer MFC codenavigation `Serialize` Funktion. Die **PacketSerialize** Memberfunktion besteht aus einer **Wenn** -Anweisung mit einer **else** Klausel. Die Funktion empfängt zwei [CArchive](../mfc/reference/carchive-class.md) Verweise als Parameter: `arData` und `arAck`. Wenn die `arData` Archivobjekt zum Speichern von (senden) festgelegt ist die **Wenn** Branch ausgeführt wird; andernfalls gilt: Wenn `arData` festgelegt ist für das Laden (empfangen) die Funktion nimmt die **else** Verzweigung. Weitere Informationen zur Serialisierung in MFC finden Sie unter [Serialisierung](../mfc/how-to-make-a-type-safe-collection.md).  
  
> [!NOTE]
>  Die `arAck` wird davon ausgegangen, dass Archivobjekt ist das Gegenteil von `arData`. Wenn `arData` ist für das Senden, `arAck` empfängt, und das Gegenteil ist "true".  
  
 Zum Senden durchläuft die Beispielfunktion für eine angegebene Anzahl von Malen, jedes Mal generiert einige Zufallsdaten zu Demonstrationszwecken. Ihre Anwendung würde sich um echte Daten von einer Quelle, z. B. eine Datei abrufen. Die `arData` Operator zum Einfügen des Archivs (**<<**) wird verwendet, um einen Datenstrom von drei aufeinander folgende Segmente der Daten zu senden:  
  
-   Einem "Header", die die Art der Daten angibt (in diesem Fall werden die Werte von der `bValue` Variable und wie viele Kopien gesendet werden).  
  
     Beide Elemente werden in diesem Beispiel nach dem Zufallsprinzip generiert.  
  
-   Die angegebene Anzahl von Kopien der Daten.  
  
     Die innere **für** Schleife sendet `bValue` die angegebene Anzahl von Malen.  
  
-   Eine Zeichenfolge mit dem Namen `strText` , die der Empfänger die Benutzer werden angezeigt.  
  
 Für den Empfang, die Funktion kann auf ähnliche Weise identisch, jedoch das Archiv Extraktionsoperator verwendet (**>>**) zum Abrufen von Daten aus dem Archiv. Die empfangende Anwendung überprüft die Daten empfängt, zeigt die endgültige "Empfangen"-Nachricht und sendet dann eine Nachricht, die besagt, dass "Gesendet" für die sendende Anwendung angezeigt.  
  
 In diesem Kommunikationsmodell auf das Wort "Empfangen", die Nachricht gesendet, dem `strText` Variable ist für die Anzeige am anderen Ende der Kommunikation, sodass sie dem empfangenden Benutzer angibt, dass eine bestimmte Anzahl von Datenpaketen empfangen wurden. Der Empfänger antwortet mit einer ähnlichen Zeichenfolge, die besagt, auf den ursprünglichen Absender Bildschirm "Gesendet" für die Anzeige dass. Empfang der beiden Zeichenfolgen gibt an, dass erfolgreiche Kommunikation stattgefunden hat.  
  
> [!CAUTION]
>  Wenn Sie ein MFC-Clientprogramm zur Kommunikation mit Servern hergestellt (MFC-Fremd) schreiben, senden Sie C++-Objekte über das Archiv nicht. Wenn der Server eine MFC-Anwendung, die die Arten von Objekten zu verstehen, die Sie senden möchten ist, ist es kann nicht zum Empfangen und deserialisiert Objekte. Ein Beispiel, in dem Artikel [Windows Sockets: Bytereihenfolge](../mfc/windows-sockets-byte-ordering.md) zeigt eine Kommunikation dieses Typs.  
  
 Weitere Informationen finden Sie unter Windows Sockets-Spezifikation: **Htonl**, **Htons**, **Ntohl**, **Ntohs**. Darüber hinaus weitere Informationen finden Sie unter:  
  
-   [Windows-Sockets: Ableiten von Socket-Klassen](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Windows-Sockets: Wie Sockets mit Archiven arbeiten](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows-Sockets: Hintergrund](../mfc/windows-sockets-background.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)   
 [CArchive::IsStoring](../mfc/reference/carchive-class.md#isstoring)   
 [CArchive::operator <<](../mfc/reference/carchive-class.md#operator_lt_lt)   
 [CArchive::operator >>](../mfc/reference/carchive-class.md#operator_lt_lt)   
 [CArchive::Flush](../mfc/reference/carchive-class.md#flush)   
 [Einfügeoperatoren](../mfc/reference/cobject-class.md#serialize)

