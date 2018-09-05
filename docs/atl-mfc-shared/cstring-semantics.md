---
title: CString-Semantik | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- semantics in Cstring
- CString objects, assignment semantics
- assignment statements, assigning CString objects
ms.assetid: d4023480-526f-499a-85f6-324b4de5b85f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 256c71cace15a3906ac048819ab2ffdef2071ff4
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43761272"
---
# <a name="cstring-semantics"></a>CString-Semantik

Obwohl [CString](../atl-mfc-shared/reference/cstringt-class.md) sind dynamische Objekte, die vergrößert werden können, sie verhalten sich wie die integrierten Grundtypen und einfache Klassen. Jede `CString` Objekt stellt einen eindeutigen Wert. `CString` Objekte sollten nicht als Zeiger auf Zeichenfolgen, sondern als tatsächlichen Zeichenfolgen betrachtet werden.

Sie können eine zuweisen `CString` zu einem anderen Objekt. Wenn Sie jedoch ändern, eine der beiden `CString` Objekte, die andere `CString` Objekt nicht geändert werden, wie im folgenden Beispiel gezeigt:

[!code-cpp[NVC_ATLMFC_Utilities#188](../atl-mfc-shared/codesnippet/cpp/cstring-semantics_1.cpp)]

Beachten Sie im Beispiel, das die beiden `CString` Objekte werden als "gleich" betrachtet, da sie die gleiche Zeichenfolge darstellen. Die `CString` Klasse Überladen des Gleichheitsoperators (`==`) zum Vergleichen zweier `CString` Objekte basierend auf ihrem Wert (Inhalt), anstatt ihre Identität (Adresse).

## <a name="see-also"></a>Siehe auch

[Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)

