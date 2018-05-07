---
title: 'Drag & Drop: Implementieren eines Drop-Ziels | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE drag and drop [MFC], implementing drop targets
- OLE drag and drop [MFC], drop target
- drag and drop [MFC], drop target
ms.assetid: 0689f1ec-5326-4008-b226-4b373c881358
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 414437f044869fef7ae48883a88688ad50c9ac5f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="drag-and-drop-implementing-a-drop-target"></a>Drag & Drop: Implementieren eines Drag & Drop-Ziels
Dieser Artikel beschreibt, wie die Anwendung ein Ablageziel machen. Implementieren die Drop-Ziel etwas mehr als implementieren eine Drop-Quelle arbeiten belegt, aber es ist immer noch relativ einfach. Diese Techniken gelten auch für nicht-OLE-Anwendungen.  
  
#### <a name="to-implement-a-drop-target"></a>Drop-Ziel implementiert.  
  
1.  Fügen Sie eine Membervariable zu den einzelnen Sichten in der Anwendung, die auf ein Ablageziel sein sollen. Diese Membervariable muss vom Typ `COleDropTarget` oder eine Klasse abgeleitet.  
  
2.  Aus Ihrer Ansichtsklasse-Funktion, behandelt der `WM_CREATE` Nachricht (in der Regel `OnCreate`), rufen Sie der neue Membervariable `Register` Memberfunktion. `Revoke` wird automatisch für Sie aufgerufen werden, wenn die Ansicht zerstört wird.  
  
3.  Überschreiben Sie die folgenden Funktionen. Wenn Sie das gleiche Verhalten in der gesamten Anwendung möchten, überschreiben Sie diese Funktionen in Ihrer Ansichtsklasse. Gegebenenfalls Verhalten in isolierten Fällen ändern oder Löschen der nicht aktivieren möchten`CView` Windows, überschreiben Sie diese Funktionen in Ihrer `COleDropTarget`-Klasse abgeleitet.  
  
    |außer Kraft setzen|Um zu ermöglichen|  
    |--------------|--------------|  
    |`OnDragEnter`|Drop-Operationen in das Fenster erfolgen. Wird aufgerufen, wenn der Cursor zuerst das Fenster wechselt.|  
    |`OnDragLeave`|Besonderes Verhalten des Ziehvorgangs des angegebenen Fensters verlässt.|  
    |`OnDragOver`|Drop-Operationen in das Fenster erfolgen. Wird aufgerufen, wenn der Cursor über das Fenster gezogen wird.|  
    |`OnDrop`|Behandlung von Daten in das angegebene Fenster gelöscht wird.|  
    |`OnScrollBy`|Spezielles Verhalten für die beim Durchführen eines Bildlaufs erforderlich im Zielfenster ist.|  
  
 Der Datei MAINVIEW. CPP-Datei, die MFC-OLE-Beispiel durableservicefactory [OCLIENT](../visual-cpp-samples.md) für ein Beispiel für diese Funktionen wie zusammenarbeiten.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Implementieren einer Drop-Quelle](../mfc/drag-and-drop-implementing-a-drop-source.md)  
  
-   [Erstellen und Zerstören von OLE-Datenobjekte und Datenquellen](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [Bearbeiten von OLE-Datenobjekte und Datenquellen](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Drag & Drop (OLE)](../mfc/drag-and-drop-ole.md)   
 [COleDropTarget-Klasse](../mfc/reference/coledroptarget-class.md)
