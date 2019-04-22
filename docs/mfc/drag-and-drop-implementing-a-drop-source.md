---
title: 'Drag & Drop: Implementieren einer Drop-Quelle'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE drag and drop [MFC], initiating drag operations
- drag and drop [MFC], calling DoDragDrop
- OLE drag and drop [MFC], drop source
- OLE drag and drop [MFC], calling DoDragDrop
- drag and drop [MFC], initiating drag operations
- drag and drop [MFC], drop source
ms.assetid: 0ed2fda0-63fa-4b1e-b398-f1f142f40035
ms.openlocfilehash: 2aa593fa953f7a9874036d48124ae7b92d88e0a6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58768639"
---
# <a name="drag-and-drop-implementing-a-drop-source"></a>Drag & Drop: Implementieren einer Drop-Quelle

In diesem Artikel wird erläutert, wie Sie Ihre Anwendung für die Bereitstellung von Daten für einen Drag & Drop-Vorgang abrufen.

Grundlegende Implementierung einer Drop-Quelle ist relativ einfach. Der erste Schritt ist, um zu bestimmen, welche Ereignisse Einleiten eines Ziehvorgangs. Empfohlen, den Anfang eines Ziehvorgangs als die Auswahl der Daten definieren, Richtlinien zur Benutzeroberfläche und eine **WM_LBUTTONDOWN** Ereignis, die auf einen Punkt innerhalb der ausgewählten Daten auftreten. Die MFC-OLE-Beispiele [OCLIENT](../overview/visual-cpp-samples.md) und [HIERSVR](../overview/visual-cpp-samples.md) befolgen Sie diese Richtlinien.

Wenn Ihre Anwendung ein Container ist, und die ausgewählten Daten ein verknüpftes oder eingebettetes Objekt vom Typ ist `COleClientItem`, rufen Sie die `DoDragDrop` Member-Funktion. Erstellen Sie andernfalls eine `COleDataSource` Objekt initialisieren Sie sie mit der Auswahl, und rufen Sie des Datenquellenobjekts `DoDragDrop` Member-Funktion. Wenn Ihre Anwendung auf einem Server ist, verwenden Sie `COleServerItem::DoDragDrop`. Informationen zum Anpassen von Standard-Drag & Drop-Verhalten, finden Sie im Artikel [Drag & Drop: Anpassen von](../mfc/drag-and-drop-customizing.md).

Wenn `DoDragDrop` gibt **DROPEFFECT_MOVE**, löschen Sie die Daten sofort aus dem Quelldokument. Keine anderen Rückgabewert `DoDragDrop` hat keinerlei Auswirkungen auf die Ablagequelle.

Weitere Informationen finden Sie unter:

- [Implementieren eines Drop-Ziels](../mfc/drag-and-drop-implementing-a-drop-target.md)

- [Anpassen von Drag & Drop](../mfc/drag-and-drop-customizing.md)

- [Erstellen und Zerstören von OLE-Datenobjekte und Datenquellen](../mfc/data-objects-and-data-sources-creation-and-destruction.md)

- [Bearbeiten von OLE-Datenobjekte und Datenquellen](../mfc/data-objects-and-data-sources-manipulation.md)

## <a name="see-also"></a>Siehe auch

[Drag & Drop (OLE)](../mfc/drag-and-drop-ole.md)<br/>
[COleDataSource::DoDragDrop](../mfc/reference/coledatasource-class.md#dodragdrop)<br/>
[COleClientItem::DoDragDrop](../mfc/reference/coleclientitem-class.md#dodragdrop)<br/>
[CView::OnDragLeave](../mfc/reference/cview-class.md#ondragleave)
