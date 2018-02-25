---
title: 'IRowsetImpl:: CreateRow | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IRowsetImpl.CreateRow
- ATL.IRowsetImpl.CreateRow
- ATL::IRowsetImpl::CreateRow
- CreateRow
- IRowsetImpl::CreateRow
dev_langs:
- C++
helpviewer_keywords:
- CreateRow method
ms.assetid: b01c430c-9484-4fef-a6cf-a2e8d9d99130
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fd378ed599795911a86fb4bc10625721c76f417b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="irowsetimplcreaterow"></a>IRowsetImpl::CreateRow
Eine Hilfsmethode wird aufgerufen, indem [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) Zuweisen einer neuen **HROW**.  
  
## <a name="syntax"></a>Syntax  
  
```
HRESULT CreateRow(DBROWOFFSET lRowsOffset,  
  DBCOUNTITEM& cRowsObtained,  
   HROW* rgRows);  
```  
  
#### <a name="parameters"></a>Parameter  
 *lRowsOffset*  
 Cursorposition der Zeile erstellt wird.  
  
 *cRowsObtained*  
 Ein Verweis übergeben zurück an den Benutzer, der angibt, der Anzahl der Zeilen, die erstellt werden.  
  
 *rgRows*  
 Ein Array von **HROW**s an den Aufrufer mit den neu erstellten Zeilenhandles zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Zeile vorhanden ist, ruft diese Methode [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) und zurückgibt. Andernfalls weist eine neue Instanz der Vorlagenvariable RowClass und fügt es [M_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetImpl-Klasse](../../data/oledb/irowsetimpl-class.md)