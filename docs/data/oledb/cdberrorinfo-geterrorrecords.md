---
title: 'Cdberrorinfo:: Geterrorrecords | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDBErrorInfo.GetErrorRecords
- ATL.CDBErrorInfo.GetErrorRecords
- ATL::CDBErrorInfo::GetErrorRecords
- GetErrorRecords
- CDBErrorInfo::GetErrorRecords
dev_langs:
- C++
helpviewer_keywords:
- GetErrorRecords method
ms.assetid: 07746774-bcca-4833-8f55-a619e9777c17
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5187de6c9150ead2c01c770e09cb1a7e64c48004
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="cdberrorinfogeterrorrecords"></a>CDBErrorInfo::GetErrorRecords
Ruft die Error-Datensätze für das angegebene Objekt ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetErrorRecords(IUnknown* pUnk,   
   const IID& iid,   
   ULONG* pcRecords) throw();  


HRESULT GetErrorRecords(ULONG* pcRecords) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 *pUnk*  
 [in] Schnittstelle für das Objekt für den Fehlerdatensätze abgerufen.  
  
 `iid`  
 [in] Die IID der Schnittstelle, die dem Fehler zugeordnet.  
  
 *pcRecords*  
 [out] Ein Zeiger auf die (1-basiert) Anzahl der Error-Datensätze.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie die erste Form der Funktion, wenn Sie die Schnittstelle zum Abrufen der Fehlerinformationen aus überprüfen möchten. Verwenden Sie andernfalls die zweite Form.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDBErrorInfo-Klasse](../../data/oledb/cdberrorinfo-class.md)