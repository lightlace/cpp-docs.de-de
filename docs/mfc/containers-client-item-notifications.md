---
title: 'Container: Clientelement-Benachrichtigungen | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- notifications [MFC], container client item
- OLE containers [MFC], client-item notifications
- client items and OLE containers
ms.assetid: e1f1c427-01f5-45f2-b496-c5bce3d76340
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 58f995893f580ef41c27653a30e94d1f106fceb1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="containers-client-item-notifications"></a>Container: Client-Element-Benachrichtigungen
Dieser Artikel beschreibt die überschreibbaren-Funktionen, die MFC-Framework Ruft auf, wenn die serveranwendungen in Ihrer Clientanwendung Dokument Elemente ändern.  
  
 [COleClientItem](../mfc/reference/coleclientitem-class.md) definiert mehrere überschreibbare-Funktionen, die aufgerufen werden als Antwort auf Anforderungen von der Component-Anwendung, die auch die Server-Anwendung aufgerufen wird. Diese Overridables dienen in der Regel als Benachrichtigungen. Informieren sie die containeranwendung verschiedene Ereignisse aus, z. B. Durchführen eines Bildlaufs, Aktivierung oder eine Änderung der Position und Änderungen, die der Benutzer durchgeführt werden, wenn die Bearbeitung oder andernfalls das Element bearbeiten.  
  
 Das Framework benachrichtigt die containeranwendung von Änderungen durch einen Aufruf von `COleClientItem::OnChange`, eine überschreibbare Funktion, deren Implementierung erforderlich ist. Diese geschützte Funktion empfängt zwei Argumente. Die erste gibt den Grund, dass der Server das Element geändert:  
  
|Benachrichtigung|Bedeutung|  
|------------------|-------------|  
|`OLE_CHANGED`|Darstellung der OLE-Element wurde geändert.|  
|`OLE_SAVED`|OLE-Element wurde gespeichert.|  
|`OLE_CLOSED`|OLE-Element wurde geschlossen.|  
|**OLE_RENAMED**|Das Serverdokument, die mit der OLE-Element wurde umbenannt.|  
|`OLE_CHANGED_STATE`|OLE-Element wurde von einem Zustand in einen anderen geändert.|  
|**OLE_CHANGED_ASPECT**|Der OLE-Element zeichnen Aspekt wurde durch das Framework geändert.|  
  
 Diese Werte werden aus der **OLE_NOTIFICATION** -Enumeration, die in AFXOLE definiert ist. H.  
  
 Das zweite Argument für diese Funktion gibt an, wie sich das Element geändert hat oder welchem Zustand sich, dass er eingegeben wurde:  
  
|Wenn die erste Argument ist|Zweites argument|  
|----------------------------|---------------------|  
|`OLE_SAVED` oder `OLE_CLOSED`|Wird nicht verwendet.|  
|`OLE_CHANGED`|Gibt den Aspekt des OLE-Elements, das geändert wurde.|  
|`OLE_CHANGED_STATE`|Beschreibt den Status eingegeben werden (`emptyState`, **LoadedState**, `openState`, `activeState`, oder `activeUIState`).|  
  
 Weitere Informationen zu den Status einer Clientelement kann davon ausgehen, finden Sie unter [Container: Client-Element-Zustände](../mfc/containers-client-item-states.md).  
  
 Das Framework ruft `COleClientItem::OnGetItemPosition` Wenn ein Element für die direkte Bearbeitung aktiviert wird. Implementierung ist für Anwendungen, die direkte Bearbeitung unterstützen. Der MFC-Anwendung-Assistent bietet eine grundlegende Implementierung, die Koordinaten des Elements weist die `CRect` -Objekt, das als Argument übergeben wird `OnGetItemPosition`.  
  
 Wenn Position oder die Größe eines OLE-Elements während der direkte Bearbeitung ändert, wird der Container-Informationen über des Elements Position und Clipping Rechtecke muss aktualisiert werden, und der Server Informationen zu den Änderungen empfangen. Das Framework ruft `COleClientItem::OnChangeItemPosition` für diesen Zweck. Der MFC-Anwendung-Assistent bietet eine Außerkraftsetzung, die Funktion der Basisklasse aufruft. Bearbeiten Sie die Funktion, die für der Assistenten zum Schreiben Ihrer `COleClientItem`-abgeleitete Klasse, damit die Funktion alle Informationen, die vom Client-Element-Objekt beibehalten wird aktualisiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Containers](../mfc/containers.md)   
 [Container: Client-Element-Zustände](../mfc/containers-client-item-states.md)   
 [COleClientItem:: OnChangeItemPosition auf](../mfc/reference/coleclientitem-class.md#onchangeitemposition)

