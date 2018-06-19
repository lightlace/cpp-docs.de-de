---
title: 'Iopenrowsetimpl:: CreateRowset | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IOpenRowsetImpl.CreateRowset
- IOpenRowsetImpl::CreateRowset
- CreateRowset
dev_langs:
- C++
helpviewer_keywords:
- CreateRowset method
ms.assetid: 69041cf6-7a2f-4409-a26e-6e984c24986e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2d4554a2aeee3218ce505dc2c135167a3e38d55c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33105178"
---
# <a name="iopenrowsetimplcreaterowset"></a>IOpenRowsetImpl::CreateRowset
Erstellt ein Rowsetobjekt. Nicht direkt vom Benutzer aufgerufen. Finden Sie unter [IOpenRowset:: OPENROWSET](https://msdn.microsoft.com/en-us/library/ms716724.aspx) in die *OLE DB Programmer's Reference.*  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      template template <class RowsetClass  
      >  
HRESULT CreateRowset(IUnknown* pUnkOuter,  
   DBID* pTableID,  
   DBID* pIndexID,  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown** ppRowset,  
   RowsetClass*& pRowsetObj);  
```  
  
#### <a name="parameters"></a>Parameter  
 `RowsetClass`  
 Ein Klassenmember für die Vorlage, des Benutzers Rowsetklasse darstellt. In der Regel vom Assistenten generiert.  
  
 `pRowsetObj`  
 [out] Ein Zeiger auf ein Rowsetobjekt. Dieser Parameter wird in der Regel nicht verwendet, jedoch kann verwendet werden, wenn Sie mehr Arbeit für das Rowset durchführen müssen, vor der Übergabe an ein COM-Objekt. Die Lebensdauer des `pRowsetObj` gebunden ist, indem Sie `ppRowset`.  
  
 Andere Parameter, finden Sie unter [IOpenRowset:: OPENROWSET](https://msdn.microsoft.com/en-us/library/ms716724.aspx) in die *OLE DB Programmer's Reference.*  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IOpenRowsetImpl-Klasse](../../data/oledb/iopenrowsetimpl-class.md)