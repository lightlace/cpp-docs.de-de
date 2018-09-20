---
title: --/ Constructors-Kommentar | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f03a65c3f870b1e7648f03b70efe7242c35a21f9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429356"
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

