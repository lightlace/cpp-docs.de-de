---
title: 'IErrorRecordsImpl:: Getbasicerrorinfo | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::IErrorRecordsImpl::GetBasicErrorInfo
- IErrorRecordsImpl::GetBasicErrorInfo
- GetBasicErrorInfo
- ATL.IErrorRecordsImpl.GetBasicErrorInfo
- IErrorRecordsImpl.GetBasicErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- GetBasicErrorInfo method
ms.assetid: d0b4dec3-f32a-4aaa-8365-524f2e7c8395
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 787cbeaea106d33b276458c75251ec5850e51550
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ierrorrecordsimplgetbasicerrorinfo"></a>IErrorRecordsImpl::GetBasicErrorInfo
Gibt grundlegende Informationen über den Fehler, z. B. den Rückgabecode und die anbieterspezifische Fehlernummer zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      STDMETHOD(GetBasicErrorInfo )(ULONG ulRecordNum,  
   ERRORINFO *pErrorInfo);  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IErrorRecords::GetBasicErrorInfo](https://msdn.microsoft.com/en-us/library/ms723907.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [IErrorRecordsImpl-Klasse](../../data/oledb/ierrorrecordsimpl-class.md)