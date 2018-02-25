---
title: 'Cdberrorinfo:: GetErrorInfo | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- GetErrorInfo
- ATL.CDBErrorInfo.GetErrorInfo
- CDBErrorInfo.GetErrorInfo
- ATL::CDBErrorInfo::GetErrorInfo
- CDBErrorInfo::GetErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- GetErrorInfo method
ms.assetid: 234e1f02-c307-4666-b3ce-2a4d62407fa1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9877b2094c3bccec1bf7552ba86d60050ab16055
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cdberrorinfogeterrorinfo"></a>CDBErrorInfo::GetErrorInfo
Aufrufe [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) zurückzugebenden ein [IErrorInfo](https://msdn.microsoft.com/en-us/library/ms718112.aspx) Schnittstellenzeiger auf den angegebenen Datensatz.  
  
## <a name="syntax"></a>Syntax  
  
```
HRESULT GetErrorInfo(ULONG ulRecordNum,   
   LCID lcid,IErrorInfo** ppErrorInfo) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) in der *OLE DB Programmer's Reference*.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDBErrorInfo-Klasse](../../data/oledb/cdberrorinfo-class.md)