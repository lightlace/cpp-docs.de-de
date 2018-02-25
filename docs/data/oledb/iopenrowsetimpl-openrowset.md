---
title: 'Iopenrowsetimpl:: OPENROWSET | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 430fd00093cbea8c294e97016d42553eea2e815d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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