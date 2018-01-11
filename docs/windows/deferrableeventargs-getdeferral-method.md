---
title: 'Deferrableeventargs:: Getdeferral-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
ms.assetid: ef6dc7c5-b0be-4b85-8507-d3fd97f2185d
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2a49fba82867650a80f45de3c6301405f96b5c47
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="deferrableeventargsgetdeferral-method"></a>DeferrableEventArgs::GetDeferral-Methode
Ruft einen Verweis auf die [Deferral](http://go.microsoft.com/fwlink/p/?linkid=526520) Objekt, das ein zurückgestelltes Ereignis darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)  
```  
  
#### <a name="parameters"></a>Parameter  
 `result`  
 Ein Zeiger, der auf die [Deferral](http://go.microsoft.com/fwlink/p/?linkid=526520) Objekt, wenn der Aufruf abgeschlossen wird.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## <a name="remarks"></a>Hinweise  
 Ein Codebeispiel finden Sie unter [DeferrableEventArgs-Klasse](../windows/deferrableeventargs-class.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [DeferrableEventArgs-Klasse](../windows/deferrableeventargs-class.md)