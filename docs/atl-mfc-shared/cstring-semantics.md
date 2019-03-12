---
title: CString-Semantik
ms.date: 11/04/2016
helpviewer_keywords:
- semantics in Cstring
- CString objects, assignment semantics
- assignment statements, assigning CString objects
ms.assetid: d4023480-526f-499a-85f6-324b4de5b85f
ms.openlocfilehash: b5398f8a0f17ffcc93c7f5f6158ecc56606e9279
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750180"
---
# <a name="cstring-semantics"></a>CString-Semantik

Obwohl [CString](../atl-mfc-shared/reference/cstringt-class.md) sind dynamische Objekte, die vergrößert werden können, sie verhalten sich wie die integrierten Grundtypen und einfache Klassen. Jede `CString` Objekt stellt einen eindeutigen Wert. `CString` Objekte sollten nicht als Zeiger auf Zeichenfolgen, sondern als tatsächlichen Zeichenfolgen betrachtet werden.

Sie können eine zuweisen `CString` zu einem anderen Objekt. Wenn Sie jedoch ändern, eine der beiden `CString` Objekte, die andere `CString` Objekt nicht geändert werden, wie im folgenden Beispiel gezeigt:

[!code-cpp[NVC_ATLMFC_Utilities#188](../atl-mfc-shared/codesnippet/cpp/cstring-semantics_1.cpp)]

Beachten Sie im Beispiel, das die beiden `CString` Objekte werden als "gleich" betrachtet, da sie die gleiche Zeichenfolge darstellen. Die `CString` Klasse Überladen des Gleichheitsoperators (`==`) zum Vergleichen zweier `CString` Objekte basierend auf ihrem Wert (Inhalt), anstatt ihre Identität (Adresse).

## <a name="see-also"></a>Siehe auch

[Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)
