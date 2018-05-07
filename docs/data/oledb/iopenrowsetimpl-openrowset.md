---
title: 'Iopenrowsetimpl:: OPENROWSET | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- OpenRowset
- IOpenRowsetImpl::OpenRowset
- IOpenRowsetImpl.OpenRowset
dev_langs:
- C++
helpviewer_keywords:
- OpenRowset method
ms.assetid: 2ece8d6c-d165-4f1d-b155-8609bbb60eb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 84bd34786dd87e92d70ad28d0f0a961cb01c1e48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="iopenrowsetimplopenrowset"></a>IOpenRowsetImpl::OpenRowset
Öffnet und gibt ein Rowset, das alle Zeilen aus einer einzelnen Basistabelle oder einem Index enthält.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT OpenRowset(IUnknown* pUnkOuter,  
   DBID* pTableID,  
   DBID* pIndexID,  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown** ppRowset);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IOpenRowset:: OPENROWSET](https://msdn.microsoft.com/en-us/library/ms716724.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode wird in ATLDB nicht gefunden. H. Sie wird durch die ATL-Objektassistenten erstellt, wenn Sie einen Anbieter erstellen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IOpenRowsetImpl-Klasse](../../data/oledb/iopenrowsetimpl-class.md)