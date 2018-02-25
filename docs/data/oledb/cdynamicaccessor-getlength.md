---
title: 'CDynamicAccessor:: GetLength | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDynamicAccessor.GetLength
- ATL.CDynamicAccessor.GetLength
- CDynamicAccessor::GetLength
- ATL::CDynamicAccessor::GetLength
dev_langs:
- C++
helpviewer_keywords:
- GetLength method
ms.assetid: 3ae8983b-b267-4cf9-bfc0-3e191f79e646
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cb5f10495e1e57a93cc79f98a234aa1007dadce6
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicaccessorgetlength"></a>CDynamicAccessor::GetLength
Ruft die Länge der angegebenen Spalte ab.  
  
## <a name="syntax"></a>Syntax  
  
```
bool GetLength(DBORDINAL nColumn,   
  DBLENGTH* pLength) const throw();  

bool GetLength(const CHAR* pColumnName,   
   DBLENGTH* pLength) const throw();  

bool GetLength(const WCHAR* pColumnName,   
   DBLENGTH* pLength) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `nColumn`  
 [in] Die Nummer der Spalte. Die spaltenzählung beginnt mit 1. Der Wert 0 verweist auf die Lesezeichenspalte, sofern vorhanden.  
  
 `pColumnName`  
 [in] Ein Zeiger auf eine Zeichenfolge, die den Namen der Spalte enthält.  
  
 `pLength`  
 [out] Ein Zeiger auf die ganze Zahl, die die Länge der Spalte in Bytes enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** , wenn die angegebene Spalte gefunden wird. Andernfalls, gibt diese Funktion **"false"**.  
  
## <a name="remarks"></a>Hinweise  
 Die erste Außerkraftsetzung nimmt die Nummer der Spalte und die zweiten und dritten Außerkraftsetzungen schalten Sie den Spaltennamen im ANSI- oder Unicode-Format, bzw. aus.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::SetLength](../../data/oledb/cdynamicaccessor-setlength.md)