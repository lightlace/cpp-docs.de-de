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
ms.openlocfilehash: 49024e903237160cc26a9c095cf9f313b43ccb6f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600764"
---
# <a name="raiseexception-function"></a>RaiseException-Funktion

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
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