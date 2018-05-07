---
title: 'CAccessorRowset:: GetColumnInfo | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- GetColumnInfo
- CAccessorRowset.GetColumnInfo
- CAccessorRowset::GetColumnInfo
dev_langs:
- C++
helpviewer_keywords:
- GetColumnInfo method
ms.assetid: 8ade2388-3c58-43cd-8ed6-499ee0531291
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 46f645ba2f662cad38fa962cea543f7530418530
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="caccessorrowsetgetcolumninfo"></a>CAccessorRowset::GetColumnInfo
Ruft die Spalteninformationen aus dem geöffneten Rowset ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetColumnInfo(DBORDINAL* pulColumns,  
   DBCOLUMNINFO** ppColumnInfo,  
   LPOLESTR* ppStrings) const;  

HRESULT GetColumnInfo(DBORDINAL* pColumns,  
   DBCOLUMNINFO** ppColumnInfo);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IColumnsInfo:: GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Der Benutzer muss die zurückgegebenen Spalteninformationen und Zeichenfolgenpuffer freigeben. Verwenden Sie die zweite Version dieser Methode, bei der Verwendung [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) und die Bindungen überschreiben müssen.  
  
 Weitere Informationen finden Sie unter [IColumnsInfo:: GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CAccessorRowset-Klasse](../../data/oledb/caccessorrowset-class.md)