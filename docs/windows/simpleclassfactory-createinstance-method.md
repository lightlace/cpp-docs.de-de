---
title: 'Simpleclassfactory:: CreateInstance-Methode | Microsoft-Dokumentation'
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
ms.openlocfilehash: f25e85e59769f822a6c732cc0911c564c0104f96
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39651079"
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
Muss **"nullptr"** ist, andernfalls CLASS_E_NOAGGREGATION zurückgegeben wird.

SimpleClassFactory unterstützt keine Aggregation. Wenn der Aggregation unterstützt wurden, und das zu erstellende Objekt war Teil einer Aggregatfunktion gehört, *pUnkOuter* wäre ein Zeiger auf das steuernde `IUnknown` Schnittstelle des Aggregats.

*riid*  
Schnittstellen-ID des Objekts zu erstellen.

*ppvObject*  
Wenn dieser Vorgang abgeschlossen ist, Zeiger auf eine Instanz des Objekts gemäß der *Riid* Parameter.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="remarks"></a>Hinweise

Wenn &#95; &#95;WRL_STRICT&#95; &#95; wird definiert, ein Assert-Fehler wird ausgegeben, wenn die Klassenvorlagenparameter angegebene Basisklasse abgeleitet ist nicht [RuntimeClass](../windows/runtimeclass-class.md), oder ist nicht mit der ClassicCom konfiguriert oder WinRtClassicComMix [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) Enumerationswert.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch
 [SimpleClassFactory-Klasse](../windows/simpleclassfactory-class.md)