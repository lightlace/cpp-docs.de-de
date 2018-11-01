---
title: ActivateInstance-Funktion
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Windows::Foundation::ActivateInstance
- client/ABI::Windows::Foundation::ActivateInstance
helpviewer_keywords:
- ActivateInstance function
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
ms.openlocfilehash: 65648d62657bf989d4a08660e0fd7724511350c1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666296"
---
# <a name="activateinstance-function"></a>ActivateInstance-Funktion

Registriert, und ruft eine Instanz eines angegebenen Typs, der definiert, die in einer angegebenen Klasse-ID ab

## <a name="syntax"></a>Syntax

```cpp
template<typename T>
inline HRESULT ActivateInstance(
   _In_ HSTRING activatableClassId,
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> instance
);
```

### <a name="parameters"></a>Parameter

*T*<br/>
Ein Typ, zu aktivieren.

*activatableClassId*<br/>
Der Name des Klassen-ID, die Parameter definiert *T*.

*Instanz*<br/>
Wenn dieser Vorgang abgeschlossen ist, einen Verweis auf eine Instanz von *T*.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein Fehler HRESULT, das die Ursache des Fehlers angibt.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Windows:: Foundation

## <a name="see-also"></a>Siehe auch

[Windows::Foundation-Namespace](../windows/windows-foundation-namespace.md)