---
title: Ableiten einer Dokumentklasse von CDocument | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CDocument class [MFC], deriving from
- classes [MFC], deriving from CDocument
- document objects [MFC], derived
- derived classes [MFC], functions often overridden
- document classes [MFC], functions often overridden
ms.assetid: e6a198e0-9799-43c0-83c5-04174d8b532c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b45dadbc062bbba61cdcb4c883f91943b1b18ba8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429824"
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

