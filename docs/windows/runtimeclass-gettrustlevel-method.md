---
title: 'Runtimeclass:: Gettrustlevel-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::GetTrustLevel
dev_langs:
- C++
helpviewer_keywords:
- GetTrustLevel method
ms.assetid: bd90407e-6dd7-41c3-9ea0-c402c276014a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 89a00c052ec1191cd57057f52401954397169b88
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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

Ein Assert-Fehler wird ausgegeben, wenn &#95; &#95; WRL_STRICT &#95; &#95; oder &#95; &#95; WRL_FORCE_INSPECTABLE_CLASS_MACRO &#95; &#95; ist nicht definiert.

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[RuntimeClass-Klasse](../windows/runtimeclass-class.md)