---
title: 'Runtimeclass:: Gettrustlevel-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::GetTrustLevel
dev_langs:
- C++
helpviewer_keywords:
- GetTrustLevel method
ms.assetid: bd90407e-6dd7-41c3-9ea0-c402c276014a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c714f37a53e111c90333352610fd73532ac86fe7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599831"
---
# <a name="runtimeclassgettrustlevel-method"></a>RuntimeClass::GetTrustLevel-Methode

Ruft die Vertrauensebene des aktuellen **RuntimeClass** Objekt.

## <a name="syntax"></a>Syntax

```cpp
STDMETHOD(GetTrustLevel)(
    _Out_ TrustLevel* trustLvl
);
```

### <a name="parameters"></a>Parameter

*trustLvl*  
Wenn dieser Vorgang abgeschlossen ist, die Vertrauensebene des aktuellen **RuntimeClass** Objekt.

## <a name="return-value"></a>Rückgabewert

Stets S_OK.

## <a name="remarks"></a>Hinweise

Ein Assert-Fehler wird ausgegeben, wenn `__WRL_STRICT__` oder `__WRL_FORCE_INSPECTABLE_CLASS_MACRO__` ist nicht definiert.

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[RuntimeClass-Klasse](../windows/runtimeclass-class.md)