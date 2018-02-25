---
title: 'IRowsetUpdateImpl:: Update | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::IRowsetUpdateImpl::Update
- IRowsetUpdateImpl::Update
- IRowsetUpdateImpl.Update
- ATL.IRowsetUpdateImpl.Update
dev_langs:
- C++
helpviewer_keywords:
- Update method
ms.assetid: 9ec6884d-aa9c-4871-a803-c048f162403c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b398bcc4d522fdb682778de1088c60c5b3ac63f3
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="irowsetupdateimplupdate"></a>IRowsetUpdateImpl::Update
Überträgt alle Änderungen, die auf die Zeile seit der letzten Fetch oder Update.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD (Update )(HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBCOUNTITEM* pcRows,  
   HROW** prgRows,  
   DBROWSTATUS** prgRowStatus);  
```  
  
#### <a name="parameters"></a>Parameter  
 `hReserved`  
 [in] Entspricht der `hChapter` im Parameters [IRowsetUpdate:: Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx).  
  
 Andere Parameter, finden Sie unter [IRowsetUpdate:: Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="remarks"></a>Hinweise  
 Änderungen werden durch den Aufruf übertragen [IRowsetChangeImpl:: FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md). Der Consumer muss Aufrufen [CRowset:: Update](../../data/oledb/crowset-update.md) für die Änderungen wirksam werden. Legen Sie *PrgRowstatus* auf einen geeigneten Wert wie beschrieben in [Zeilenzustände](https://msdn.microsoft.com/en-us/library/ms722752.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetUpdateImpl-Klasse](../../data/oledb/irowsetupdateimpl-class.md)