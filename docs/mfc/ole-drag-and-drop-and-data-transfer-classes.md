---
title: OLE Drag & Drop und Datentransferklassen | Microsoft-Dokumentation
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
ms.openlocfilehash: a4b5d694d0081fbe2d852884c4a379e962c22f2a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444137"
---
# <a name="ole-drag-and-drop-and-data-transfer-classes"></a>OLE-Drag & Drop- und Datenübertragungs-Klassen

Diese Klassen sind in OLE-Datenübertragungen verwendet. Sie können Daten zwischen Anwendungen mithilfe der Zwischenablage oder durch Drag und Drop übertragen werden.

[COleDropSource](../mfc/reference/coledropsource-class.md)<br/>
Steuert den Drag & Drop-Vorgang von Anfang bis Ende. Diese Klasse bestimmt, wenn der Ziehvorgang beginnt und endet. Außerdem werden Cursor Feedback während des Drag & Drop-Vorgangs angezeigt.

[COleDataSource](../mfc/reference/coledatasource-class.md)<br/>
Verwendet, wenn eine Anwendung Daten für eine Datenübertragung bereitstellt. `COleDataSource` kann als Zwischenablagenobjekt objektorientierten angezeigt werden.

[COleDropTarget](../mfc/reference/coledroptarget-class.md)<br/>
Stellt das Ziel eines Drag & Drop-Vorgangs. Ein `COleDropTarget` Objekt entspricht einem Fenster auf dem Bildschirm. Es bestimmt, ob alle Daten auf ihm abgelegt werden und den tatsächlichen Drop-Vorgang implementiert.

[COleDataObject](../mfc/reference/coledataobject-class.md)<br/>
Verwendet als auf Empfängerseite `COleDataSource`. `COleDataObject` Objekte ermöglichen den Zugriff auf die Daten von einem `COleDataSource` Objekt.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)

