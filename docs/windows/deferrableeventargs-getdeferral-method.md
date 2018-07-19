---
title: 'Deferrableeventargs:: Getdeferral-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: ef6dc7c5-b0be-4b85-8507-d3fd97f2185d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2442894c5f7bd85eb94262e776294c1e52a19e01
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33883540"
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