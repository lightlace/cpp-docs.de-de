---
title: RaiseException-Funktion | Microsoft Docs
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
ms.openlocfilehash: 2af97ac13386db450318f4d1f384517a8dd77baf
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882182"
---
# <a name="raiseexception-function"></a>RaiseException-Funktion
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
inline void __declspec(noreturn)   RaiseException(  
      HRESULT hr,   
      DWORD dwExceptionFlags = EXCEPTION_NONCONTINUABLE);  
```  
  
#### <a name="parameters"></a>Parameter  
 `hr`  
 Ausnahmecode: der ausgelösten Ausnahme; d. h. das HRESULT des eines fehlgeschlagenen Vorgangs.  
  
 `dwExceptionFlags`  
 Ein Flag, das angibt, eine vernachlässigbar Ausnahme (der Wert des Kennzeichens ist 0 (null)) oder noncontinuable Ausnahme (Flagwert ist ungleich null). Standardmäßig ist die Ausnahme fortfahren verhindert.  
  
## <a name="remarks"></a>Hinweise  
 Löst eine Ausnahme in den aufrufenden Thread aus.  
  
 Weitere Informationen finden Sie unter Windows **RaiseException** Funktion.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** internal.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)