---
title: 'IRowsetImpl:: SetDBStatus | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bcc7895e7f52022905b23d71ef670eb19f2e836e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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