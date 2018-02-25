---
title: 'IRowsetLocateImpl:: Getrowsbybookmark | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IRowsetLocateImpl::GetRowsByBookmark
- IRowsetLocateImpl.GetRowsByBookmark
- GetRowsByBookmark
dev_langs:
- C++
helpviewer_keywords:
- GetRowsByBookmark method
ms.assetid: 07906e42-3582-427e-812a-aa19791e3c56
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 68f546472e95147046b702a62be835ad64091d47
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="irowsetlocateimplgetrowsbybookmark"></a>IRowsetLocateImpl::GetRowsByBookmark
Ruft eine oder mehrere Zeilen, die die angegebenen Lesezeichen entsprechen ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD (GetRowsByBookmark )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const DBBKMARK rgcbBookmarks[],  
   const BYTE* rgpBookmarks,  
   HROW rghRows[],  
   DBROWSTATUS* rgRowStatus[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 `hReserved`  
 [in] Entspricht `hChapter` Parameter [IRowsetLocate:: Getrowsbybookmark](https://msdn.microsoft.com/en-us/library/ms725420.aspx).  
  
 Andere Parameter, finden Sie unter [IRowsetLocate:: Getrowsbybookmark](https://msdn.microsoft.com/en-us/library/ms725420.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="remarks"></a>Hinweise  
 Das Lesezeichen kann ein Wert, die Sie definieren oder einen OLE DB- [standard Lesezeichen](https://msdn.microsoft.com/en-us/library/ms712954.aspx) (**DBBMK_FIRST** oder **DBBMK_LAST**). Die Cursorposition wird nicht geändert werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetLocateImpl-Klasse](../../data/oledb/irowsetlocateimpl-class.md)   
 [IRowsetLocateImpl::GetRowsAt](../../data/oledb/irowsetlocateimpl-getrowsat.md)