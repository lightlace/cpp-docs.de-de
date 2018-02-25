---
title: 'IRowsetImpl:: Refrows | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::IRowsetImpl::RefRows
- ATL.IRowsetImpl.RefRows
- IRowsetImpl.RefRows
- RefRows
- IRowsetImpl::RefRows
dev_langs:
- C++
helpviewer_keywords:
- RefRows method
ms.assetid: 1c048a2a-65dc-4bba-9c81-a23c0dc249c8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: db2ae7e068f3c253e546274dbdfe693889a06504
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="irowsetimplrefrows"></a>IRowsetImpl::RefRows
Wird aufgerufen, indem [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) und [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md) erhöhen, oder einen Verweiszähler für eine vorhandene Zeilenhandle freigeben.  
  
## <a name="syntax"></a>Syntax  
  
```
HRESULT RefRows(DBCOUNTITEM cRows,  
   const HROWrghRows[],  
   DBREFCOUNT rgRefCounts[],  
   DBROWSTATUS rgRowStatus[],  
   BOOL bAdd);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IRowset::AddRefRows](https://msdn.microsoft.com/en-us/library/ms719619.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetImpl-Klasse](../../data/oledb/irowsetimpl-class.md)   
 [CSimpleRow-Klasse](../../data/oledb/csimplerow-class.md)