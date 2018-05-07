---
title: 'Container: Client-Element-Zustände | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE containers [MFC], client-item states
- states, OLE container client-item
- lifetime, lifetime states and OLE container client items
- client items and OLE containers
ms.assetid: e7021caa-bd07-4adb-976e-f5f3d025bc53
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5046ea7f3f3775cfe0009afe50f33a6ce6723cc0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="containers-client-item-states"></a>Container: Client-Element-Zustände
Dieser Artikel beschreibt die verschiedenen Zustände, die ein Clientelement während seiner Lebensdauer durchläuft.  
  
 Ein Clientelement übergibt durchlaufen mehrere Zustände, wie es erstellt, aktiviert, geändert und gespeichert wird. Jedes Mal, wenn das Element Zustandsänderungen, das Framework ruft [COleClientItem:: OnChange](../mfc/reference/coleclientitem-class.md#onchange) mit der `OLE_CHANGED_STATE` Benachrichtigung. Der zweite Parameter ist ein Wert aus der **COleClientItem:: ItemState** Enumeration. Es kann einer der folgenden sein:  
  
-   **COleClientItem::emptyState**  
  
-   **COleClientItem::loadedState**  
  
-   **COleClientItem::openState**  
  
-   **COleClientItem::activeState**  
  
-   **COleClientItem::activeUIState**  
  
 In den Zustand "leer" ist ein Clientelement noch nicht vollständig ein Element. Arbeitsspeicher dafür zugeordnet wurde, aber es wurde noch nicht initialisiert wurde mit Daten für das OLE-Element. Dies ist der Status einer Client-Element befindet sich in, wenn er durch einen Aufruf von erstellt wurde **neue** aber noch nicht im zweiten Schritt der Erstellung der Regel in zwei Schritten durchlaufen hat.  
  
 Im zweiten Schritt ausgeführt, die durch einen Aufruf von `COleClientItem::CreateFromFile` oder ein anderes **Aktivierungsmodus *** Xxxx* -Funktion, das Element vollständig erstellt. OLE-Daten (aus einer Datei oder einer anderen Quelle, z. B. der Zwischenablage) zugeordneten der `COleClientItem`-abgeleitetes Objekt. Jetzt ist das Element in den geladenen Zustand.  
  
 Wenn ein Element wurde wurde in der Server-Fenster geöffnet, anstatt direkt in den Container Dokument geöffnet, ist es im Zustand geöffnet (oder vollständig geöffnet). In diesem Status wird in der Regel eine Schraffur gezeichnet, über die Darstellung des Elements im Fenster "des Containers", um anzugeben, dass das Element an anderer Stelle aktiv ist.  
  
 Wenn ein Element direkt aktiviert wurde, übergibt er, in der Regel nur kurz, über den aktiven Zustand. Danach wechselt er in der Benutzeroberfläche im aktiven Status, in dem der Server seine Menüs, Symbolleisten und andere Komponenten Benutzeroberfläche, mit denen des Containers zusammengeführt wurde. Das Vorhandensein dieser Komponenten Benutzeroberfläche unterscheidet sich die Benutzeroberfläche im aktiven Status von aktiven Zustand. Andernfalls ähnelt der aktive Zustand der Benutzeroberfläche im aktiven Status. Wenn der Server zum Rückgängigmachen unterstützt, ist der Server erforderlich, um das OLE-Element rückgängig-Statusinformationen beibehalten, bis der geladenen oder geöffneten Zustand erreicht.  
  
## <a name="see-also"></a>Siehe auch  
 [Containers](../mfc/containers.md)   
 [Aktivierung](../mfc/activation-cpp.md)   
 [Container: Clientelement-Benachrichtigungen](../mfc/containers-client-item-notifications.md)   
 [Von Trackern](../mfc/trackers.md)   
 [CRectTracker-Klasse](../mfc/reference/crecttracker-class.md)
