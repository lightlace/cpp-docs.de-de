---
title: OLE-Drag &amp; Drop- und Datenübertragungs-Klassen
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
ms.openlocfilehash: e30a358da55b29f9519bc1ab8ee5c93ada308d98
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62186061"
---
# <a name="ole-drag-and-drop-and-data-transfer-classes"></a>OLE-Drag &amp; Drop- und Datenübertragungs-Klassen

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
