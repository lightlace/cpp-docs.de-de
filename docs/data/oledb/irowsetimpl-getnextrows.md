---
title: 'IRowsetImpl:: GetNextRows | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- GetNextRows
- ATL.IRowsetImpl.GetNextRows
- ATL::IRowsetImpl::GetNextRows
- IRowsetImpl::GetNextRows
- IRowsetImpl.GetNextRows
dev_langs:
- C++
helpviewer_keywords:
- GetNextRows method
ms.assetid: 1c0975d6-d770-4884-830b-6986c6fa8e65
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fee6e2a1b6b7111d193f4a22c9d70bd0beb5df37
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="irowsetimplgetnextrows"></a>IRowsetImpl::GetNextRows
Ruft Zeilen ab sequenziell, zum Speichern der vorherigen Position.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(GetNextRows )(HCHAPTER hReserved,  
   DBROWOFFSET lRowsOffset,  
   DBROWCOUNT cRows,  
   DBCOUNTITEM* pcRowsObtained,  
   HROW** prghRows);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IRowset:: GetNextRows](https://msdn.microsoft.com/en-us/library/ms709827.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetImpl-Klasse](../../data/oledb/irowsetimpl-class.md)   
 [IRowsetImpl::AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md)   
 [IRowsetImpl::ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md)