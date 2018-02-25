---
title: 'IErrorRecordsImpl:: Getcustomerrorobject | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bca5511899bc4eabedb719dd5f5d73ad5473bd02
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
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