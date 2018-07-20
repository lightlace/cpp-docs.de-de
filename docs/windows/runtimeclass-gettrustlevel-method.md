---
title: 'Runtimeclass:: Gettrustlevel-Methode | Microsoft Docs'
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
ms.openlocfilehash: bc588950cc8752a7c2b8e1ddf00b2193aaf0f395
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892630"
---
# <a name="runtimeclassgettrustlevel-method"></a>RuntimeClass::GetTrustLevel-Methode

Ruft die Vertrauensebene des aktuellen RuntimeClass-Objekts ab.

## <a name="syntax"></a>Syntax

```cpp
STDMETHOD(GetTrustLevel)(
    _Out_ TrustLevel* trustLvl
);
```

### <a name="parameters"></a>Parameter

*trustLvl*  
Wenn dieser Vorgang abgeschlossen wird, die Vertrauensebene der aktuellen RuntimeClass-Objekt.

## <a name="return-value"></a>Rückgabewert

Stets S_OK.

## <a name="remarks"></a>Hinweise

Ein Assert-Fehler wird ausgegeben, wenn &#95; &#95;WRL_STRICT&#95; &#95; oder &#95; &#95;WRL_FORCE_INSPECTABLE_CLASS_MACRO&#95; &#95; ist nicht definiert.

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[RuntimeClass-Klasse](../windows/runtimeclass-class.md)