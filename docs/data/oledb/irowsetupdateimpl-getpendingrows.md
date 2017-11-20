---
title: 'IRowsetUpdateImpl:: Getpendingrows | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetUpdateImpl::GetPendingRows
- GetPendingRows
- IRowsetUpdateImpl.GetPendingRows
- ATL::IRowsetUpdateImpl::GetPendingRows
- ATL.IRowsetUpdateImpl.GetPendingRows
dev_langs: C++
helpviewer_keywords: GetPendingRows method
ms.assetid: 2d1ef748-da6d-4184-98dc-096427358dfd
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0ee25e0e67ecb90178e1df1c54ac6db1fb718cbe
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetupdateimplgetpendingrows"></a>IRowsetUpdateImpl::GetPendingRows
Gibt eine Liste der Zeilen mit ausstehenden Änderungen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      STDMETHOD ( GetPendingRows )(  
   HCHAPTER /* hReserved */,  
   DBPENDINGSTATUS dwRowStatus,  
   DBCOUNTITEM* pcPendingRows,  
   HROW** prgPendingRows,  
   DBPENDINGSTATUS** prgPendingStatus   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `hReserved`  
 [in] Entspricht der `hChapter` im Parameters [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/en-us/library/ms719626.aspx).  
  
 Andere Parameter, finden Sie unter [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/en-us/library/ms719626.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie unter [IRowsetUpdate::GetPendingRows](https://msdn.microsoft.com/en-us/library/ms719626.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetUpdateImpl-Klasse](../../data/oledb/irowsetupdateimpl-class.md)