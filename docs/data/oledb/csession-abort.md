---
title: 'CSession:: Abort | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CSession.Abort
- CSession::Abort
- ATL.CSession.Abort
- ATL::CSession::Abort
dev_langs:
- C++
helpviewer_keywords:
- Abort method
ms.assetid: 02413b20-c486-451f-b4d7-73a6e8065df8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8b4789db8497f314c19eb531327f4b712f37fc5e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095829"
---
# <a name="csessionabort"></a>CSession::Abort
Die Transaktion abbricht.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT Abort(BOID* pboidReason = NULL,   
   BOOL bRetaining = FALSE,   
   BOOL bAsync = FALSE) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [ITransaction:: Abort](https://msdn.microsoft.com/en-us/library/ms709833.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CSession-Klasse](../../data/oledb/csession-class.md)