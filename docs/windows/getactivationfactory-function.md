---
title: GetActivationFactory-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::GetActivationFactory
- client/ABI::Windows::Foundation::GetActivationFactory
- client/Windows::Foundation::GetActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- GetActivationFactory function
ms.assetid: 5736d285-6beb-42aa-8788-e261c0010afe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f5afaa14d926cc7dde86cdbdb6b5ca8162f81d7c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402147"
---
# <a name="getactivationfactory-function"></a>GetActivationFactory-Funktion

Ruft eine aktivierungsfactory für den durch die Template-Parameter angegebenen Typ ab.

## <a name="syntax"></a>Syntax

```cpp
template<typename T>
inline HRESULT GetActivationFactory(
   _In_ HSTRING activatableClassId,
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> factory
);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Ein Vorlagenparameter, der angibt, welche die aktivierungsfactory.

*activatableClassId*<br/>
Der Name der Klasse, die die Aktivierungs-Factory erstellt werden kann.

*Factory*<br/>
Wenn dieser Vorgang abgeschlossen ist, einen Verweis auf die aktivierungsfactory für den Typ *T*.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein Fehler HRESULT, der angibt, warum dieser Vorgang fehlgeschlagen ist.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Windows:: Foundation

## <a name="see-also"></a>Siehe auch

[Windows::Foundation-Namespace](../windows/windows-foundation-namespace.md)