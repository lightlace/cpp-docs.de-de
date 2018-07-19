---
title: 'Simpleactivationfactory:: Activateinstance-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance
dev_langs:
- C++
helpviewer_keywords:
- ActivateInstance method
ms.assetid: 4f836e51-5a6c-4bad-b871-9f25199298b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5af4bfd22302b7694b9bafbc1452d636b19cb3c7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889420"
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

Wenn &#95; &#95;WRL_STRICT&#95; &#95; wird definiert, ein Assert-Fehler wird ausgegeben, wenn in der Klasse Template-Parameter angegebene Basisklasse abgeleitet ist nicht [RuntimeClass](../windows/runtimeclass-class.md), oder ist nicht mit der WinRt konfiguriert oder WinRtClassicComMix [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) -Enumerationswert.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[SimpleActivationFactory-Klasse](../windows/simpleactivationfactory-class.md)