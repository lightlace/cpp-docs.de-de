---
title: 'Simpleclassfactory:: CreateInstance-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleClassFactory::CreateInstance
dev_langs:
- C++
helpviewer_keywords:
- CreateInstance method
ms.assetid: 17b7947a-2608-49d9-b730-fef76501c9bc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 68778eb1b5421cfcf22261d8b1c1efd99bc32c50
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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

Wenn &#95; &#95; WRL_STRICT &#95; &#95; wird definiert, ein Assert-Fehler wird ausgegeben, wenn in der Klasse Template-Parameter angegebene Basisklasse abgeleitet ist nicht [RuntimeClass](../windows/runtimeclass-class.md), oder ist nicht konfiguriert, mit dem ClassicCom oder WinRtClassicComMix [RuntimeClassType ](../windows/runtimeclasstype-enumeration.md) -Enumerationswert.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[SimpleClassFactory-Klasse](../windows/simpleclassfactory-class.md)