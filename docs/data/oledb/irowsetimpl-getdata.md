---
title: 'IRowsetImpl:: | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.IRowsetImpl.GetData
- ATL::IRowsetImpl::GetData
- IRowsetImpl::GetData
- IRowsetImpl.GetData
dev_langs:
- C++
helpviewer_keywords:
- GetData method [OLE DB]
ms.assetid: cb15f1cc-bd25-4b74-93c3-db71aa93829c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 64bc8d6b84195aef8fd9dc3b0093221cc8e057d7
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="irowsetimplgetdata"></a>IRowsetImpl::GetData
Ruft Daten aus dem Rowset Kopie der Zeile ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(GetData )(HROW hRow,  
   HACCESSOR hAccessor,  
   void* pDstData);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IRowset:: GetData](https://msdn.microsoft.com/en-us/library/ms716988.aspx) in der *OLE DB Programmer's Reference*.  
  
 Einige Parameter entsprechen den *OLE DB Programmer's Reference* Parameter unterschiedliche Namen verwendet, die in beschriebenen **IRowset:: GetData**:  
  
|OLE DB-Vorlagenparameter|*OLE DB Programmer's Reference* Parameter|  
|--------------------------------|------------------------------------------------|  
|*pDstData*|`pData`|  
  
## <a name="remarks"></a>Hinweise  
 Behandelt auch Datenkonvertierung bei Verwenden der OLE DB-Datenkonvertierung DLL.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetImpl-Klasse](../../data/oledb/irowsetimpl-class.md)