---
title: 'IRowsetImpl:: M_bcanfetchback | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetImpl.m_bCanFetchBack
- ATL::IRowsetImpl::m_bCanFetchBack
- IRowsetImpl.m_bCanFetchBack
- IRowsetImpl::m_bCanFetchBack
- m_bCanFetchBack
dev_langs:
- C++
helpviewer_keywords:
- m_bCanFetchBack
ms.assetid: cfa007b0-7ba5-48a3-9d05-9f1916305fb7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bf194fc7d7547cf03194f4dd5bedf014c9101b0a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetimplmbcanfetchback"></a>IRowsetImpl::m_bCanFetchBack
Gibt an, ob ein Anbieter rückwärts abrufen unterstützt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
unsigned m_bCanFetchBack:1;  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Verknüpft die **DBPROP_CANFETCHBACKWARDS** Eigenschaft in der **DBPROPSET_ROWSET** Gruppe. Der Anbieter muss unterstützen **DBPROP_CANFETCHBACKWARDS** für **M_bCanFetchBackwards** auf "true" sein.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetImpl-Klasse](../../data/oledb/irowsetimpl-class.md)   
 [IRowsetImpl::m_bCanScrollBack](../../data/oledb/irowsetimpl-m-bcanscrollback.md)