---
title: 'Runtimeclass:: Release-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::Release
dev_langs:
- C++
helpviewer_keywords:
- Release method
ms.assetid: 0bd6f9e2-ad90-4de6-adef-a6286f458cb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1c1f9500abc1c92ea5f9aca64e379adfdcf84a44
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607523"
---
# <a name="runtimeclassrelease-method"></a>RuntimeClass::Release-Methode
Führt einen COM-Freigabe-Vorgang für die aktuelle **RuntimeClass** Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
STDMETHOD_(  
   ULONG,  
   Release  
)();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Verweiszähler NULL ist, wird die **RuntimeClass** Objekt wird gelöscht.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [RuntimeClass-Klasse](../windows/runtimeclass-class.md)