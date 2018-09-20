---
title: 'Module:: getactivationfactory-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GetActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- GetActivationFactory method
ms.assetid: 59da8844-072e-414b-b89c-1db1cc4fd81d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 995594ee48e6ca408e88d9ab14968d88b536d309
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403506"
---
# <a name="modulegetactivationfactory-method"></a>Module::GetActivationFactory-Methode

Ruft eine aktivierungsfactory für das Modul ab.

## <a name="syntax"></a>Syntax

```cpp
WRL_NOTHROW HRESULT GetActivationFactory(
   _In_ HSTRING pActivatibleClassId,
   _Deref_out_ IActivationFactory **ppIFactory,
   wchar_t* serverName = nullptr
);
```

### <a name="parameters"></a>Parameter

*pActivatibleClassId*<br/>
Die IID der von einer Runtime-Klasse.

*ppIFactory*<br/>
Die "iactivationfactory" für die angegebene Runtime-Klasse.

*ServerName*<br/>
Der Name einer Teilmenge von Klassenfactorys im aktuellen Modul. Geben Sie den Servernamen in verwendet die [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) -Makro, oder geben Sie **"nullptr"** um den Standardnamen für den Server zu erhalten.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls der HRESULT-Wert zurückgegeben, indem GetActivationFactory.

## <a name="requirements"></a>Anforderungen

**Header:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Module-Klasse](../windows/module-class.md)<br/>
[ActivatableClass-Makros](../windows/activatableclass-macros.md)