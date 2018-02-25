---
title: CArrayRowset-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CArrayRowset<TAccessor>
- ATL.CArrayRowset
- CArrayRowset
- ATL::CArrayRowset
- ATL::CArrayRowset<TAccessor>
dev_langs:
- C++
helpviewer_keywords:
- CArrayRowset class
ms.assetid: 511427e1-73ca-4fd8-9ba1-ae9463557cb6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 28d3a28f5c00cb0231738e8f02f07318bf156921
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="carrayrowset-class"></a>CArrayRowset-Klasse
Greift auf die Elemente eines Rowsets mit Arraysyntax.  
  
## <a name="syntax"></a>Syntax

```cpp
template < class TAccessor >  
class CArrayRowset :   
   public CVirtualBuffer <TAccessor>,   
   protected CBulkRowset <TAccessor>  
```  
  
#### <a name="parameters"></a>Parameter  
 `TAccessor`  
 Der Typ der Accessorklasse, die das Rowset verwendet werden soll.  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[CArrayRowset](../../data/oledb/carrayrowset-carrayrowset.md)|Konstruktor.|  
|[Snapshot](../../data/oledb/carrayrowset-snapshot.md)|Liest das gesamte Rowset in den Speicher.|  
  
### <a name="operators"></a>Operatoren  
  
|||  
|-|-|  
|[Operator &#91; &#93;](../../data/oledb/carrayrowset-operator.md)|Greift auf ein Element des Rowsets.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|[CArrayRowset::m_nRowsRead](../../data/oledb/carrayrowset-m-nrowsread.md)|Die Anzahl der Zeilen, die bereits gelesen.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB-Consumer-Vorlagenreferenz](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CRowset-Klasse](../../data/oledb/crowset-class.md)