---
title: 'IErrorRecordsImpl:: Getcustomerrorobject | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IErrorRecordsImpl::GetCustomErrorObject
- IErrorRecordsImpl::GetCustomErrorObject
- ATL.IErrorRecordsImpl.GetCustomErrorObject
- IErrorRecordsImpl.GetCustomErrorObject
- GetCustomErrorObject
dev_langs: C++
helpviewer_keywords: GetCustomErrorObject method
ms.assetid: 96d3549b-a49c-4552-94b2-71babaf1bf20
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 73babd593359a502d8d12cf1bbfb5a3c6f8c477b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="ierrorrecordsimplgetcustomerrorobject"></a>IErrorRecordsImpl::GetCustomErrorObject
Gibt einen Zeiger auf eine Schnittstelle für eine benutzerdefinierte Fehlerobjekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      STDMETHOD( GetCustomErrorObject )(  
   ULONG ulRecordNum,  
   REFIID riid,  
   IUnknown **ppObject   
);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/en-us/library/ms725417.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IErrorRecordsImpl-Klasse](../../data/oledb/ierrorrecordsimpl-class.md)