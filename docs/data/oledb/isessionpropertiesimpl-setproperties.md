---
title: 'Isessionpropertiesimpl:: SetProperties | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ISessionPropertiesImpl.SetProperties
- SetProperties
- ISessionPropertiesImpl::SetProperties
dev_langs: C++
helpviewer_keywords: SetProperties method
ms.assetid: 2e1219ed-0e1e-460e-84d6-031acfbfd3d2
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2833613789a67219eddaff57b7b6de54fce7f880
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="isessionpropertiesimplsetproperties"></a>ISessionPropertiesImpl::SetProperties
Legt Eigenschaften fest, der **DBPROPSET_SESSION** Eigenschaftengruppe.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      STDMETHOD(SetProperties)(   
   ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]    
);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [ISessionProperties::SetProperties](https://msdn.microsoft.com/en-us/library/ms714405.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [ISessionPropertiesImpl-Klasse](../../data/oledb/isessionpropertiesimpl-class.md)   
 [ISessionPropertiesImpl::GetProperties](../../data/oledb/isessionpropertiesimpl-getproperties.md)