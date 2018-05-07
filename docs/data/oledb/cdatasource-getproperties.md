---
title: 'CDataSource:: GetProperties | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CDataSource::GetProperties
- ATL.CDataSource.GetProperties
- CDataSource.GetProperties
- ATL::CDataSource::GetProperties
- GetProperties
dev_langs:
- C++
helpviewer_keywords:
- GetProperties method
ms.assetid: ffaecc17-9fe7-449e-94d6-43d31ad06cfc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e519504777a1ff9f2927d74340bec73e1b157e6d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cdatasourcegetproperties"></a>CDataSource::GetProperties
Gibt die Eigenschaftsinformationen für das Quellobjekt verbundenen Daten angefordert.  
  
## <a name="syntax"></a>Syntax  
  
```
HRESULT GetProperties(ULONG ulPropIDSets,   
   constDBPROPIDSET* pPropIDSet,   
   ULONG* pulPropertySets,   
   DBPROPSET** ppPropsets) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IDBProperties::GetProperties](https://msdn.microsoft.com/en-us/library/ms714344.aspx) in der *OLE DB Programmer's Reference* im Windows SDK.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie zum Abrufen einer einzelnen Eigenschaft [GetProperty](../../data/oledb/cdatasource-getproperty.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDataSource-Klasse](../../data/oledb/cdatasource-class.md)