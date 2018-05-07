---
title: 'CDynamicAccessor:: SetLength | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CDynamicAccessor::SetLength
- CDynamicAccessor.SetLength
- CDynamicAccessor::SetLength
- ATL.CDynamicAccessor.SetLength
dev_langs:
- C++
helpviewer_keywords:
- SetLength method
ms.assetid: 8109ae73-04ec-4a47-be97-ba1e60080384
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ae99881309188b9cfa7ec3a93a6d4afa43ba72ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cdynamicaccessorsetlength"></a>CDynamicAccessor::SetLength
Legt die Länge der angegebenen Spalte.  
  
## <a name="syntax"></a>Syntax  
  
```
bool SetLength(DBORDINAL nColumn,   
   DBLENGTH nLength)throw();  

bool SetLength(const CHAR* pColumnName,   
   DBLENGTH nLength) throw();  

bool SetLength(const WCHAR* pColumnName,   
   DBLENGTH nLength) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `nColumn`  
 [in] Die Nummer der Spalte. Die spaltenzählung beginnt mit 1. Der Wert 0 verweist auf die Lesezeichenspalte, sofern vorhanden.  
  
 `nLength`  
 [in] Die Länge der Spalte in Bytes.  
  
 `pColumnName`  
 [in] Ein Zeiger auf eine Zeichenfolge, die den Namen der Spalte enthält.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** , wenn die Länge der angegebenen Spalte festgelegt ist. Andernfalls, gibt diese Funktion **"false"**.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::GetLength](../../data/oledb/cdynamicaccessor-getlength.md)