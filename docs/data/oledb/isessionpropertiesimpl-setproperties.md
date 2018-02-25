---
title: 'Isessionpropertiesimpl:: SetProperties | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ISessionPropertiesImpl.SetProperties
- SetProperties
- ISessionPropertiesImpl::SetProperties
dev_langs:
- C++
helpviewer_keywords:
- SetProperties method
ms.assetid: 2e1219ed-0e1e-460e-84d6-031acfbfd3d2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 91de7025ab5c976a7dabaa029aaa23e732b906b5
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="isessionpropertiesimplsetproperties"></a>ISessionPropertiesImpl::SetProperties
Legt Eigenschaften fest, der **DBPROPSET_SESSION** Eigenschaftengruppe.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(SetProperties)(ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [ISessionProperties::SetProperties](https://msdn.microsoft.com/en-us/library/ms714405.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [ISessionPropertiesImpl-Klasse](../../data/oledb/isessionpropertiesimpl-class.md)   
 [ISessionPropertiesImpl::GetProperties](../../data/oledb/isessionpropertiesimpl-getproperties.md)