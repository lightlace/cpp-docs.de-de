---
title: OLE Drag-and-Drop und Datentransferklassen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE drag and drop [MFC], and data transfer classes
- drag and drop [MFC], classes
- data transfer [MFC], OLE
- data transfer classes [MFC]
ms.assetid: c8ab2825-ed69-4b88-8ae6-f368b94726b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d55d6d171f490631afe17a605f50607fb55f070b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ole-drag-and-drop-and-data-transfer-classes"></a>OLE-Drag & Drop- und Datenübertragungs-Klassen
Diese Klassen werden in der OLE-Datenübertragungen verwendet. Sie können Daten zwischen Anwendungen mithilfe der Zwischenablage oder durch Drag und Drop übertragen werden.  
  
 [COleDropSource](../mfc/reference/coledropsource-class.md)  
 Steuert den Drag & Drop-Vorgang von Anfang bis Ende. Diese Klasse bestimmt, wenn der Ziehvorgang beginnt und endet. Er enthält außerdem Cursors während des Drag-and-Drop-Vorgangs.  
  
 [COleDataSource](../mfc/reference/coledatasource-class.md)  
 Verwendet, wenn eine Anwendung Daten für Datenübertragungen bereitstellt. `COleDataSource` kann als eine objektorientierte Zwischenablage-Datenobjekt angesehen werden.  
  
 [COleDropTarget](../mfc/reference/coledroptarget-class.md)  
 Stellt das Ziel eines Drag-and-Drop-Vorgangs. Ein `COleDropTarget` Objekt entspricht einem Fenster auf dem Bildschirm. Es bestimmt, ob akzeptieren keine Daten auf ihm abgelegt werden, und implementiert den tatsächliche Drop-Vorgang.  
  
 [COleDataObject](../mfc/reference/coledataobject-class.md)  
 Verwendet als auf der Empfängerseite `COleDataSource`. `COleDataObject` -Objekte ermöglichen den Zugriff auf die von gespeicherten Daten einer `COleDataSource` Objekt.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../mfc/class-library-overview.md)

