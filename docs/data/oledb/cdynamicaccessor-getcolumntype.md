---
title: 'CDynamicAccessor:: GetColumnType | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CDynamicAccessor.GetColumnType
- CDynamicAccessor::GetColumnType
- GetColumnType
- CDynamicAccessor.GetColumnType
- ATL::CDynamicAccessor::GetColumnType
dev_langs:
- C++
helpviewer_keywords:
- GetColumnType method
ms.assetid: ac96a2e9-6049-4eb5-9718-9f5f5446b74e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 301fd04aba6d5f3157bade523ac7a805c977a518
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicaccessorgetcolumntype"></a>CDynamicAccessor::GetColumnType
Ruft den Datentyp einer angegebenen Spalte ab.  
  
## <a name="syntax"></a>Syntax  
  
```
bool GetColumnType(DBORDINAL nColumn,   
  DBTYPE* pType) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `nColumn`  
 [in] Die Nummer der Spalte. Die spaltenzählung beginnt mit 1. Der Wert 0 verweist auf die Lesezeichenspalte, sofern vorhanden.  
  
 `pType`  
 [out] Ein Zeiger auf den Datentyp der angegebenen Spalte.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg oder **"false"** bei einem Fehler.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)   
 [DBTYPE](https://msdn.microsoft.com/en-us/library/ms711251.aspx)