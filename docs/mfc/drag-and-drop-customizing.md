---
title: 'Drag & Drop: Anpassen von | Microsoft-Dokumentation'
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
ms.openlocfilehash: 7dd7e88d6843ec3d95538e482c6c05a3d853f4d1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390764"
---
# <a name="drag-and-drop-customizing"></a>Drag & Drop: Anpassen

Die Standardimplementierung der Drag & Drop-Funktion ist für die meisten Anwendungen ausreichend. Einige Anwendungen erfordern jedoch möglicherweise, dass dieser gemäß dem Standardverhalten geändert werden. Dieser Artikel beschreibt die erforderlichen Schritte zum Ändern dieser Standardeinstellungen. Dieses Verfahren können Sie darüber hinaus Anwendungen einrichten, die Verbunddokumente als Drop-Quellen nicht unterstützen.

Wenn Sie sind standard OLE-Drag & Drop-Verhalten anpassen, oder Sie verfügen über eine nicht-OLE-Anwendung, müssen Sie erstellen eine `COleDataSource` Objekt, das die Daten enthalten. Wenn der Benutzer einen Drag & Drop-Vorgang gestartet wird, sollten Ihren Code Aufrufen der `DoDragDrop` Funktion, die von diesem Objekt nicht von anderen Klassen, die Drag & Drop-Vorgänge unterstützen.

Optional können Sie erstellen eine `COleDropSource` Objekt, das Steuern der Dropdownliste aus, und überschreiben einige seiner Funktionen je nach Art des Verhaltens, die Sie ändern möchten. Dieses & Drop-Source-Objekt wird dann an übergeben `COleDataSource::DoDragDrop` so ändern Sie das Standardverhalten dieser Funktionen. Diese verschiedenen Optionen bieten ein hohes Maß an Flexibilität in, wie Sie Drag & Drop-Vorgänge in Ihrer Anwendung unterstützen. Weitere Informationen zu Datenquellen finden Sie im Artikel [Datenobjekte und Datenquellen (OLE)](../mfc/data-objects-and-data-sources-ole.md).

Sie können die folgenden Funktionen zum Anpassen von Drag & Drop-Vorgänge überschreiben:

|außer Kraft setzen|Zum Anpassen|
|--------------|------------------|
|`OnBeginDrag`|Wie Initiieren des Ziehvorgangs wird nach dem Aufruf von `DoDragDrop`.|
|`GiveFeedback`|Visuelles Feedback, z. B. Cursor Darstellung, um verschiedene Ergebnisse zu erzielen.|
|`QueryContinueDrag`|Die Beendigung eines Drag & Drop-Vorgangs. Diese Funktion können Sie zum Überprüfen der Modifizierer Tastaturzuständen während des Ziehvorgangs.|

## <a name="see-also"></a>Siehe auch

[Drag & Drop (OLE)](../mfc/drag-and-drop-ole.md)<br/>
[COleDropSource-Klasse](../mfc/reference/coledropsource-class.md)<br/>
[COleDataSource-Klasse](../mfc/reference/coledatasource-class.md)
