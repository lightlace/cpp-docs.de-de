---
title: 'Irowsetidentityimpl:: Issamerow | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IsSameRow
- IRowsetIdentityImpl.IsSameRow
- ATL.IRowsetIdentityImpl.IsSameRow
- IRowsetIdentityImpl::IsSameRow
- ATL::IRowsetIdentityImpl::IsSameRow
dev_langs:
- C++
helpviewer_keywords:
- IsSameRow method
ms.assetid: e35ad54e-73f1-4dc0-8d8c-9e98202baf0a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 64422229b05867bcbf0a75e0c100b8428c9abd95
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="irowsetidentityimplissamerow"></a>IRowsetIdentityImpl::IsSameRow
Vergleicht zwei Zeilenhandles, um festzustellen, ob sie auf der gleichen Zeile verweisen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(IsSameRow )(HROW hThisRow,  
   HROW hThatRow);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IRowsetIdentity::IsSameRow](https://msdn.microsoft.com/en-us/library/ms719629.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="remarks"></a>Hinweise  
 Vergleich von Zeilenhandles wandelt diese Methode die **HROW** Fensterhandles zu **RowClass** Member und ruft `memcmp` für den Zeiger.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetIdentityImpl-Klasse](../../data/oledb/irowsetidentityimpl-class.md)