---
title: 'IRowsetImpl:: RestartPosition | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetImpl.RestartPosition
- IRowsetImpl::RestartPosition
- RestartPosition
- ATL::IRowsetImpl::RestartPosition
- IRowsetImpl.RestartPosition
dev_langs:
- C++
helpviewer_keywords:
- RestartPosition method
ms.assetid: 14de66ef-8d2c-4404-adb6-3f6c74ac6cf1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1c203cc19e31f22df5903f099e953fcf5663718f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetimplrestartposition"></a>IRowsetImpl::RestartPosition
Positioniert die nächste Abrufposition auf seine anfängliche Position; erstellt, d. h. seine Position, die bei der Erstinstallation des Rowsets.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(RestartPosition )(HCHAPTER /* hReserved */);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IRowset:: RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="remarks"></a>Hinweise  
 Die Rowsetposition ist nicht definiert, bis **GetNextRow** aufgerufen wird. Sie können verschieben rückwärts in einem Rowet durch Aufrufen von `RestartPosition` , und klicken Sie dann Rückwärtsbildlauf oder-Abruf der Abwärtskompatibilität vorhanden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetImpl-Klasse](../../data/oledb/irowsetimpl-class.md)