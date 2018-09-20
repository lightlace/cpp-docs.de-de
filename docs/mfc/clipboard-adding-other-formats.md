---
title: 'Zwischenablage: Hinzufügen anderer Formate | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- formats [MFC], Clipboard
- Clipboard, formats
- custom formats, placing on Clipboard
- custom formats
- registering custom Clipboard data formats
- custom Clipboard data formats
ms.assetid: aea58159-65ed-4385-aeaa-3d9d5281903b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f2a34228a6e6b0c0d4f1800142e657a462aa095
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402004"
---
# <a name="clipboard-adding-other-formats"></a>Zwischenablage: Hinzufügen anderer Formate

In diesem Thema wird erläutert, wie zum Erweitern der Liste der unterstützten Formate, insbesondere für die Unterstützung von OLE wird. Das Thema [Zwischenablage: Daten kopieren und Einfügen](../mfc/clipboard-copying-and-pasting-data.md) beschreibt die minimale Implementierung, die zum Kopieren und Einfügen aus der Zwischenablage unterstützen. Wenn dies alles Sie implementieren ist, sind die einzigen Formate, die in der Zwischenablage platziert **CF_METAFILEPICT**, **CF_EMBEDSOURCE**, **CF_OBJECTDESCRIPTOR**, und möglicherweise **CF_LINKSOURCE**. Die meisten Anwendungen benötigen Weitere Formate in der Zwischenablage als diese drei.

##  <a name="_core_registering_custom_formats"></a> Registrieren benutzerdefinierte Formate

Um eigene benutzerdefinierte Formate zu erstellen, führen Sie auf die gleiche Prozedur, die Sie verwenden, wenn alle benutzerdefiniertes Format der Zwischenablage zu registrieren: übergeben Sie den Namen des Formats, das die **RegisterClipboardFormat** Funktion und ihren Rückgabewert als die Format-ID.

##  <a name="_core_placing_formats_on_the_clipboard"></a> Platzieren von Formaten in die Zwischenablage

Um weitere Formate, die in der Zwischenablage platziert hinzuzufügen, müssen Sie überschreiben die `OnGetClipboardData` Funktion in der Sie von einem abgeleiteten `COleClientItem` oder `COleServerItem` (je nachdem, ob die Daten kopiert werden systemeigene). In dieser Funktion sollten Sie das folgende Verfahren verwenden.

#### <a name="to-place-formats-on-the-clipboard"></a>Um Formate in der Zwischenablage zu platzieren.

1. Erstellen eines `COleDataSource`-Objekts

1. Übergeben Sie diese Datenquelle an eine Funktion, die die Liste der unterstützten Formate die systemeigene Datenformate, durch den Aufruf hinzufügt `COleDataSource::CacheGlobalData`.

1. Hinzufügen von standard-Formate durch Aufrufen von `COleDataSource::CacheGlobalData` für jedes Standardformat, das Sie unterstützen möchten.

Diese Technik wird verwendet, in der MFC-OLE-Beispielprogramm [HIERSVR](../visual-cpp-samples.md) (Überprüfen Sie die `OnGetClipboardData` Memberfunktion die **CServerItem** Klasse). Der einzige Unterschied in diesem Beispiel ist dieser Schritt 3 nicht implementiert ist, da HIERSVR keine andere standard-Formate unterstützt.

### <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [OLE-Objekte und Daten-Datenquellen und einheitliche Datenübertragung](../mfc/data-objects-and-data-sources-ole.md)

- [OLE- Drag & drop](../mfc/drag-and-drop-ole.md)

- [OLE](../mfc/ole-background.md)

## <a name="see-also"></a>Siehe auch

[Zwischenablage: Verwenden des OLE-Zwischenablagemechanismus](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

