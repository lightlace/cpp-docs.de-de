---
title: GetActivationFactory-Funktion
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::GetActivationFactory
- client/ABI::Windows::Foundation::GetActivationFactory
- client/Windows::Foundation::GetActivationFactory
helpviewer_keywords:
- GetActivationFactory function
ms.assetid: 5736d285-6beb-42aa-8788-e261c0010afe
ms.openlocfilehash: 3e138eee9e5bc02971cd1eb34c78f2be4ad5c9a0
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033942"
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

*factory*<br/>
Wenn dieser Vorgang abgeschlossen ist, einen Verweis auf die aktivierungsfactory für den Typ *T*.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein Fehler HRESULT, der angibt, warum dieser Vorgang fehlgeschlagen ist.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Windows::Foundation

## <a name="see-also"></a>Siehe auch

[Windows::Foundation-Namespace](windows-foundation-namespace.md)