---
title: Datenobjekte und Datenquellen (OLE)
ms.date: 11/04/2016
helpviewer_keywords:
- data objects [MFC], definition
- data transfer [MFC]
- OLE [MFC], data transfer
- data sources [MFC], definition
- data transfer [MFC], definition
- OLE [MFC], data objects
- OLE [MFC], data sources
ms.assetid: 8f68eed8-0ce8-4489-a4cc-f95554f89090
ms.openlocfilehash: 09e328171657c3c6557a5d77acae0f034e517955
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50612484"
---
# <a name="data-objects-and-data-sources-ole"></a>Datenobjekte und Datenquellen (OLE)

Beim Ausführen einer Datenübertragung, entweder über die Zwischenablage oder Drag & Drop, enthält die Daten an eine Quelle und Ziel. Eine Anwendung gibt die Daten für das Kopieren und eine andere Anwendung akzeptiert das Element zum Einfügen. Jede Seite der Übertragung muss zum Durchführen verschiedener Vorgänge mit den gleichen Daten für die Übertragung erfolgreich ist. Die Microsoft Foundation Class (MFC)-Bibliothek bietet zwei Klassen, die jede Seite der Übertragung darstellen:

- Datenquellen (wie von implementiert `COleDataSource` Objekte) darstellen die Quellseite der Datenübertragung. Sie werden durch die quellanwendung erstellt, wenn Daten in die Zwischenablage kopiert werden sollen, oder wenn Daten für einen Drag & Drop-Vorgang bereitgestellt werden.

- Datenobjekte (wie von implementiert `COleDataObject` Objekte) darstellen der Zielseite der Datenübertragung. Sie werden erstellt, wenn die Zielanwendung Daten, die gelöscht werden enthält, darin, oder wenn es angefordert wird, zum eines Einfügevorgangs aus der Zwischenablage.

In den folgenden Artikeln wird erläutert, wie Datenobjekte und Datenquellen in Ihren Anwendungen verwenden. Diese Informationen gelten für Container und Server-Anwendungen, da beide bei aufgerufen werden können, kopieren und Einfügen von Daten.

- [Datenobjekte und Datenquellen: Erstellen und Zerstören](../mfc/data-objects-and-data-sources-creation-and-destruction.md)

- [Datenobjekte und Datenquellen: Bearbeitung](../mfc/data-objects-and-data-sources-manipulation.md)

## <a name="in-this-section"></a>In diesem Abschnitt

[Drag & Drop](../mfc/drag-and-drop-ole.md)

[Zwischenablage](../mfc/clipboard.md)

## <a name="see-also"></a>Siehe auch

[OLE](../mfc/ole-in-mfc.md)<br/>
[COleDataObject-Klasse](../mfc/reference/coledataobject-class.md)<br/>
[COleDataSource-Klasse](../mfc/reference/coledatasource-class.md)
