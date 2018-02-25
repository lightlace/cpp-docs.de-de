---
title: 'CDynamicAccessor:: AddBindEntry | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CDynamicAccessor::AddBindEntry
- AddBindEntry
- CDynamicAccessor.AddBindEntry
- CDynamicAccessor::AddBindEntry
- ATL.CDynamicAccessor.AddBindEntry
dev_langs:
- C++
helpviewer_keywords:
- AddBindEntry method
ms.assetid: 8f139376-7db3-4193-ba3b-63fe938ffa79
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7234b06a32f53a24c5ccb9978ccc3910fa900807
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicaccessoraddbindentry"></a>CDynamicAccessor::AddBindEntry
Fügt einen Eintrag für die Bindung den Ausgabespalten.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT AddBindEntry(const DBCOLUMNINFO& info) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `info`  
 [in] Ein **DBCOLUMNINFO** Struktur, die Informationen in der Spalte enthält. Finden Sie unter "DBCOLUMNINFO-Strukturen" in [IColumnsInfo:: GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="return-value"></a>Rückgabewert  
 Zu den standardmäßigen `HRESULT` Werte.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode zum Überschreiben den Standardeinstellung Accessor mit erstellt `CDynamicAccessor` (siehe [Gewusst wie: Abrufen von Daten?](../../data/oledb/fetching-data.md)).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)