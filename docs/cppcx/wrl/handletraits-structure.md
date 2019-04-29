---
title: HANDLETraits-Struktur
ms.date: 09/27/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits structure
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close method
- Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue method
ms.assetid: 22963e88-d857-4624-9182-7c986daff722
ms.openlocfilehash: 4dd2cde62d36c46926e703e6fb649e2ae4ef7811
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398367"
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
[HANDLETraits::Close](#close)                     | Schließt das angegebene Handle.
[HANDLETraits::GetInvalidValue](#getinvalidvalue) | Stellt ein ungültiges Handle dar.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`HANDLETraits`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="close"></a>HANDLETraits::Close

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

## <a name="getinvalidvalue"></a>HANDLETraits::GetInvalidValue

Stellt ein ungültiges Handle dar.

```cpp
inline static HANDLE GetInvalidValue();
```

### <a name="return-value"></a>Rückgabewert

Gibt immer INVALID_HANDLE_VALUE zurück. (INVALID_HANDLE_VALUE wird von Windows definiert.)
