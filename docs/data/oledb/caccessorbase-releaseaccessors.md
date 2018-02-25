---
title: 'CAccessorBase:: Releaseaccessors | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAccessorBase::ReleaseAccessors
- CAccessorBase.ReleaseAccessors
- ReleaseAccessors
dev_langs:
- C++
helpviewer_keywords:
- ReleaseAccessors method
ms.assetid: f08bc88e-0552-4a9c-9c65-b4061094649a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e68556f39d256cd0173ec24d7a2310076b6eca42
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="caccessorbasereleaseaccessors"></a>CAccessorBase::ReleaseAccessors
Gibt die Accessoren erstellt, die von der Klasse frei.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT ReleaseAccessors(IUnknown* pUnk);  
```  
  
#### <a name="parameters"></a>Parameter  
 *pUnk*  
 [in] Ein Zeiger auf ein **IUnknown** Schnittstelle für das COM-Objekt, das für die Accessoren erstellt wurden.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Aufgerufen von [CAccessorRowset:: Close](../../data/oledb/caccessorrowset-close.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CAccessorBase-Klasse](../../data/oledb/caccessorbase-class.md)