---
title: HANDLETraits-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/27/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits structure
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close method
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue method
ms.assetid: 22963e88-d857-4624-9182-7c986daff722
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3e670dca205f07d1e13a93f8acd0df5965b45109
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161709"
---
# <a name="handletraits-structure"></a>HANDLETraits-Struktur

Definiert die allgemeinen Merkmale eines Handles.

## <a name="syntax"></a>Syntax

```cpp
struct HANDLETraits;
```

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

Name   | Beschreibung
------ | ---------------------
`Type` | Ein Synonym für den HANDLE.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                              | Beschreibung
------------------------------------------------- | -----------------------------
[Handletraits:: Close](#close)                     | Schließt das angegebene Handle.
[Handletraits:: Getinvalidvalue](#getinvalidvalue) | Stellt ein ungültiges Handle dar.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`HANDLETraits`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="close"></a>Handletraits:: Close

Schließt das angegebene Handle.

```cpp
inline static bool Close(
   _In_ Type h
);
```

### <a name="parameters"></a>Parameter

*h*<br/>
Das Handle zu schließen.

### <a name="return-value"></a>Rückgabewert

**"true"** Wenn behandeln *h* geschlossen wird, erfolgreich ist; andernfalls **"false"**.

## <a name="getinvalidvalue"></a>Handletraits:: Getinvalidvalue

Stellt ein ungültiges Handle dar.

```cpp
inline static HANDLE GetInvalidValue();
```

### <a name="return-value"></a>Rückgabewert

Gibt immer INVALID_HANDLE_VALUE zurück. (INVALID_HANDLE_VALUE wird von Windows definiert.)
