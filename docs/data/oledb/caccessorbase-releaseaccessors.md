---
title: 'CAccessorBase:: Releaseaccessors | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1c73035e27b1f896891630cd9b4d9a135b3c4758
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
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