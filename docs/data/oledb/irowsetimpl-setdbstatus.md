---
title: 'IRowsetImpl:: SetDBStatus | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetImpl.SetDBStatus
- IRowsetImpl::SetDBStatus
- SetDBStatus
dev_langs:
- C++
helpviewer_keywords:
- SetDBStatus method
ms.assetid: b73f526a-4fc6-4adb-9611-c3cca2cddb23
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7e6e07b6fe1a45a779c5ffe1e1afffaabdcb6d34
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33103901"
---
# <a name="irowsetimplsetdbstatus"></a>IRowsetImpl::SetDBStatus
Legt die `DBSTATUS` Statusflags für das angegebene Feld.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      virtual HRESULT SetDBStatus(DBSTATUS* statusFlags,  
   RowClass* currentRow,  
   ATLCOLUMNINFO* columnInfo);  
```  
  
#### <a name="parameters"></a>Parameter  
 `statusFlags`  
 Die [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) Flags für die Spalte festlegen.  
  
 `currentRow`  
 Die aktuelle Zeile.  
  
 *columnInfo*  
 Die Spalte, deren Status festgelegt wird.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert.  
  
## <a name="remarks"></a>Hinweise  
 Der Anbieter, überschreibt dieser Funktion können Sie spezielle Verarbeitungsschritte für **DBSTATUS_S_ISNULL** und **DBSTATUS_S_DEFAULT**.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetImpl-Klasse](../../data/oledb/irowsetimpl-class.md)