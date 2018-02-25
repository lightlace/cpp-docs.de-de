---
title: IRowsetLocateImpl::Hash | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IRowsetLocateImpl::Hash
- IRowsetLocateImpl.Hash
dev_langs:
- C++
helpviewer_keywords:
- Hash method
ms.assetid: 7df4386d-80fb-4332-a85f-baae98cdc6e0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 321f10dd0f6b25441b1dc78fa660ff2aa66b3d36
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="irowsetlocateimplhash"></a>IRowsetLocateImpl::Hash
Gibt Hashing Werte für die angegebene Lesezeichen ausführen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD (Hash )(HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmarks,  
   const DBBKMARK* rgcbBookmarks[],  
   const BYTE* rgpBookmarks[],  
   DBHASHVALUE rgHashValues[],  
   DBROWSTATUS rgBookmarkStatus[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 `hReserved`  
 [in] Entspricht `hChapter` Parameter [IRowsetLocate::Hash](https://msdn.microsoft.com/en-us/library/ms709697.aspx).  
  
 Andere Parameter, finden Sie unter [IRowsetLocate::Hash](https://msdn.microsoft.com/en-us/library/ms709697.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetLocateImpl-Klasse](../../data/oledb/irowsetlocateimpl-class.md)