---
title: 'Serialisierung: Serialisieren eines Objekts | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- serializing objects [MFC]
- serialization [MFC], objects
- objects [MFC], serializing
ms.assetid: 1db772b1-ad55-4fcf-b133-126cca082510
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e05cce1132b180ac8f1350b68d951d776a62315f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381087"
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

