---
title: 'CRowset:: GetData | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowset<TAccessor>::GetData
- ATL::CRowset<TAccessor>::GetData
- ATL::CRowset::GetData
- ATL.CRowset<TAccessor>.GetData
- CRowset<TAccessor>.GetData
- CRowset::GetData
- CRowset.GetData
- ATL.CRowset.GetData
dev_langs:
- C++
helpviewer_keywords:
- GetData method [OLE DB]
ms.assetid: 1e0347b5-3e24-4ff8-a790-839616c1522f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c0a8268f115f6c6d5a887bea7aad8a244d7e530c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="crowsetgetdata"></a>CRowset::GetData
Ruft Daten aus dem Rowset Kopie der Zeile ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetData() throw();   


HRESULT GetData(int nAccessor) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `nAccessor`  
 [in] Die Indexnummer des (null Offset) des Accessors für den Zugriff auf die Daten verwenden.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn Sie einen Accessor angeben, die keinen Autoaccessor in [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md), verwenden Sie diese Methode explizit die Daten abgerufen werden, durch die Anzahl der Accessor übergeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CRowset-Klasse](../../data/oledb/crowset-class.md)