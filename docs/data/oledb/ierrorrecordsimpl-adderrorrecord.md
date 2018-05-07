---
title: 'IErrorRecordsImpl:: Adderrorrecord | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IErrorRecordsImpl.AddErrorRecord
- AddErrorRecord
- IErrorRecordsImpl::AddErrorRecord
dev_langs:
- C++
helpviewer_keywords:
- AddErrorRecord method
ms.assetid: b5f8e9ae-509d-454f-b511-4bda7e972607
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bc60982a99b6c052d10ffe300efbfbcdde49d0fa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ierrorrecordsimpladderrorrecord"></a>IErrorRecordsImpl::AddErrorRecord
Fügt einen Datensatz mit dem OLE DB-Fehler-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(AddErrorRecord )(ERRORINFO *pErrorInfo,  
   DWORD dwLookupID,  
   DISPPARAMS *pdispparams,  
   IUnknown *punkCustomError,  
   DWORD dwDynamicErrorID);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IErrorRecords::AddErrorRecord](https://msdn.microsoft.com/en-us/library/ms725362.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IErrorRecordsImpl-Klasse](../../data/oledb/ierrorrecordsimpl-class.md)