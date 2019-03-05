---
title: Verbindungspunkte
ms.date: 11/19/2018
f1_keywords:
- IConnectionPoint
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
ms.openlocfilehash: 6f934c4a5a24c5d54805a60e81cb0afdcdc2c14a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304742"
---
# <a name="connection-points"></a>Verbindungspunkte

In diesem Artikel wird erläutert, wie zum Implementieren von Verbindungspunkten (früher als OLE-Verbindungspunkte) unter Verwendung der MFC-Klassen `CCmdTarget` und `CConnectionPoint`.

In der Vergangenheit definiert das Component Object Model (COM) einen allgemeinen Mechanismus (`IUnknown::QueryInterface`*) darf, Objekte zu implementieren und Funktionalität in Schnittstellen verfügbar zu machen. Ein entsprechenden Mechanismus, der Objekte, die ihre Funktion aufrufen, bestimmte Schnittstellen verfügbar machen zulässig wurde jedoch nicht definiert. COM definiert d. h., wie eingehende Zeiger auf Objekte (Zeiger auf dieses Objekts Schnittstellen) behandelt wurden, aber es waren keine explizites Modell für Ausgangsschnittstellen (Zeiger das Objekt, auf andere Objekte Schnittstellen enthält). COM verfügt jetzt über ein Modell namens Verbindungspunkte, die diese Funktion unterstützt.

Eine Verbindung besteht aus zwei Teilen: das Objekt mit dem Aufruf der Schnittstelle, die aufgerufen wird, die Quelle und das Objekt, das die-Schnittstelle implementieren, die Senke aufgerufen haben. Ein Verbindungspunkt ist die Schnittstelle, die von der Quelle verfügbar gemacht werden. Durch einen Verbindungspunkt verfügbar zu machen, kann eine Quelle senken, um Verbindungen mit sich selbst (Quelle) herzustellen. Zeigen Sie über die Verbindung Mechanismus (die `IConnectionPoint` Schnittstelle), ein Zeiger auf die Ereignissenken-Schnittstelle mit dem Quellobjekt übergeben wird. This-Zeigers stellt die Quelle mit Zugriff auf die Senke in der Implementierung eines Satzes von Memberfunktionen bereit. Beispielsweise kann die Quelle zum Auslösen eines Ereignisses, das von der Senke implementiert, die entsprechende Methode der Senke der Implementierung aufrufen. Die folgende Abbildung veranschaulicht die Verbindung Zeitpunkt gerade beschrieben.

![Verbindungspunkt implementiert](../mfc/media/vc37lh1.gif "Verbindungspunkt implementiert") <br/>
Implementierter Verbindungspunkt

MFC implementiert dieses Modell in der [CConnectionPoint](../mfc/reference/cconnectionpoint-class.md) und [CCmdTarget](../mfc/reference/ccmdtarget-class.md) Klassen. Von abgeleiteten Klassen `CConnectionPoint` implementieren die `IConnectionPoint` Schnittstelle verwendet, um Verbindungspunkte für andere Objekte verfügbar zu machen. Von abgeleiteten Klassen `CCmdTarget` implementieren die `IConnectionPointContainer` -Schnittstelle, die Auflisten aller verfügbaren Verbindungspunkte eines Objekts oder einen bestimmten Verbindungspunkt finden kann.

Für jeden Verbindungspunkt in der Klasse implementiert wird müssen Sie eine-Verbindungsteil deklarieren, die den Verbindungspunkt implementiert. Wenn Sie eine oder mehrere Verbindungspunkte implementieren, müssen Sie auch eine einzelne Verbindung-Zuordnung in der Klasse deklarieren. Eine Zuordnung für die Verbindung ist eine Tabelle der Verbindungspunkte, die vom ActiveX-Steuerelement unterstützt wird.

Die folgenden Beispiele veranschaulichen eine einfache Verbindung Zuordnung und einem Verbindungspunkt an. Im ersten Beispiel wird der Verbindungstabelle und Punkt; im zweite Beispiel implementiert die Zuordnung und Punkt. Beachten Sie, dass `CMyClass` muss eine `CCmdTarget`-abgeleitete Klasse. Im ersten Beispiel Code eingefügt in der Klassendeklaration, unter dem **geschützt** Abschnitt:

[!code-cpp[NVC_MFCConnectionPoints#1](../mfc/codesnippet/cpp/connection-points_1.h)]

Die **BEGIN_CONNECTION_PART** und **END_CONNECTION_PART** Makros deklarieren eine eingebetteten Klasse `XSampleConnPt` (abgeleitet `CConnectionPoint`), implementiert dieses bestimmten Verbindungspunkt. Wenn Sie überschreiben möchten `CConnectionPoint` Memberfunktionen oder Memberfunktionen eigene hinzufügen, müssen sie zwischen diesen beiden Makros deklariert werden. Z. B. die `CONNECTION_IID` Makro überschreibt die `CConnectionPoint::GetIID` Memberfunktion, wenn Sie zwischen diesen beiden Makros platziert.

Im zweiten Beispiel wird der Code in der Implementierungsdatei (.cpp-Datei) des Steuerelements eingefügt. Dieser Code implementiert Verbindung Code Map, die den Verbindungspunkt enthält, `SampleConnPt`:

[!code-cpp[NVC_MFCConnectionPoints#2](../mfc/codesnippet/cpp/connection-points_2.cpp)]

Wenn Ihre Klasse verfügt über mehr als eine Verbindung, die zeigen, fügen Sie zusätzliche **CONNECTION_PART** Makros zwischen der **BEGIN_CONNECTION_MAP** und **END_CONNECTION_MAP** Makros.

Fügen Sie schließlich einen Aufruf von `EnableConnections` in den Konstruktor der Klasse. Zum Beispiel:

[!code-cpp[NVC_MFCConnectionPoints#3](../mfc/codesnippet/cpp/connection-points_3.cpp)]

Nachdem dieser Code eingefügt wurde, Ihre `CCmdTarget`-abgeleiteten Klasse stellt einen Verbindungspunkt für die `ISampleSink` Schnittstelle. Die folgende Abbildung veranschaulicht dieses Beispiel.

![Mithilfe von MFC implementierter Verbindungspunkt](../mfc/media/vc37lh2.gif "mithilfe von MFC implementierter Verbindungspunkt") <br/>
Mit MFC implementierter Verbindungspunkt

Verbindungspunkte unterstützen in der Regel "Multicasting" – die Möglichkeit, mehrere senken übertragen verbunden sind, auf die gleiche Schnittstelle. Das folgende Beispielfragment zeigt, wie Sie Multicast, indem jede Senke an einem Verbindungspunkt durchlaufen:

[!code-cpp[NVC_MFCConnectionPoints#4](../mfc/codesnippet/cpp/connection-points_4.cpp)]

In diesem Beispiel ruft den aktuellen Satz von Verbindungen ab, auf die `SampleConnPt` Verbindungspunkt mit einem Aufruf von `CConnectionPoint::GetConnections`. Anschließend durchläuft es die Verbindungen und ruft `ISampleSink::SinkFunc` auf jedes aktive Verbindung.

## <a name="see-also"></a>Siehe auch

[MFC COM](../mfc/mfc-com.md)
