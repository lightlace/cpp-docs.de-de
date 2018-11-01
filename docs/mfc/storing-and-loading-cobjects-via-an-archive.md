---
title: Speichern und Laden eines CObject per Archiv
ms.date: 11/04/2016
f1_keywords:
- CObject
helpviewer_keywords:
- CObjects [MFC], loading through archives
- CArchive class [MFC], storing and loading objects
- Serialize method, vs. CArchive operators
- CObject class [MFC], CArchive objects
- CObjects [MFC]
ms.assetid: a829b6dd-bc31-47e0-8108-fbb946722db9
ms.openlocfilehash: 370e8202d1bd1cda04edbdbd12bd936bdf5ef7b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50493690"
---
# <a name="storing-and-loading-cobjects-via-an-archive"></a>Speichern und Laden eines CObject per Archiv

Speichern und laden `CObject`über ein Archiv erfordert zusätzlich ist zu berücksichtigen. In bestimmten Fällen rufen Sie die `Serialize` Funktion des Objekts, in dem der `CArchive` Objekt ist ein Parameter der der `Serialize` Aufruf, im Gegensatz zur Verwendung der **< \<** oder **>>** Operator, der die `CArchive`. Wichtig zu bedenken ist, die die `CArchive` **>>** Operator Konstrukte der `CObject` im Arbeitsspeicher, die basierend auf `CRuntimeClass` Informationen, die zuvor durch das Speichern von Archiv in die Datei geschrieben.

Gibt an, ob Sie aus diesem Grund verwenden die `CArchive` **< \<** und **>>** Operatoren, im Vergleich zu Aufrufen `Serialize`, davon abhängig, ob Sie *müssen* das Archiv laden, um das Objekt dynamisch zu rekonstruieren basierend auf zuvor gespeicherte `CRuntimeClass` Informationen. Verwenden der `Serialize` -Funktion in den folgenden Fällen:

- Wenn das Objekt zu deserialisieren, wissen Sie im voraus die exakte Klasse des Objekts.

- Beim Deserialisieren des Objekts verfügen Sie bereits für dieses Volume zugewiesene Arbeitsspeicher.

> [!CAUTION]
>  Wenn Sie laden das Objekt mit der `Serialize` -Funktion, Sie müssen auch speichern, das mit der `Serialize` Funktion. Nicht speichern, indem die `CArchive` **<<** -Operator, und klicken Sie dann mithilfe von Load der `Serialize` Funktion, oder speichern Sie die Verwendung der `Serialize` Funktion, und klicken Sie dann zu laden, indem `CArchive >>` Operator.

Das folgende Beispiel veranschaulicht die Fälle:

[!code-cpp[NVC_MFCSerialization#36](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_1.h)]

[!code-cpp[NVC_MFCSerialization#37](../mfc/codesnippet/cpp/storing-and-loading-cobjects-via-an-archive_2.cpp)]

Zusammenfassend, wenn die serialisierbare Klasse definiert, die ein eingebettetes `CObject` als ein Element, sollten Sie *nicht* verwenden die `CArchive` **< \<** und **>>** Operatoren für dieses Objekt müssen jedoch die `Serialize` stattdessen funktionieren. Auch wenn die serialisierbare Klasse definiert, einen Zeiger auf eine `CObject` (oder ein Objekt abgeleitet `CObject`) als ein Element, aber Konstrukte dieses Objekt seinen eigenen Konstruktor, Sie sollten auch aufrufen `Serialize`.

## <a name="see-also"></a>Siehe auch

[Serialisierung: Serialisieren eines Objekts](../mfc/serialization-serializing-an-object.md)

