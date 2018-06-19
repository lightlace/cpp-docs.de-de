---
title: 'Igetdatasourceimpl:: GetDatasource | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- GetDataSource
- IGetDataSourceImpl.GetDataSource
- IGetDataSourceImpl::GetDataSource
dev_langs:
- C++
helpviewer_keywords:
- GetDataSource method
ms.assetid: b70995d2-b951-452e-a2d4-fb3eb085886e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 99ef8aa8466d9a805c2e3dba10d465d41f21e416
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101798"
---
# <a name="igetdatasourceimplgetdatasource"></a>IGetDataSourceImpl::GetDataSource
Gibt einen Schnittstellenzeiger auf das Datenquellenobjekt, das die Sitzung erstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(GetDataSource)(REFIID riid,   
   IUnknown ** ppDataSource);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IGetDataSource::GetDataSource](https://msdn.microsoft.com/en-us/library/ms725443.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="remarks"></a>Hinweise  
 Nützlich, wenn Sie Eigenschaften in das Datenquellenobjekt zugreifen müssen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IGetDataSourceImpl-Klasse](../../data/oledb/igetdatasourceimpl-class.md)