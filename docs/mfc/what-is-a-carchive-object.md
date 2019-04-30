---
title: Was ist ein CArchive-Objekt?
ms.date: 11/04/2016
f1_keywords:
- CArchive
helpviewer_keywords:
- archive objects [MFC]
- archives [MFC], for serialization
- buffers, serializable objects
- CArchive class [MFC], about CArchive class [MFC]
- buffering, serializable objects
ms.assetid: 843f1825-288d-4d89-a1fa-70e1f92d9b8b
ms.openlocfilehash: 4bae451168449ce3e120ba9d172a615864ac2157
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346380"
---
# <a name="what-is-a-carchive-object"></a>Was ist ein CArchive-Objekt?

Ein `CArchive` Objekt lässt sich als typsicherer Pufferung für das Schreiben oder Lesen serialisierbare Objekte aus einer `CFile` Objekt. In der Regel die `CFile` Objekt darstellt, eine Datenträgerdatei, jedoch kann er auch einer Arbeitsspeicherdatei sein (`CSharedFile` Objekt), z. B., die Zwischenablage darstellt.

Ein angegebener `CArchive` Objekt entweder Speicher (schreibt, serialisiert) oder das Laden (liest, deserialisiert) Daten, aber nicht beides. Die Lebensdauer einer `CArchive` Objekt ist eine Pass-through-Objekte in eine Datei schreiben oder Lesen von Objekten aus einer Datei auf. Daher zwei nacheinander erstellt `CArchive` Objekte sind erforderlich, um Daten in eine Datei zu serialisieren und Deserialisieren Sie ihn anschließend aus der Datei zurück.

Wenn ein Archiv Objekte in einer Datei speichert, fügt das Archiv der `CRuntimeClass` Namen auf die Objekte. Dann, wenn ein weiteres Archiv Objekte aus einer Datei in den Speicher, lädt die `CObject`-abgeleitete Objekte sind dynamisch rekonstruiert basierend auf den `CRuntimeClass` der Objekte. Ein angegebenes Objekt kann mehr als einmal verwiesen werden, wie sie in der Datei durch das Speichern von Archiv geschrieben wird. Das Archiv laden, wird das Objekt jedoch nur einmal rekonstruieren. Die Informationen darüber, wie ein Archiv angefügt wird `CRuntimeClass` werden Informationen zu Objekten und rekonstruiert-Objekten berücksichtigt möglich mehrere Verweise in beschrieben [technischen Hinweis 2](../mfc/tn002-persistent-object-data-format.md).

Wie Daten in ein Archiv serialisiert sind, sammelt das Archiv die Daten, bis der Puffer voll ist. Dann das Archiv auf den Puffer in schreibt die `CFile` Objekt verweist die `CArchive` Objekt. Auf ähnliche Weise, wie Sie Daten aus einem Archiv lesen, liest er Daten aus der Datei in den Puffer, und klicken Sie dann aus dem Puffer in das deserialisierte Objekt. Diese Pufferung reduziert die Anzahl der Häufigkeit, mit die eine Festplatte physisch gelesen wird, die somit verbessern die Leistung Ihrer Anwendung.

## <a name="see-also"></a>Siehe auch

[Serialisierung: Serialisieren eines Objekts](../mfc/serialization-serializing-an-object.md)
