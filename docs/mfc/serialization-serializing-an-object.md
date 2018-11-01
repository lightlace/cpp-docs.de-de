---
title: 'Serialisierung: Serialisieren eines Objekts'
ms.date: 11/04/2016
helpviewer_keywords:
- serializing objects [MFC]
- serialization [MFC], objects
- objects [MFC], serializing
ms.assetid: 1db772b1-ad55-4fcf-b133-126cca082510
ms.openlocfilehash: 10a7c52e6187f4db8345e1eadb88faeefa50b419
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588523"
---
# <a name="serialization-serializing-an-object"></a>Serialisierung: Serialisieren eines Objekts

Der Artikel [Serialisierung: Erstellen einer serialisierbaren Klasse](../mfc/serialization-making-a-serializable-class.md) zeigt, wie eine Klasse serialisierbar zu machen. Nachdem Sie eine serialisierbare Klasse haben, können Sie Objekte der Klasse in und aus einer Datei über serialisieren eine [CArchive](../mfc/reference/carchive-class.md) Objekt. In diesem Artikel wird erläutert:

- [Ist ein CArchive-Objekt](../mfc/what-is-a-carchive-object.md).

- [Zwei Möglichkeiten zum Erstellen einer CArchive](../mfc/two-ways-to-create-a-carchive-object.md).

- [Gewusst wie: Verwenden der CArchive <\< und >> Operatoren](../mfc/using-the-carchive-output-and-input-operators.md).

- [Speichern und Laden eines CObject per Archiv](../mfc/storing-and-loading-cobjects-via-an-archive.md).

Lassen Sie das Framework das Archiv für das serialisierbare Dokument zu erstellen, oder erstellen Sie explizit die `CArchive` Objekt selbst. Sie können Daten zwischen einer Datei und das serialisierbare Objekt übertragen, mit der <\< und >> Operatoren für `CArchive` oder in einigen Fällen durch Aufrufen der `Serialize` Funktion eine `CObject`-abgeleitete Klasse.

## <a name="see-also"></a>Siehe auch

[Serialisierung](../mfc/serialization-in-mfc.md)

