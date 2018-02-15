---
title: 'IRowsetUpdateImpl:: IsUpdateAllowed | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetUpdateImpl::IsUpdateAllowed
- IRowsetUpdateImpl.IsUpdateAllowed
- IsUpdateAllowed
dev_langs:
- C++
helpviewer_keywords:
- IsUpdateAllowed method
ms.assetid: d6daf3b3-a8e0-4275-a67d-897dea01e297
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4744e6f5be9c9b535c7359b615a5195c6da33fd9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="irowsetupdateimplisupdateallowed"></a>IRowsetUpdateImpl::IsUpdateAllowed
Überschreiben Sie diese Methode, um für Sicherheit, Integrität und so weiter vor Updates zu überprüfen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT IsUpdateAllowed(DBPENDINGSTATUS /* [in] *//* status */,  
   HROW /* [in] *//* hRowUpdate */,  
   DBROWSTATUS* /* [out] *//* pRowStatus */);  
```  
  
#### <a name="parameters"></a>Parameter  
 *status*  
 [in] Der Status der ausstehenden Vorgänge auf die Zeilen.  
  
 *hRowUpdate*  
 [in] Handle für die Zeilen, die der Benutzer aktualisieren möchte.  
  
 *pRowStatus*  
 [out] Der Status an den Benutzer zurückgegeben.  
  
## <a name="remarks"></a>Hinweise  
 Gibt zurück, wenn Sie feststellen, dass ein Update zugelassen werden sollen, `S_OK`; andernfalls gibt **E_FAIL**. Wenn Sie ein Update zuzulassen, müssen Sie auch Festlegen der **DBROWSTATUS** in [IRowsetUpdateImpl:: Update](../../data/oledb/irowsetupdateimpl-update.md) in eine entsprechende [Zeilenstatus](https://msdn.microsoft.com/en-us/library/ms722752.aspx).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IRowsetUpdateImpl-Klasse](../../data/oledb/irowsetupdateimpl-class.md)