---
title: 'Simpleclassfactory:: CreateInstance-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleClassFactory::CreateInstance
dev_langs:
- C++
helpviewer_keywords:
- CreateInstance method
ms.assetid: 17b7947a-2608-49d9-b730-fef76501c9bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8a31d364a6464962b8243cfaced03131a20f9324
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="simpleclassfactorycreateinstance-method"></a>SimpleClassFactory::CreateInstance-Methode

Erstellt eine Instanz der angegebenen Schnittstelle.

## <a name="syntax"></a>Syntax

```cpp
STDMETHOD( CreateInstance )(
   _Inout_opt_ IUnknown* pUnkOuter,
   REFIID riid,
   _Deref_out_ void** ppvObject
);
```

### <a name="parameters"></a>Parameter

*pUnkOuter*  
Muss `nullptr`ist, andernfalls wird CLASS_E_NOAGGREGATION zurückgegeben.

SimpleClassFactory unterstützt keine Aggregation. Wenn die Aggregation unterstützt wurden, und das Objekt erstellt wurde, Teil einer Aggregatfunktion gehört, `pUnkOuter` wäre ein Zeiger auf die controlling IUnknown-Schnittstelle des Aggregats.

*riid*  
Schnittstellen-ID des Objekts zu erstellen.

*ppvObject*  
Wenn dieser Vorgang abgeschlossen wird, Zeiger auf eine Instanz des Objekts gemäß der `riid` Parameter.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="remarks"></a>Hinweise

Wenn &#95; &#95;WRL_STRICT&#95; &#95; wird definiert, ein Assert-Fehler wird ausgegeben, wenn in der Klasse Template-Parameter angegebene Basisklasse abgeleitet ist nicht [RuntimeClass](../windows/runtimeclass-class.md), oder ist nicht mit der ClassicCom konfiguriert oder WinRtClassicComMix [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) -Enumerationswert.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[SimpleClassFactory-Klasse](../windows/simpleclassfactory-class.md)