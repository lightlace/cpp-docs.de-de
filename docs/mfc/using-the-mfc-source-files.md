---
title: Verwenden der MFC-Quelldateien
ms.date: 11/04/2016
helpviewer_keywords:
- public members
- source files
- MFC, source files
- MFC source files
- comments, MFC
- private member access
- protected member access
- source files, MFC
ms.assetid: 3230e8fb-3b69-4ddf-9538-365ac7ea5e72
ms.openlocfilehash: 40decb64914167061f6538df36d086347f52e1b6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659289"
---
# <a name="using-the-mfc-source-files"></a>Verwenden der MFC-Quelldateien

Die Microsoft Foundation Class (MFC)-Bibliothek stellt der vollständige Quellcode bereit. Headerdateien (. h) befinden sich im Verzeichnis \atlmfc\include; Implementierungsdateien (.cpp) befinden sich im Verzeichnis \atlmfc\src\mfc.

In dieser Artikelreihe wird erläutert, die Konventionen, die MFC verwendet, um das Kommentieren von den verschiedenen Teilen der einzelnen Klassen, was bedeutet, dass diese Kommentare und was Sie erwarten sollten, finden Sie in den einzelnen Abschnitten. Die Visual C++-Assistenten verwenden ähnliche Konventionen für die Klassen, die sie für Sie erstellen, und wahrscheinlich finden Sie diese Konventionen nützlich für Ihren eigenen Code.

Möglicherweise kennen Sie die **öffentliche**, **geschützt**, und **private** C++-Schlüsselwörter. Bei Betrachtung der MFC-Headerdateien werden Sie feststellen, dass jede Klasse, die mehrere dieser verfügen kann. Z. B. öffentliche Member-Variablen und Funktionen möglicherweise unter mehr als einem **öffentliche** Schlüsselwort. Dies ist da MFC Membervariablen und Funktionen, die auf der Grundlage ihrer Verwendung, nicht durch den Typ der Zugriff gewährt trennt. MFC verwendet **private** sparsam; auch Elemente berücksichtigt, Implementierungsdetails sind im Allgemeinen geschützt und oft öffentlich sind. Obwohl der Zugriff auf die Details der Implementierung wird nicht empfohlen, verlässt MFC die Entscheidung für Sie.

In der MFC-Quelldateien und die Dateien, die die MFC-Anwendungs-Assistent erstellt, finden Sie Kommentare, wie diese innerhalb von Klassendeklarationen (in der Regel in dieser Reihenfolge):

`// Constructors`

`// Attributes`

`// Operations`

`// Overridables`

`// Implementation`

In dieser Artikelreihe behandelten Themen gehören:

- [Ein Beispiel für die Kommentare](../mfc/an-example-of-the-comments.md)

- [Die / / Implementierung Kommentar](../mfc/decrement-implementation-comment.md)

- [Die / / konstruktorenkommentar](../mfc/decrement-constructors-comment.md)

- [Die / / Attributes-Kommentar](../mfc/decrement-attributes-comment.md)

- [Die / / Operations-Kommentar](../mfc/decrement-operations-comment.md)

- [Die / / / / Overridables-Kommentar](../mfc/decrement-overridables-comment.md)

## <a name="see-also"></a>Siehe auch

[Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)

