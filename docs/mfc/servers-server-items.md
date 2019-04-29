---
title: 'Server: Server-Elemente'
ms.date: 11/04/2016
helpviewer_keywords:
- server items, implementing
- servers [MFC], server items
- architecture [MFC], server-item
- server items
- OLE server applications [MFC], server items
ms.assetid: 28ba81a1-726a-4728-a52d-68bc7efd5a3c
ms.openlocfilehash: abee619aa921b3e036a2bbeb1b4f5ae08d83f5bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62307847"
---
# <a name="servers-server-items"></a>Server: Server-Elemente

Wenn ein Container einen Server gestartet wird, damit ein Benutzer ein eingebettetes oder verknüpftes OLE-Element bearbeiten kann, erstellt die Serveranwendung ein "Serverelement". Das Element für Server, ein Objekt einer Klasse abgeleitet `COleServerItem`, stellt eine Schnittstelle zwischen dem Serverdokument und die Container-Anwendung bereit.

Die `COleServerItem` -Klasse definiert mehrere überschreibbare Memberfunktionen, die von OLE, in der Regel als Antwort auf Anforderungen aus dem Container aufgerufen werden. Server-Elemente können Teil des Serverdokuments oder das gesamte Dokument darstellen. Wenn ein OLE-Element im Containerdokument eingebettet ist, stellt das Serverelement den gesamten Server-Dokument dar. Wenn das OLE-Element verknüpft wird, kann das Serverelement darstellen, einen Teil des Serverdokuments oder das gesamte Dokument, je nachdem, ob der Link zu einem Part und die gesamte.

In der [HIERSVR](../overview/visual-cpp-samples.md) z. B. die Server-Item-Klasse, Beispiel `CServerItem`, verfügt über einen Member, die ein Zeiger auf ein Objekt der Klasse ist `CServerNode`. Die `CServerNode` Objekt ist ein Knoten in der Anwendung HIERSVR-Dokument, das eine Struktur ist. Wenn die `CServerNode` Objekt ist der Stammknoten der `CServerItem` Objekt darstellt, das gesamte Dokument. Wenn die `CServerNode` Objekt ist, einen untergeordneten Knoten der `CServerItem` -Objekt stellt einen Teil des Dokuments dar. Finden Sie im MFC-OLE-Beispiel [HIERSVR](../overview/visual-cpp-samples.md) ein Beispiel für diese Interaktion.

##  <a name="_core_implementing_server_items"></a> Implementieren von Server-Elemente

Wenn Sie den Assistenten zum verwenden, um "Starter"-Code für Ihre Anwendung zu erzeugen, alles, was Sie tun, um die Serverelemente in Ihrem Startcode enthalten ist, eine der Serveroptionen über die Seite OLE-Optionen wählen. Wenn Sie Server-Elemente zu einer vorhandenen Anwendung hinzufügen, führen Sie die folgenden Schritte aus:

#### <a name="to-implement-a-server-item"></a>Um einen zu implementieren.

1. Leiten Sie eine Klasse von `COleServerItem` ab.

1. In der abgeleiteten Klasse außer Kraft setzen der `OnDraw` Member-Funktion.

   Das Framework ruft `OnDraw` das OLE-Element in einer Metadatei zu rendern. Die Container-Anwendung verwendet dieses Metadatei zum Rendern des Elements an. Ansichtsklasse der Anwendung verfügt auch über eine `OnDraw` Member-Funktion, die verwendet wird, zum Rendern des Elements, wenn die Serveranwendung aktiv ist.

1. Implementieren Sie eine Überschreibung der `OnGetEmbeddedItem` für die Server-Dokument-Klasse. Weitere Informationen finden Sie im Artikel [Server: Implementieren von Serverdokumenten](../mfc/servers-implementing-server-documents.md) und im MFC-OLE-Beispiel [HIERSVR](../overview/visual-cpp-samples.md).

1. Implementieren Sie Ihre Server-Item-Klasse `OnGetExtent` Member-Funktion. Das Framework ruft diese Funktion, um die Größe des Elements abrufen. Bei der Standardimplementierung wird keine Aktion ausgeführt.

##  <a name="_core_a_tip_for_server.2d.item_architecture"></a> Ein Tipp für Serverelement Architektur

Wie im [Berichtsserverelemente implementieren](#_core_implementing_server_items), Server-Anwendungen müssen in der Lage, Elemente, die sowohl in der Serveransicht auch in einer Metadatei ein, die die Container-Anwendung zu rendern. In der Microsoft Foundation Class Library-Anwendungsarchitektur, die Ansichtsklasse des `OnDraw` Memberfunktion rendert das Element aus, wenn er bearbeitet wird (finden Sie unter [CView:: OnDraw](../mfc/reference/cview-class.md#ondraw) in die *Klassenbibliotheksreferenz* ). Des Serverelement `OnDraw` rendert das Element in einer Metadatei in allen anderen Fällen (finden Sie unter [COleServerItem:: OnDraw](../mfc/reference/coleserveritem-class.md#ondraw)).

Duplizierung von Code zu vermeiden, Schreiben Hilfsfunktionen in Ihrer Serverdokument Klasse und Aufrufen von der `OnDraw` Funktionen in Ihren Kursen anzeigen und Server-Element. Das MFC-OLE-Beispiel [HIERSVR](../overview/visual-cpp-samples.md) nutzt diese Strategie: die Funktionen `CServerView::OnDraw` und `CServerItem::OnDraw` beide rufen `CServerDoc::DrawTree` zum Rendern des Elements.

Die Ansicht und das Element enthalten `OnDraw` Memberfunktionen, da sie unter verschiedenen Bedingungen zeichnen. Die Ansicht muss berücksichtigt wie Zoomen, Auswahlgröße und Umfang, Clipping und Elemente der Benutzeroberfläche wie z. B. Bildlaufleisten Faktoren. Das Serverelement zeichnet auf der anderen Seite immer das gesamte OLE-Objekt.

Weitere Informationen finden Sie unter [CView:: OnDraw](../mfc/reference/cview-class.md#ondraw), [COleServerItem](../mfc/reference/coleserveritem-class.md), [COleServerItem:: OnDraw](../mfc/reference/coleserveritem-class.md#ondraw), und [COleServerDoc::OnGetEmbeddedItem](../mfc/reference/coleserverdoc-class.md#ongetembeddeditem)in die *Class Library Reference*.

## <a name="see-also"></a>Siehe auch

[Server](../mfc/servers.md)
