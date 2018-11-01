---
title: OLE-Drag & Drop- und Datenübertragungs-Klassen
ms.date: 11/04/2016
f1_keywords:
- vc.classes.ole
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE drag and drop [MFC], and data transfer classes
- drag and drop [MFC], classes
- data transfer [MFC], OLE
- data transfer classes [MFC]
ms.assetid: c8ab2825-ed69-4b88-8ae6-f368b94726b8
ms.openlocfilehash: 7520881314da9568f6130f5fe2ccf0a3e0e88e2a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475183"
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

