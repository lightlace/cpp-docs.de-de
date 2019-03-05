---
title: --Konstruktorenkommentar
ms.date: 11/04/2016
helpviewer_keywords:
- constructors comment
- declarations, constructors
- MFC source files, Constructors comment
- declaring constructors, code comments
- comments, MFC
- comments, constructors comment
- constructors [MFC], declaring
- instance constructors, code comments
ms.assetid: f400774e-ba85-49ed-85b7-70ef2f7dcb2b
ms.openlocfilehash: e0d02af016a0c7bfb0869b7cdd30fe0db2975102
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265807"
---
# <a name="-constructors-comment"></a>// Constructors-Kommentar

Die `// Constructors` Teil einer MFC-Klassendeklaration deklariert, Konstruktoren (in der C++-Sinne) als auch für Initialisierungsfunktionen erforderlich, um das Objekt wirklich verwenden. Z. B. `CWnd::Create` wird im Abschnitt Konstruktoren, da Sie vor der Verwendung der `CWnd` Objekt, es muss "vollständig konstruiert werden" von der C++-Konstruktor zuerst aufgerufen und dem anschließenden Aufrufen der `Create` Funktion. In der Regel sind diese Member öffentlich.

Z. B. Klasse `CStdioFile` hat drei Konstruktoren, von denen, in der Auflistung unter angezeigt wird [ein Beispiel für die Kommentare](../mfc/an-example-of-the-comments.md).

## <a name="see-also"></a>Siehe auch

[Verwenden der MFC-Quelldateien](../mfc/using-the-mfc-source-files.md)<br/>
[/ / Implementierungskommentar](../mfc/decrement-implementation-comment.md)<br/>
[Attributekommentar](../mfc/decrement-attributes-comment.md)<br/>
[Vorgänge-Kommentar](../mfc/decrement-operations-comment.md)<br/>
[/ / Overridables-Kommentar](../mfc/decrement-overridables-comment.md)
