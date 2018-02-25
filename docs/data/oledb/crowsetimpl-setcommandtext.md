---
title: 'CRowsetImpl:: SetCommandText | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRowsetImpl.SetCommandText
- CRowsetImpl::SetCommandText
dev_langs:
- C++
helpviewer_keywords:
- SetCommandText method
ms.assetid: e016d7df-c1a0-4dee-b19b-c876680221fd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e345799f74d4c32ffae88baebb69ed828266dcfc
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="crowsetimplsetcommandtext"></a>CRowsetImpl::SetCommandText
Überprüft, und speichert die **DBID**s in den beiden Zeichenfolgen ([M_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) und [M_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)).  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT CRowsetBaseImpl::SetCommandText(DBID* pTableID,  
   DBID* pIndexID);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pTableID`  
 [in] Ein Zeiger auf die **DBID** , die ID der Tabelle darstellt.  
  
 `pIndexID`  
 [in] Ein Zeiger auf die **DBID** , die Index-ID darstellt.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Die **SetCommentText** Methode wird aufgerufen, indem `CreateRowset`, ein statischen vorlagenbasiert Methode `IOpenRowsetImpl`.  
  
 Diese Methode delegiert die Arbeit durch Aufrufen von [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) und [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md) über einen upcasted Zeiger.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [CRowsetImpl-Klasse](../../data/oledb/crowsetimpl-class.md)