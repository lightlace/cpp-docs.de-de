---
title: 'Container: Clientelement-Zustände'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE containers [MFC], client-item states
- states, OLE container client-item
- lifetime, lifetime states and OLE container client items
- client items and OLE containers
ms.assetid: e7021caa-bd07-4adb-976e-f5f3d025bc53
ms.openlocfilehash: 1453ba3f96e49cefc9014a93ebcfbcfe5c6bc905
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273672"
---
# <a name="containers-client-item-states"></a>Container: Clientelement-Zustände

Dieser Artikel beschreibt die verschiedenen Zustände, die ein Clientelement, der während seiner Lebensdauer durchläuft.

Ein Clientelement übergibt durchlaufen mehrere Zustände, wie sie erstellt haben, aktiviert, geändert und gespeichert haben. Jedes Mal, wenn das Element den Zustand ändert, das Framework ruft [COleClientItem:: OnChange](../mfc/reference/coleclientitem-class.md#onchange) mit der **OLE_CHANGED_STATE** Benachrichtigung. Der zweite Parameter ist ein Wert aus der `COleClientItem::ItemState` Enumeration. Sie können eine der folgenden sein:

- *COleClientItem::emptyState*

- *COleClientItem::loadedState*

- *COleClientItem::openState*

- *COleClientItem::activeState*

- *COleClientItem::activeUIState*

In der leeren Zustand ist eine Client-Element nicht vollständig, aber ein Element. Arbeitsspeicher dafür zugeordnet wurde, aber es wurde noch nicht initialisiert wurde mit Daten für das OLE-Element. Dies ist der Status einer Client-Element befindet sich in, wenn durch einen Aufruf von Erstellung **neue** aber noch nicht im zweiten Schritt der typischen zweistufige Erstellung vorgenommen wurden.

Im zweiten Schritt ausgeführt, die durch einen Aufruf von `COleClientItem::CreateFromFile` oder einem anderen `CreateFrom` *Xxxx* -Funktion, die das Element wird vollständig erstellt. OLE-Daten (aus einer Datei oder einer anderen Quelle, z. B. die Zwischenablage) zugeordnet wurde die `COleClientItem`-abgeleitetes Objekt. Nachdem das Element in den geladenen Zustand befindet.

Wenn ein Element verfügt über wurde in das Serverzertifikat-Fenster geöffnet, anstatt direkt in den Container Dokument geöffnet, ist es in den Zustand öffnen (oder voll geöffnet). In diesem Zustand wird in der Regel eine Schraffur gezeichnet, über die Darstellung des Elements im Fenster des Containers, um anzugeben, dass das Element an anderer Stelle aktiv ist.

Wenn ein Element vorhanden aktiviert wurde, übergibt, in der Regel nur kurz gesagt, über den aktiven Status. Danach wechselt er in der Benutzeroberfläche im aktiven Status, in dem der Server die Menüs, Symbolleisten und andere Komponenten der Benutzeroberfläche mit denen des Containers zusammengeführt wurde. Das Vorhandensein dieser Komponenten der Benutzeroberfläche unterscheidet es sich um die Benutzeroberfläche im aktiven Status vom Zustand "aktiv". Andernfalls ähnelt der aktive Zustand der Benutzeroberfläche im aktiven Status. Wenn der Server zum Rückgängigmachen unterstützt, ist der Server erforderlich, um das OLE-Element wieder rückgängig zu machen Informationen beibehalten, bis die geladenen oder geöffneten Zustand erreicht.

## <a name="see-also"></a>Siehe auch

[Container](../mfc/containers.md)<br/>
[Activation (Aktivierung)](../mfc/activation-cpp.md)<br/>
[Container: Clientelement-Benachrichtigungen](../mfc/containers-client-item-notifications.md)<br/>
[Tracker](../mfc/trackers.md)<br/>
[CRectTracker-Klasse](../mfc/reference/crecttracker-class.md)
