---
title: Ableiten einer Dokumentklasse von CDocument
ms.date: 11/04/2016
helpviewer_keywords:
- CDocument class [MFC], deriving from
- classes [MFC], deriving from CDocument
- document objects [MFC], derived
- derived classes [MFC], functions often overridden
- document classes [MFC], functions often overridden
ms.assetid: e6a198e0-9799-43c0-83c5-04174d8b532c
ms.openlocfilehash: 042ba7adc8d36e57a714e03ec67c1c0f22b4da78
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50496121"
---
# <a name="deriving-a-document-class-from-cdocument"></a>Ableiten einer Dokumentklasse von CDocument

Dokumente enthalten, und die Daten Ihrer Anwendung zu verwalten. Um MFS-Anwendungsassistenten bereitgestellter Document-Klasse verwenden zu können, müssen Sie die folgenden Schritte ausführen:

- Leiten Sie eine Klasse von `CDocument` für jeden Typ des Dokuments.

- Hinzufügen von Membervariablen zum Speichern von Daten des Dokuments.

- Außer Kraft setzen `CDocument`des `Serialize` Member-Funktion in der Dokumentklasse. `Serialize` schreibt, und die Daten des Dokuments zum und vom Datenträger liest.

## <a name="other-document-functions-often-overridden"></a>Oft überschrieben Dokumentfunktionen für andere

Sie können auch andere überschreiben möchten `CDocument` Memberfunktionen. Insbesondere werden oft müssen Sie überschreiben [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) und [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) zum Initialisieren des Dokuments ab-Datenmember und [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) zerstören dynamisch zugeordnete Daten. Informationen zu überschreibbaren Membern finden Sie in der Klasse [CDocument](../mfc/reference/cdocument-class.md) in die *MFC-Referenz*.

## <a name="see-also"></a>Siehe auch

[Verwenden von Dokumenten](../mfc/using-documents.md)

