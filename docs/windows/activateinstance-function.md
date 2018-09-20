---
title: ActivateInstance-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Windows::Foundation::ActivateInstance
- client/ABI::Windows::Foundation::ActivateInstance
dev_langs:
- C++
helpviewer_keywords:
- ActivateInstance function
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ebebe0bbceafe82c41ec99b2532c965670776127
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426392"
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