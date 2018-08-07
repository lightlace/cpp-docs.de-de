---
title: RaiseException-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::RaiseException
dev_langs:
- C++
helpviewer_keywords:
- RaiseException function
ms.assetid: f9c74f6d-112a-4d2e-900f-622f795d5dbf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e93b7281b079918641bf36ebcd72968a98eb95ec
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39602665"
---
# <a name="raiseexception-function"></a>RaiseException-Funktion
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
inline void __declspec(noreturn)   RaiseException(  
      HRESULT hr,   
      DWORD dwExceptionFlags = EXCEPTION_NONCONTINUABLE);  
```  
  
### <a name="parameters"></a>Parameter  
 *HR*  
 Der Ausnahmecode, der die Ausnahme ausgelöst wird; d. h. das HRESULT des einen fehlgeschlagenen Vorgang.  
  
 *dwExceptionFlags*  
 Ein Flag, der angibt, ein vernachlässigbare Ausnahme (der Flagwert ist 0 (null)), oder eine noncontinuable Ausnahme (Flag-Wert ungleich NULL ist). Standardmäßig ist die Ausnahme nicht fortsetzbare.  
  
## <a name="remarks"></a>Hinweise  
 Löst eine Ausnahme aus, in dem aufrufenden Thread aus.  
  
 Weitere Informationen finden Sie in der Windows `RaiseException` Funktion.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** internal.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)