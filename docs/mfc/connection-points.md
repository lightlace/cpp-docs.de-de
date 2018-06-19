---
title: Verbindungspunkte | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- IConnectionPoint
dev_langs:
- C++
helpviewer_keywords:
- IConnectionPoint interface
- connections, connection points
- OLE COM connection points
- MFC COM, connection points
- COM, connection points
- interfaces, IConnectionPoint
- MFC, COM support
- connection points [MFC]
- CCmdTarget class [MFC], and connection points
- sinks, connection points
ms.assetid: bc9fd7c7-8df6-4752-ac8c-0b177442c88d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 56686fe4ea2920f9365b84ec3064df4be95f4a3b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33346421"
---
# <a name="connection-points"></a>Verbindungspunkte
In diesem Artikel wird erläutert, wie zum Implementieren von Verbindungspunkten (früher OLE-Verbindungspunkte) mithilfe von MFC-Klassen `CCmdTarget` und `CConnectionPoint`.  
  
 In der Vergangenheit definiert das Component Object Model (COM) einen allgemeinen Mechanismus (**IUnknown:: QueryInterface**), die Objekte zum Implementieren und Verfügbarmachen von Funktionalität in Schnittstellen zulässig. Ein entsprechenden Mechanismus, der Objekte, die ihre Funktion aufrufen, bestimmte Schnittstellen verfügbar machen zulässig wurde jedoch nicht definiert. D. h. COM eingehender Zeiger auf Objekte definiert (Zeiger auf dieses Objekt Schnittstellen) behandelt wurden, aber es kein explizites Modell für Ausgangsschnittstellen (Zeiger das Objekt beinhalten, die auf andere Objekte Schnittstellen). COM verfügt jetzt über ein Modell als Verbindungspunkte bezeichnet, die diese Funktion unterstützt.  
  
 Eine Verbindung besteht aus zwei Teilen: Objekt beim Aufrufen der Schnittstelle mit dem Namen, die Quelle und das Objekt, das die-Schnittstelle implementieren, die so genannte Senke. Ein Verbindungspunkt ist die Schnittstelle, die von der Datenquelle verfügbar gemacht. Durch einen Verbindungspunkt verfügbar gemacht werden, kann eine Quelle senken zum Herstellen von Verbindungen mit sich selbst (Quelle). Zeigen Sie über die Verbindung Mechanismus (die **IConnectionPoint** Schnittstelle), ein Zeiger auf die Schnittstelle mit dem Quellobjekt übergeben wird. This-Zeiger bietet der Quelle mit Zugriff auf die Senke Implementierung eines Satzes von Memberfunktionen. Beispielsweise kann die Quelle zum Auslösen eines Ereignisses, das von der Senke implementiert, die entsprechende Methode der Implementierung die Senke aufrufen. Die folgende Abbildung veranschaulicht die Verbindung eben beschriebene zeigen.  
  
 ![Implementierte Verbindungspunkt](../mfc/media/vc37lh1.gif "vc37lh1")  
Implementierter Verbindungspunkt  
  
 MFC implementiert dieses Modell in der [CConnectionPoint](../mfc/reference/cconnectionpoint-class.md) und [CCmdTarget](../mfc/reference/ccmdtarget-class.md) Klassen. Abgeleitete Klassen von **CConnectionPoint** implementieren die **IConnectionPoint** Schnittstelle verwendet, um Verbindungspunkte für andere Objekte verfügbar zu machen. Abgeleitete Klassen von `CCmdTarget` implementieren die **IConnectionPointContainer** -Schnittstelle, die Auflisten aller verfügbaren Verbindungspunkte für ein Objekt oder einen bestimmten Verbindungspunkt suchen kann.  
  
 Für jeden Verbindungspunkt in der Klasse implementiert müssen Sie eine-Verbindungsteil deklarieren, die den Verbindungspunkt implementiert. Wenn Sie eine oder mehrere Verbindungspunkte implementieren, müssen Sie auch eine einzelne Verbindung-Zuordnung in der Klasse deklarieren. Eine Zuordnung für die Verbindung ist eine Tabelle von Verbindungspunkten vom ActiveX-Steuerelement unterstützt wird.  
  
 Die folgenden Beispiele veranschaulichen einen einfachen Verbindungstabelle und einen Verbindungspunkt. Im erste Beispiel deklariert Verbindung Karten- und Punkt. im zweite Beispiel implementiert die Zuordnung und Punkt. Beachten Sie, dass `CMyClass` muss eine `CCmdTarget`-Klasse. Im ersten Beispiel Code eingefügt in der Klassendeklaration unter der **geschützt** Abschnitt:  
  
 [!code-cpp[NVC_MFCConnectionPoints#1](../mfc/codesnippet/cpp/connection-points_1.h)]  
  
 Die `BEGIN_CONNECTION_PART` und **END_CONNECTION_PART** Makros deklarieren eine eingebettete Klasse `XSampleConnPt` (abgeleitet `CConnectionPoint`), implementiert dieses bestimmten Verbindungspunkt. Wenn Sie überschreiben möchten `CConnectionPoint` Memberfunktionen oder Hinzufügen von Memberfunktionen von Ihren eigenen, zwischen diesen zwei Makros zu deklarieren. Z. B. die `CONNECTION_IID` Makro überschreibt die `CConnectionPoint::GetIID` Memberfunktion, wenn zwischen diesen beiden Makros platziert.  
  
 Im zweiten Beispiel wird der Code in der Implementierungsdatei (.cpp-Datei) des Steuerelements eingefügt. Dieser Code implementiert die Verbindungstabelle, einschließlich den Verbindungspunkt `SampleConnPt`:  
  
 [!code-cpp[NVC_MFCConnectionPoints#2](../mfc/codesnippet/cpp/connection-points_2.cpp)]  
  
 Wenn die Klasse verfügt über mehr als eine Verbindung, die zeigen, fügen Sie zusätzliche `CONNECTION_PART` Makros zwischen den `BEGIN_CONNECTION_MAP` und `END_CONNECTION_MAP` Makros.  
  
 Fügen Sie schließlich einen Aufruf von `EnableConnections` im Konstruktor der Klasse. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCConnectionPoints#3](../mfc/codesnippet/cpp/connection-points_3.cpp)]  
  
 Sobald dieser Code eingefügt wurden, Ihre `CCmdTarget`-abgeleitete Klasse macht einen Verbindungspunkt für die **ISampleSink** Schnittstelle. Die folgende Abbildung veranschaulicht dieses Beispiel.  
  
 ![Mithilfe von MFC implementierter Verbindungspunkt](../mfc/media/vc37lh2.gif "vc37lh2")  
Ein mit MFC implementierter Verbindungspunkt  
  
 Verbindungspunkte unterstützen in der Regel "Multicasting" – die Möglichkeit, mehrere Ereignisempfängern Übertragung auf die gleiche Schnittstelle verbunden. Das folgende Beispielfragment zeigt, wie Sie Multicast durch jede Senke auf einem Verbindungspunkt durchlaufen:  
  
 [!code-cpp[NVC_MFCConnectionPoints#4](../mfc/codesnippet/cpp/connection-points_4.cpp)]  
  
 In diesem Beispiel ruft den aktuellen Satz von Verbindungen ab, auf die `SampleConnPt` Verbindungspunkt mit einem Aufruf von `CConnectionPoint::GetConnections`. Anschließend durchläuft es die Verbindungen und ruft **ISampleSink::SinkFunc** für jede aktive Verbindung.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC COM](../mfc/mfc-com.md)

