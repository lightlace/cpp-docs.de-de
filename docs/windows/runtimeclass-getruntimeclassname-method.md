---
title: 'Runtimeclass:: Getruntimeclassname-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::GetRuntimeClassName
dev_langs:
- C++
helpviewer_keywords:
- GetRuntimeClassName method
ms.assetid: f6388163-fe65-4948-a4bc-ae6826f480e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 126133c5e542414f1fb38635e1cb14314bc55d52
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020394"
---
# <a name="runtimeclassgetruntimeclassname-method"></a>RuntimeClass::GetRuntimeClassName-Methode

Ruft den Common Language Runtime-Klassennamen des aktuellen **RuntimeClass** Objekt.

## <a name="syntax"></a>Syntax

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

### <a name="parameters"></a>Parameter
*runtimeName*  
Wenn dieser Vorgang abgeschlossen ist, den Namen der Common Language Runtime-Klasse.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="remarks"></a>Hinweise

Ein Assert-Fehler wird ausgegeben, wenn `__WRL_STRICT__` oder `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` ist nicht definiert.

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch
 [RuntimeClass-Klasse](../windows/runtimeclass-class.md)