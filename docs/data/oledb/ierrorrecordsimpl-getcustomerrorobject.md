---
title: 'IErrorRecordsImpl:: Getcustomerrorobject | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::IErrorRecordsImpl::GetCustomErrorObject
- IErrorRecordsImpl::GetCustomErrorObject
- ATL.IErrorRecordsImpl.GetCustomErrorObject
- IErrorRecordsImpl.GetCustomErrorObject
- GetCustomErrorObject
dev_langs:
- C++
helpviewer_keywords:
- GetCustomErrorObject method
ms.assetid: 96d3549b-a49c-4552-94b2-71babaf1bf20
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b89955ed3dbb11e4bb310b44526d390d6c143fc1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ierrorrecordsimplgetcustomerrorobject"></a>IErrorRecordsImpl::GetCustomErrorObject
Gibt einen Zeiger auf eine Schnittstelle für eine benutzerdefinierte Fehlerobjekt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(GetCustomErrorObject )(ULONG ulRecordNum,  
   REFIID riid,  
   IUnknown **ppObject);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/en-us/library/ms725417.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IErrorRecordsImpl-Klasse](../../data/oledb/ierrorrecordsimpl-class.md)