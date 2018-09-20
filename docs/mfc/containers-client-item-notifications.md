---
title: 'Container: Client-Element-Benachrichtigungen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], container client item
- OLE containers [MFC], client-item notifications
- client items and OLE containers
ms.assetid: e1f1c427-01f5-45f2-b496-c5bce3d76340
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5db5170b6c946e4bfeda99a3275f045a07fc9beb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46435219"
---
# <a name="containers-client-item-notifications"></a>Container: Client-Element-Benachrichtigungen

Dieser Artikel beschreibt die überschreibbaren-Funktionen, die MFC-Framework aufruft, wenn Server-Anwendungen in der Clientanwendung Dokument Elemente ändern.

[COleClientItem](../mfc/reference/coleclientitem-class.md) definiert mehrere überschreibbare-Funktionen, die aufgerufen werden als Antwort auf Anforderungen von der Komponente-Anwendung, die auch die Server-Anwendung aufgerufen wird. Diese / / Overridables fungieren in der Regel als Benachrichtigungen. Informieren sie die Container-Anwendung, der verschiedene Ereignisse wie scrollen, Aktivierung oder eine Änderung der Position, und der Änderungen, die der Benutzer hat beim Bearbeiten oder bearbeiten andernfalls das Element.

Das Framework benachrichtigt Ihre containeranwendung Änderungen durch einen Aufruf von `COleClientItem::OnChange`, eine überschreibbare Funktion, deren Implementierung erforderlich ist. Diese geschützte Funktion empfängt zwei Argumente. Die erste gibt an, der Grund, dass der Server das Element geändert wird:

|benachrichtigungs-|Bedeutung|
|------------------|-------------|
|**OLE_CHANGED**|Darstellung für das OLE-Element wurde geändert.|
|**OLE_SAVED**|Das OLE-Element wurde gespeichert.|
|**OLE_CLOSED**|Das OLE-Element wurde geschlossen.|
|**OLE_RENAMED**|Das Serverdokument mit dem OLE-Element wurde umbenannt.|
|**OLE_CHANGED_STATE**|Das OLE-Element wurde von einem Zustand in einen anderen geändert.|
|**OLE_CHANGED_ASPECT**|Das OLE-Element zeichnen Aspekt wurde durch das Framework geändert.|

Diese Werte werden aus der **OLE_NOTIFICATION** -Enumeration, die in AFXOLE definiert ist. H.

Das zweite Argument für diese Funktion gibt an, wie sich das Element geändert hat oder was angeben, dass er eingegeben wurde:

|Wenn die erste Argument ist|Zweites argument|
|----------------------------|---------------------|
|**OLE_SAVED** oder **OLE_CLOSED**|Wird nicht verwendet.|
|**OLE_CHANGED**|Gibt den Aspekt des OLE-Elements, die geändert wurde.|
|**OLE_CHANGED_STATE**|Beschreibt den Status, die eingegeben wird (*EmptyState*, *LoadedState*, *OpenState*, *ActiveState*, oder  *ActiveUIState*).|

Weitere Informationen zu den Status einer Client-Element kann davon ausgehen, finden Sie unter [Container: Client-Element-Zustände](../mfc/containers-client-item-states.md).

Das Framework ruft `COleClientItem::OnGetItemPosition` Wenn ein Element für direktes Editieren aktiviert wird. Implementierung ist für Anwendungen mit Unterstützung für direktes Editieren erforderlich. Der MFC-Anwendung-Assistent bietet eine grundlegende Implementierung, die Koordinaten des Elements weist die `CRect` -Objekt, das als Argument übergeben wird `OnGetItemPosition`.

Wenn ein OLE-Element Position oder Größe während der direkten Bearbeitung ändert, des Containers-Informationen des Elements Position und Clipping Rechtecke muss aktualisiert werden, und der Server muss Informationen zu den Änderungen erhalten. Das Framework ruft `COleClientItem::OnChangeItemPosition` für diesen Zweck. Der MFC-Anwendung-Assistent bietet eine Außerkraftsetzung, die die Basisklasse-Funktion aufruft. Bearbeiten Sie die Funktion, die der Anwendungs-Assistent ist, schreibt Ihre `COleClientItem`-Klasse, damit die Funktion keine Informationen beibehalten, die von Ihrem Client-Element-Objekt aktualisiert.

## <a name="see-also"></a>Siehe auch

[Container](../mfc/containers.md)<br/>
[Container: Client-Element-Zustände](../mfc/containers-client-item-states.md)<br/>
[COleClientItem:: OnChangeItemPosition auf](../mfc/reference/coleclientitem-class.md#onchangeitemposition)

