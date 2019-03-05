---
title: Verwenden von Dokumenten
ms.date: 11/04/2016
helpviewer_keywords:
- documents [MFC], C++ applications
- data [MFC], reading
- documents [MFC]
- files [MFC], writing to
- data [MFC], documents
- files [MFC]
- views [MFC], C++ applications
- document/view architecture [MFC], documents
- reading data [MFC], documents and views
- printing [MFC], documents
- writing to files [MFC]
ms.assetid: f390d6d8-d0e1-4497-9b6a-435f7ce0776c
ms.openlocfilehash: fb35d1731912b2e322bc61621f7900e0d98e1e72
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57294680"
---
# <a name="using-documents"></a>Verwenden von Dokumenten

Zusammenarbeit, Dokumenten und Ansichten:

- Enthalten, verwalten und Anzeigen Ihrer anwendungsspezifischen [Daten](../mfc/managing-data-with-document-data-variables.md).

- Bieten eine Schnittstelle, bestehend aus [dokumentieren Datenvariablen](../mfc/managing-data-with-document-data-variables.md) zum Bearbeiten der Daten.

- Teilnehmen [schreiben und Lesen von Dateien](../mfc/serializing-data-to-and-from-files.md).

- Teilnehmen [Drucken](../mfc/role-of-the-view-in-printing.md).

- [Behandeln](../mfc/handling-commands-in-the-document.md) die meisten Befehle und Meldungen von der Anwendung.

Das Dokument ist besonders beim Verwalten von Daten. Store Sie Ihre Daten in der Regel in Klassenmembervariablen Dokument. Die Ansicht verwendet diese Variablen, um den Zugriff auf die Daten zum Anzeigen und aktualisieren. Standardmechanismus für die Serialisierung des Dokuments verwaltet lesen und Schreiben von Daten in und aus Dateien. Dokumente können auch Befehle (aber nicht über die Windows-Nachrichten als WM_COMMAND) behandeln.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Ableiten einer Dokumentklasse von CDocument](../mfc/deriving-a-document-class-from-cdocument.md)

- [Verwalten von Daten mit Dokumentdatenvariablen](../mfc/managing-data-with-document-data-variables.md)

- [Serialisieren von Daten in und aus Dateien](../mfc/serializing-data-to-and-from-files.md)

- [Umgehen des Serialisierungsmechanismus](../mfc/bypassing-the-serialization-mechanism.md)

- [Behandeln von Kommentaren in einem Dokument](../mfc/handling-commands-in-the-document.md)

- [Die OnNewDocument-Member-Funktion](../mfc/reference/cdocument-class.md#onnewdocument)

- [Die DeleteContents-Member-Funktion](../mfc/reference/cdocument-class.md#deletecontents)

## <a name="see-also"></a>Siehe auch

[Dokument-/Ansichtsarchitektur](../mfc/document-view-architecture.md)
