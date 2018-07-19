---
title: 'CDynamicAccessor:: GetStatus | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CDynamicAccessor::GetStatus
- CDynamicAccessor.GetStatus
- ATL.CDynamicAccessor.GetStatus
- CDynamicAccessor::GetStatus
dev_langs:
- C++
helpviewer_keywords:
- GetStatus method
ms.assetid: 8f1aba69-5c2c-4ca7-ad84-7b4b27995eb8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 98e120e19c6115b98ed57bc8d25a934b84573386
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095790"
---
# <a name="cdynamicaccessorgetstatus"></a>CDynamicAccessor::GetStatus
Ruft den Status der angegebenen Spalte ab.  
  
## <a name="syntax"></a>Syntax  
  
```
bool GetStatus(DBORDINAL nColumn,   
  DBSTATUS* pStatus) const throw();  

bool GetStatus(const CHAR* pColumnName,  
   DBSTATUS* pStatus) const throw();  

bool GetStatus(const WCHAR* pColumnName,  
   DBSTATUS* pStatus) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 `nColumn`  
 [in] Die Nummer der Spalte. Die spaltenzählung beginnt mit 1. Der Wert 0 verweist auf die Lesezeichenspalte, sofern vorhanden.  
  
 `pColumnName`  
 [in] Ein Zeiger auf eine Zeichenfolge, die den Namen der Spalte enthält.  
  
 `pStatus`  
 [out] Ein Zeiger auf die Variable, die den Status in der Spalte enthält. Finden Sie unter [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) in der *OLE DB Programmer's Reference* für Weitere Informationen.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** , wenn die angegebene Spalte gefunden wird. Andernfalls, gibt diese Funktion **"false"**.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::SetStatus](../../data/oledb/cdynamicaccessor-setstatus.md)