---
title: --Attribute Kommentar | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- comments, Attributes
- Attributes comment in MFC source files
- MFC source files, Attributes comment
- public attributes comment
ms.assetid: 96388e11-42df-4994-aedf-decd152961a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 04288cb4482ad477d0ddf69f621afc0b12b3bf93
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46414848"
---
# <a name="-attributes-comment"></a>// Attributes-Kommentar

Die `// Attributes` Teil einer MFC-Klassendeklaration enthält den öffentlichen Attributen (oder Eigenschaften) des Objekts. In der Regel sind diese Membervariablen oder Get/Set-Funktionen. Die Funktionen "Get" und "Set" können, oder können nicht virtuell sein. Die "Get"-Funktionen sind in der Regel **const**, da in den meisten Fällen sie keine Nebeneffekte haben. Diese Elemente sind normalerweise public. geschützte und private Attribute werden in der Regel im Implementation-Abschnitt gefunden.

In diesem Beispiel aus der Klasse auflisten `CStdioFile`unter [ein Beispiel für die Kommentare](../mfc/an-example-of-the-comments.md), die Liste enthält eine Membervariable *M_pStream*. Klasse `CDC` enthält fast 20 Elemente unterhalb des Kommentars.

> [!NOTE]
>  Large-Klassen, z. B. `CDC` und `CWnd`, möglicherweise so viele Elemente, die einfach Auflisten aller Attribute in einer Gruppe keine Klarheit hinzufügen würden. In solchen Fällen werden die Klassenbibliothek Weitere Kommentare als Überschriften aus, um weitere Elemente voneinander abzugrenzen. Z. B. `CDC` verwendet `// Device-Context Functions`, `// Drawing Tool Functions`, `// Drawing Attribute Functions`, und vieles mehr. Gruppen, die Attribute darstellen, werden die übliche Syntax, die oben beschriebenen folgen. Viele OLE-Klassen haben einen Implementation-Abschnitt namens `// Interface Maps`.

## <a name="see-also"></a>Siehe auch

[Verwenden der MFC-Quelldateien](../mfc/using-the-mfc-source-files.md)<br/>
[Ein Beispiel für die Kommentare](../mfc/an-example-of-the-comments.md)<br/>
[/ / Implementierungskommentar](../mfc/decrement-implementation-comment.md)<br/>
[/ Constructors-Kommentar](../mfc/decrement-constructors-comment.md)<br/>
[Vorgänge-Kommentar](../mfc/decrement-operations-comment.md)<br/>
[/ / Overridables-Kommentar](../mfc/decrement-overridables-comment.md)

