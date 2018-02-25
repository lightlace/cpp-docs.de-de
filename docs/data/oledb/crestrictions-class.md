---
title: CRestrictions-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CRestrictions
- CRestrictions
- ATL.CRestrictions
dev_langs:
- C++
helpviewer_keywords:
- CRestrictions class
ms.assetid: 0aaa2364-641c-4318-b110-7446aada4b4f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8e68234f3a93cacf22c3abb0c4181a938b3f1dd6
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="crestrictions-class"></a>CRestrictions-Klasse
Eine generische Klasse, die Sie Einschränkungen für Schemarowsets angeben kann.  
  
## <a name="syntax"></a>Syntax

```cpp
template <class T, short nRestrictions, const GUID* pguid>  
class CRestrictions : 
        public CSchemaRowset <T, nRestrictions>  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse für den Accessor.  
  
 `nRestrictions`  
 Die Anzahl der Einschränkungsspalten für das Schemarowset.  
  
 `pguid`  
 Ein Zeiger auf die GUID für das Schema.  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[Öffnen](../../data/oledb/crestrictions-open.md)|Gibt ein Resultset entsprechend die benutzerdefinierte Einschränkungen.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbsch.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)