---
title: 'CDataSource:: GetProperty | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CDataSource::GetProperty
- ATL.CDataSource.GetProperty
- CDataSource.GetProperty
- CDataSource::GetProperty
dev_langs:
- C++
helpviewer_keywords:
- GetProperty method
ms.assetid: 6531147c-b164-4ab5-a4a7-509634b85b4d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: afe21f6f41491a4f62eda09e2df43aa470417e20
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cdatasourcegetproperty"></a>CDataSource::GetProperty
Gibt den Wert einer angegebenen Eigenschaft für das Quellobjekt verbundenen Daten zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetProperty(const GUID& guid,   
   DBPROPID propid,   
   VARIANT* pVariant) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `guid`  
 [in] Eine GUID identifiziert den Eigenschaftensatz für die Eigenschaft zurückgegeben werden sollen.  
  
 `propid`  
 [in] Eigenschafts-ID für die Eigenschaft zurückgegeben.  
  
 *pVariant*  
 [out] Ein Zeiger auf die Variante, in denen **GetProperty** gibt den Wert der Eigenschaft zurück.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie zum Abrufen mehrerer Eigenschaften [GetProperties](../../data/oledb/cdatasource-getproperties.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDataSource-Klasse](../../data/oledb/cdatasource-class.md)