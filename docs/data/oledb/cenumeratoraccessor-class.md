---
title: CEnumeratorAccessor-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CEnumeratorAccessor
- CEnumeratorAccessor
- ATL.CEnumeratorAccessor
dev_langs:
- C++
helpviewer_keywords:
- CEnumeratorAccessor class
ms.assetid: 21e8e7ea-3511-4afe-b33f-d520f4ff82bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bb071f47eb7079c8de63da47ee0d837f44442c1a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33097240"
---
# <a name="cenumeratoraccessor-class"></a>CEnumeratorAccessor-Klasse
Verwendet von [CEnumerator](../../data/oledb/cenumerator-class.md) für den Datenzugriff aus dem Enumerator-Rowset.  
  
## <a name="syntax"></a>Syntax

```cpp
class CEnumeratorAccessor  
```  
  
## <a name="members"></a>Member  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[m_bIsParent](../../data/oledb/cenumeratoraccessor-m-bisparent.md)|Eine Variable, der angibt, ob der Enumerator eine übergeordnete Enumerator ist die Zeile ist ein Enumerator.|  
|[m_nType](../../data/oledb/cenumeratoraccessor-m-ntype.md)|Eine Variable, der angibt, ob die Zeile eine Datenquelle oder einen Enumerator beschreibt.|  
|[m_szDescription](../../data/oledb/cenumeratoraccessor-m-szdescription.md)|Die Beschreibung der Datenquelle oder Enumerator.|  
|[m_szName](../../data/oledb/cenumeratoraccessor-m-szname.md)|Der Name der Datenquelle oder Enumerator.|  
|[m_szParseName](../../data/oledb/cenumeratoraccessor-m-szparsename.md)|Zeichenfolge zu übergeben [IParseDisplayName](http://msdn.microsoft.com/library/windows/desktop/ms680604) zum Abrufen eines Monikers für die Datenquelle oder eines Enumerators.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Rowset besteht aus den Datenquellen und Enumeratoren, die aus dem aktuellen Enumerator sichtbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)