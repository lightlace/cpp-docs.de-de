---
title: 'CBulkRowset:: setRows | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CBulkRowset.SetRows
- CBulkRowset::SetRows
- CBulkRowset<TAccessor>.SetRows
- ATL.CBulkRowset<TAccessor>.SetRows
- CBulkRowset<TAccessor>::SetRows
- ATL::CBulkRowset<TAccessor>::SetRows
- ATL::CBulkRowset::SetRows
- CBulkRowset.SetRows
- SetRows
dev_langs:
- C++
helpviewer_keywords:
- SetRows method
ms.assetid: 7e92312a-bfd0-4c24-a799-62bef663f28e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1519c0113744bb3c1e03bec52d5504ce504ee719
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cbulkrowsetsetrows"></a>CBulkRowset::SetRows
Legt die Anzahl von Zeilenhandles, die von jedem Aufruf abgerufen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      void SetRows(DBROWCOUNT nRows) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `nRows`  
 [in] Die neue Größe des Rowsets (Anzahl von Zeilen).  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie diese Funktion aufrufen, muss es sein, bevor das Rowset geöffnet wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CBulkRowset-Klasse](../../data/oledb/cbulkrowset-class.md)