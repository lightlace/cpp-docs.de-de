---
title: 'IRowsetUpdateImpl:: IsUpdateAllowed | Microsoft Docs'
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetUpdateImpl::IsUpdateAllowed
- IRowsetUpdateImpl.IsUpdateAllowed
- IsUpdateAllowed
dev_langs:
- C++
helpviewer_keywords:
- IsUpdateAllowed method
ms.assetid: d6daf3b3-a8e0-4275-a67d-897dea01e297
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 363626cedddea3da57e829a43c21c63b5c2b05cd
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122003"
---
# <a name="irowsetupdateimplisupdateallowed"></a>IRowsetUpdateImpl::IsUpdateAllowed
Überschreiben Sie diese Methode, um für Sicherheit, Integrität und so weiter vor Updates zu überprüfen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT IsUpdateAllowed(DBPENDINGSTATUS /* [in] */ /* status */,  
   HROW /* [in] */ /* hRowUpdate */,  
   DBROWSTATUS* /* [out] */ /* pRowStatus */);  
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