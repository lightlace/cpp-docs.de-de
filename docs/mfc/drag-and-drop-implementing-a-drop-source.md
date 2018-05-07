---
title: 'Drag & Drop: Implementieren einer Drop-Quelle | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE drag and drop [MFC], initiating drag operations
- drag and drop [MFC], calling DoDragDrop
- OLE drag and drop [MFC], drop source
- OLE drag and drop [MFC], calling DoDragDrop
- drag and drop [MFC], initiating drag operations
- drag and drop [MFC], drop source
ms.assetid: 0ed2fda0-63fa-4b1e-b398-f1f142f40035
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c057657605296b3ba65128f26b25aa526f45b211
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="drag-and-drop-implementing-a-drop-source"></a>Drag & Drop: Implementieren einer Drag & Drop-Quelle
In diesem Artikel wird erläutert, wie Ihre Anwendung zum Bereitstellen eines Drag & Drop-Vorgangs zu machen.  
  
 Grundlegende Implementierung einer Drop-Quelle ist relativ einfach. Der erste Schritt besteht, um zu bestimmen, welche Ereignisse Einleiten eines Ziehvorgangs. Empfohlene Richtlinien zur Benutzeroberfläche der Anfang eines Ziehvorgangs als die Auswahl der Daten definieren und ein `WM_LBUTTONDOWN` Ereignis auf einen Punkt innerhalb der ausgewählten Daten auftreten. MFC-OLE-Beispielen [OCLIENT](../visual-cpp-samples.md) und [HIERSVR](../visual-cpp-samples.md) gelten folgende Richtlinien.  
  
 Wenn Ihre Anwendung ein Container ist, und die ausgewählten Daten ein verknüpftes oder ein eingebettetes Objekt des Typs ist `COleClientItem`, rufen Sie die `DoDragDrop` Memberfunktion. Erstellen Sie andernfalls eine `COleDataSource` -Objekt, initialisieren Sie es mit der Auswahl und rufen Sie des Datenquellenobjekts `DoDragDrop` Memberfunktion. Wenn Ihre Anwendung auf einem Server ist, verwenden `COleServerItem::DoDragDrop`. Informationen zum Anpassen von standard-Drag & Drop-Verhalten, finden Sie im Artikel [Drag & Drop: Anpassen von](../mfc/drag-and-drop-customizing.md).  
  
 Wenn `DoDragDrop` gibt `DROPEFFECT_MOVE`, löschen Sie die Quelldaten sofort aus dem Quelldokument. Keine andere Rückgabewert `DoDragDrop` hat keine Auswirkung auf eine Drop-Quelle.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Implementieren eines Drop-Ziels](../mfc/drag-and-drop-implementing-a-drop-target.md)  
  
-   [Anpassen von Drag & Drop](../mfc/drag-and-drop-customizing.md)  
  
-   [Erstellen und Zerstören von OLE-Datenobjekte und Datenquellen](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [Bearbeiten von OLE-Datenobjekte und Datenquellen](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Drag & Drop (OLE)](../mfc/drag-and-drop-ole.md)   
 [Oledatasource](../mfc/reference/coledatasource-class.md#dodragdrop)   
 [COleClientItem::DoDragDrop](../mfc/reference/coleclientitem-class.md#dodragdrop)   
 [CView::OnDragLeave](../mfc/reference/cview-class.md#ondragleave)

