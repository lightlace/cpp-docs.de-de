---
title: CString-Semantik | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- semantics in Cstring
- CString objects, assignment semantics
- assignment statements, assigning CString objects
ms.assetid: d4023480-526f-499a-85f6-324b4de5b85f
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 394e459a46003e3f1baccff7dd4c76f40b73e354
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cstring-semantics"></a>CString-Semantik
Obwohl [CString](../atl-mfc-shared/reference/cstringt-class.md) Objekte sind dynamische Objekte, die erweitert werden können, sie fungiert als einfache Klassen und integrierten primitiven Typen. Jede `CString` -Objekt stellt einen eindeutigen Wert dar. `CString`Objekte sollten nicht als Zeiger auf Zeichenfolgen, sondern als tatsächlichen Zeichenfolgen betrachtet werden.  
  
 Sie können eine zuweisen **CString** zu einem anderen Objekt. Wenn Sie jedoch ändern, einen der beiden `CString` Objekte, die andere `CString` -Objekt nicht geändert wird, wie im folgenden Beispiel gezeigt:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#188](../atl-mfc-shared/codesnippet/cpp/cstring-semantics_1.cpp)]  
  
 Beachten Sie im Beispiel, das die beiden `CString` Objekte werden als "gleich" betrachtet, da sie die gleiche Zeichenfolge darstellen. Die `CString` Klasse Überladen des Gleichheitsoperators (`==`) zum Vergleichen zweier `CString` Objekte basierend auf ihren Wert (Inhalt) statt ihre Identität (Adresse).  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)

