---
title: 'CRowset:: Issamerow | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRowset::IsSameRow
- CRowset.IsSameRow
- IsSameRow
- ATL::CRowset::IsSameRow
- ATL.CRowset.IsSameRow
- CRowset<TAccessor>::IsSameRow
- ATL.CRowset<TAccessor>.IsSameRow
- CRowset<TAccessor>.IsSameRow
- ATL::CRowset<TAccessor>::IsSameRow
dev_langs:
- C++
helpviewer_keywords:
- IsSameRow method
ms.assetid: 53cba847-52f5-4dd9-973f-bbe7454c425c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b43788e1c64df3db223aa02df53014d3871b4c71
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetissamerow"></a>CRowset::IsSameRow
Vergleicht die angegebene Zeile mit der aktuellen Zeile.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT IsSameRow(HROW hRow) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `hRow`  
 [in] Ein Handle für die Zeile, auf die aktuelle Zeile verglichen werden soll.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt. `S_OK` Gibt an, dass die Zeilen identisch sind. Weitere Werte finden Sie unter [IRowsetIndentity::IsSameRow](https://msdn.microsoft.com/en-us/library/ms719629.aspx) in der *OLE DB Programmer's Reference* im Windows SDK.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRowset-Klasse](../../data/oledb/crowset-class.md)