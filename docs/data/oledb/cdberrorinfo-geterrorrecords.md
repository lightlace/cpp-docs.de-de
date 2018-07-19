---
title: 'Cdberrorinfo:: Geterrorrecords | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 33e0ab54bc3da570aecba0df347e14a511b0a833
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095221"
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