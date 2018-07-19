---
title: 'Drag & Drop: Anpassen von | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- drag and drop [MFC], implementing in non-OLE applications
- drag and drop [MFC], customizing behavior
- drag and  [MFC], COleDataSource object
- drag and drop [MFC], calling DoDragDrop
- OLE drag and drop [MFC], customizing behavior
ms.assetid: 03369d3e-46bf-4140-b58c-d0c9657cf38a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 59ec5a5a493106750fa7bb8c7ec31b8dbb011070
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344242"
---
# <a name="drag-and-drop-customizing"></a>Drag & Drop: Anpassen
Die standardmäßige Implementierung des Drag-and-Drop-Features reicht für die meisten Anwendungen zur Verfügung. Einige Anwendungen erfordern jedoch, dass dieses Standardverhalten geändert werden. Dieser Artikel beschreibt die erforderlichen Schritte zum Ändern dieser Standardeinstellungen. Darüber hinaus können Sie diese Technik verwenden, Anwendungen her, die Verbunddokumente als Drop-Quellen nicht unterstützen.  
  
 Wenn Sie standard-OLE-Drag & Drop-Verhalten anpassen, oder Sie verfügen über eine nicht-OLE-Anwendung, müssen Sie erstellen eine `COleDataSource` Objekt, das die Daten enthalten. Wenn der Benutzer einen Drag-and-Drop-Vorgang gestartet wird, sollten Ihren Code Aufrufen der `DoDragDrop` Funktion von diesem Objekt statt aus anderen Klassen, die Drag & Drop-Vorgänge unterstützen.  
  
 Optional können Sie erstellen eine `COleDropSource` Objekt zum Steuern der Dropdownliste aus, und überschreiben einige seiner Funktionen abhängig vom Verhalten, die Sie ändern möchten. Diese Ablagequelle Objekt wird dann zum übergeben `COleDataSource::DoDragDrop` so ändern Sie das Standardverhalten dieser Funktionen. Diese verschiedenen Optionen bieten ein hohes Maß an Flexibilität in wie Sie Drag & Drop-Operationen in Ihrer Anwendung unterstützen. Weitere Informationen zu Datenquellen finden Sie im Artikel [Datenobjekte und Datenquellen (OLE)](../mfc/data-objects-and-data-sources-ole.md).  
  
 Sie können die folgenden Funktionen zum Anpassen von Drag & Drop-Vorgänge überschreiben:  
  
|außer Kraft setzen|Zum Anpassen|  
|--------------|------------------|  
|`OnBeginDrag`|Wie Ziehen initiiert wird nach dem Aufruf `DoDragDrop`.|  
|`GiveFeedback`|Visuelles Feedback, z. B. die Darstellung des Cursors für verschiedene Drop Ergebnisse.|  
|`QueryContinueDrag`|Die Beendigung eines Drag-and-Drop-Vorgangs. Diese Funktion können Sie wichtige Zustände an Modifizierer während des Ziehvorgangs zu überprüfen.|  
  
## <a name="see-also"></a>Siehe auch  
 [Drag & Drop (OLE)](../mfc/drag-and-drop-ole.md)   
 [COleDropSource-Klasse](../mfc/reference/coledropsource-class.md)   
 [COleDataSource-Klasse](../mfc/reference/coledatasource-class.md)
