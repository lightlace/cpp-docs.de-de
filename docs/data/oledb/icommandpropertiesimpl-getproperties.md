---
title: 'Icommandpropertiesimpl:: GetProperties | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandPropertiesImpl::GetProperties
- ICommandPropertiesImpl.GetProperties
- GetProperties
dev_langs:
- C++
helpviewer_keywords:
- GetProperties method
ms.assetid: 1bee5f1b-bd08-435a-956a-e4cebcdf5d5e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4a00cac292463251b89b314e7d4bd953480c505e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icommandpropertiesimplgetproperties"></a>ICommandPropertiesImpl::GetProperties
Gibt alle angeforderten Eigenschaftensätze, die mithilfe des Befehls eigenschaftenzuordnung zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(GetProperties)(const ULONG cPropertyIDSets,   
   const DBPROPIDSET rgPropertyIDSets[],   
   ULONG * pcPropertySets,   
   DBPROPSET ** prgPropertySets);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [ICommandProperties:: GetProperties](https://msdn.microsoft.com/en-us/library/ms723119.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="remarks"></a>Hinweise  
 Siehe [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [ICommandPropertiesImpl-Klasse](../../data/oledb/icommandpropertiesimpl-class.md)   
 [ICommandPropertiesImpl::SetProperties](../../data/oledb/icommandpropertiesimpl-setproperties.md)