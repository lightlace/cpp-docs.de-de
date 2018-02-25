---
title: 'Idbpropertiesimpl:: GetPropertyInfo | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IDBPropertiesImpl::GetPropertyInfo
- IDBPropertiesImpl.GetPropertyInfo
- GetPropertyInfo
dev_langs:
- C++
helpviewer_keywords:
- GetPropertyInfo method
ms.assetid: 170e9640-5010-4e0d-8a54-f50b23af08ad
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: aa96d49ae5a0ac01d90d6f6c5a0efe020d7a5a3e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="idbpropertiesimplgetpropertyinfo"></a>IDBPropertiesImpl::GetPropertyInfo
Gibt Eigenschafteninformationen, die von der Datenquelle unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(GetPropertyInfo)(ULONG cPropertySets,   
   const DBPROPIDSET rgPropertySets[],   
   ULONG * pcPropertyInfoSets,   
   DBPROPINFOSET ** prgPropertyInfoSets,   
   OLECHAR ** ppDescBuffer);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [GetPropertyInfo](https://msdn.microsoft.com/en-us/library/ms718175.aspx) in der *OLE DB Programmer's Reference*.  
  
 Einige Parameter entsprechen den *OLE DB Programmer's Reference* Parameter unterschiedliche Namen verwendet, die in beschriebenen **GetPropertyInfo**:  
  
|OLE DB-Vorlagenparameter|*OLE DB Programmer's Reference* Parameter|  
|--------------------------------|------------------------------------------------|  
|`cPropertySets`|`cPropertyIDSets`|  
|`rgPropertySets`|`rgPropertyIDSets`|  
  
## <a name="remarks"></a>Hinweise  
 Verwendet [idbinitializeimpl:: M_pcutlpropinfo](../../data/oledb/idbinitializeimpl-m-pcutlpropinfo.md) , diese Funktionalität zu implementieren.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IDBPropertiesImpl-Klasse](../../data/oledb/idbpropertiesimpl-class.md)   
 [IDBPropertiesImpl::GetProperties](../../data/oledb/idbpropertiesimpl-getproperties.md)   
 [IDBPropertiesImpl::SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)