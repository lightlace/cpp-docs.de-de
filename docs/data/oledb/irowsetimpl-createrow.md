---
title: 'IRowsetImpl:: CreateRow | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: eae3fbdce1db5760d4ee5ca75e007c01e98b7bed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33103241"
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