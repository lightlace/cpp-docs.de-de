---
title: 'Simpleactivationfactory:: Activateinstance-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance
dev_langs: C++
helpviewer_keywords: ActivateInstance method
ms.assetid: 4f836e51-5a6c-4bad-b871-9f25199298b4
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6bbe9d8c215674f087c6e0fa4ca7f3439fb89b78
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="simpleactivationfactoryactivateinstance-method"></a>SimpleActivationFactory::ActivateInstance-Methode

Erstellt eine Instanz der angegebenen Schnittstelle.

## <a name="syntax"></a>Syntax

```cpp
STDMETHOD( ActivateInstance )(
    _Deref_out_ IInspectable **ppvObject
);
```

### <a name="parameters"></a>Parameter

*ppvObject*  
Wenn dieser Vorgang abgeschlossen wird, Zeiger auf eine Instanz des Objekts gemäß der `Base` Klassenvorlagenparameter.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="remarks"></a>Hinweise

Wenn &#95; &#95; WRL_STRICT &#95; &#95; wird definiert, ein Assert-Fehler wird ausgegeben, wenn in der Klasse Template-Parameter angegebene Basisklasse abgeleitet ist nicht [RuntimeClass](../windows/runtimeclass-class.md), oder ist nicht konfiguriert, mit dem WinRt oder WinRtClassicComMix [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) -Enumerationswert.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[SimpleActivationFactory-Klasse](../windows/simpleactivationfactory-class.md)