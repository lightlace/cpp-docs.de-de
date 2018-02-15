---
title: CEnumeratorAccessor-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CEnumeratorAccessor
- CEnumeratorAccessor
- ATL.CEnumeratorAccessor
dev_langs:
- C++
helpviewer_keywords:
- CEnumeratorAccessor class
ms.assetid: 21e8e7ea-3511-4afe-b33f-d520f4ff82bb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 57595cb2440aa8ad83c7cc0ad6916b3f22d6fb37
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
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