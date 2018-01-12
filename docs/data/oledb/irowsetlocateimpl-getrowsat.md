---
title: 'IRowsetLocateImpl:: GetRowsAt | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetRowsAt
- IRowsetLocateImpl.GetRowsAt
- ATL::IRowsetLocateImpl::GetRowsAt
- IRowsetLocateImpl::GetRowsAt
- ATL.IRowsetLocateImpl.GetRowsAt
dev_langs: C++
helpviewer_keywords: GetRowsAt method
ms.assetid: 6aeb09dc-3aa8-4729-97a8-144dd27063f7
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a757c6102851851ab4175f939a6f76d8136fa61c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetlocateimplgetrowsat"></a>IRowsetLocateImpl::GetRowsAt
Ruft Zeilen ab der Zeile, in einem Lesezeichen als Offset angegeben ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      STDMETHOD ( GetRowsAt )(  
   HWATCHREGION /* hReserved1 */,  
   HCHAPTER hReserved2,  
   DBBKMARK cbBookmark,  
   const BYTE* pBookmark,  
   DBROWOFFSET lRowsOffset,  
   DBROWCOUNT cRows,  
   DBCOUNTITEM* pcRowsObtained,  
   HROW** prghRows   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IRowsetLocate:: GetRowsAt](https://msdn.microsoft.com/en-us/library/ms723031.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="remarks"></a>Hinweise  
 Um stattdessen von der Cursorposition bis abzurufen, verwenden Sie [IRowset::GetRowsAt](https://msdn.microsoft.com/en-us/library/ms723031.aspx).  
  
 `IRowsetLocateImpl::GetRowsAt`die Cursorposition wird nicht geändert werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetLocateImpl-Klasse](../../data/oledb/irowsetlocateimpl-class.md)   
 [IRowsetLocateImpl::GetRowsByBookmark](../../data/oledb/irowsetlocateimpl-getrowsbybookmark.md)