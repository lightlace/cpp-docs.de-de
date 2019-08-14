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
ms.openlocfilehash: 6f23f792f750e4352494bf3e4bde08f0fe360439
ms.sourcegitcommit: db1ed91fa7451ade91c3fb76bc7a2b857f8a5eef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2019
ms.locfileid: "68980488"
---
# <a name="using-the-mfc-source-files"></a>Verwenden der MFC-Quelldateien

Die MFC-Bibliothek (Microsoft Foundation Class) stellt vollständigen Quellcode bereit. Header Dateien (. h) befinden sich im Verzeichnis "\atlmfc\include". Implementierungs Dateien (cpp-Dateien) befinden sich im Verzeichnis \atlmfc\src\mfc.

In dieser Artikel Familie werden die Konventionen erläutert, die MFC verwendet, um die verschiedenen Teile der einzelnen Klassen zu kommentieren, was diese Kommentare bedeuten und was Sie in den einzelnen Abschnitten erwarten sollten. Die visuellen C++ Assistenten verwenden ähnliche Konventionen für die Klassen, die Sie für Sie erstellen, und Sie werden diese Konventionen wahrscheinlich für Ihren eigenen Code nützlich finden.

Möglicherweise sind Sie mit den Schlüsselwörtern **Public**, **Protected**und **private** C++ vertraut. In den MFC-Header Dateien werden Sie feststellen, dass jede Klasse mehrere davon aufweisen kann. Beispielsweise können öffentliche Element Variablen und-Funktionen unter mehr als einem **öffentlichen** Schlüsselwort liegen. Der Grund hierfür ist, dass MFC Element Variablen und-Funktionen abhängig von ihrer Verwendung trennt, nicht nach dem zulässigen Zugriffstyp. MFC verwendet **private** sparsam. Auch Elemente, die als Implementierungsdetails angesehen werden, sind häufig **geschützt**, und viele Male sind **öffentlich**. Obwohl der Zugriff auf die Implementierungsdetails nicht empfehlenswert ist, behält MFC die Entscheidung bei.

In den MFC-Quelldateien und den Header Dateien, die der MFC-Anwendungs-Assistent erstellt, finden Sie Kommentare wie diese innerhalb von Klassen Deklarationen (in der Regel in dieser Reihenfolge):

`// Constructors`

`// Attributes`

`// Operations`

`// Overridables`

`// Implementation`

Zu den in dieser Artikel Familie behandelten Themen gehören:

- [Ein Beispiel für die Kommentare](../mfc/an-example-of-the-comments.md)

- [Der//-Implementierungs Kommentar.](../mfc/decrement-implementation-comment.md)

- [Der//-konstruktorkommentar.](../mfc/decrement-constructors-comment.md)

- [Der//-Attribut Kommentar](../mfc/decrement-attributes-comment.md)

- [Der//Vorgangs Kommentar](../mfc/decrement-operations-comment.md)

- [Der//Overridables-Kommentar](../mfc/decrement-overridables-comment.md)

## <a name="see-also"></a>Siehe auch

[Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)
