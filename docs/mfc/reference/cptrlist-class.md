---
title: CPtrList Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPtrList
dev_langs:
- C++
helpviewer_keywords:
- lists, generic
- CPtrList class [MFC]
- generic lists
ms.assetid: 4139a09c-4338-4f42-9eea-51336120b43c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a143fd99a79212ed0078f06b334ab6ae0964b3f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33370239"
---
# <a name="cptrlist-class"></a>CPtrList-Klasse
Unterstützt Listen void-Zeigern.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPtrList : public CObject  
```  
  
## <a name="members"></a>Member  
 Die Memberfunktionen von `CPtrList` ähneln den Memberfunktionen der Klasse [CObList](../../mfc/reference/coblist-class.md). Aufgrund dieser Ähnlichkeit können Sie die `CObList`-Referenzdokumentation für Memberfunktionsbesonderheiten verwenden. Wenn Sie einen `CObject`-Zeiger als Funktionsparameter oder als Rückgabewert finden, ersetzen Sie einen Zeiger auf `void`.  
  
 `CObject*& CObList::GetHead() const;`  
  
 Beispielsweise übersetzt zu  
  
 `void*& CPtrList::GetHead() const;`  
  
## <a name="remarks"></a>Hinweise  
 `CPtrList` enthält das `IMPLEMENT_DYNAMIC`-Makro zur Unterstützung von Laufzeittypenzugriff und zum Sichern in ein `CDumpContext`-Objekt. Wenn Sie eine Sicherung einzelner Zeigerlistenelemente benötigen, müssen Sie die Tiefe des Sicherungskontexts auf 1 oder größer festlegen.  
  
 Zeigerlisten können nicht serialisiert werden.  
  
 Wenn ein `CPtrList`-Objekt gelöscht wird oder dessen Elemente entfernt werden, werden nur die Zeiger, und nicht die Entitäten, auf die sie verweisen, entfernt.  
  
 Weitere Informationen zur Verwendung von `CPtrList`, finden Sie im Artikel [Sammlungen](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CPtrList`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcoll.h  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CObList-Klasse](../../mfc/reference/coblist-class.md)
