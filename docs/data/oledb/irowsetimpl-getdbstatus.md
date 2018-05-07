---
title: 'IRowsetImpl:: GetDBStatus | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- GetDBStatus
- IRowsetImpl.GetDBStatus
- IRowsetImpl::GetDBStatus
dev_langs:
- C++
helpviewer_keywords:
- GetDBStatus method
ms.assetid: e51d8ee2-fc0c-4909-861c-026c94fb0dfc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ebebbc2d1392e4f3c863ce366e8d19cfad3b7162
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetimplgetdbstatus"></a>IRowsetImpl::GetDBStatus
Gibt die `DBSTATUS` Statusflags für das angegebene Feld.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      virtual DBSTATUS GetDBStatus(RowClass* currentRow,  
   ATLCOLUMNINFO* columnNames);  
```  
  
#### <a name="parameters"></a>Parameter  
 [in] `currentRow`  
 Die aktuelle Zeile.  
  
 [in] `columnNames`  
 Die Spalte, deren Status angefordert wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Die [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) Flags für die Spalte.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetImpl-Klasse](../../data/oledb/irowsetimpl-class.md)