---
title: HANDLENullTraits-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/27/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::GetInvalidValue
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits structure
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close method
- Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::GetInvalidValue method
ms.assetid: 88a29a14-c516-40cb-a0ca-ee897a668623
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1060d28e35a52e2a8c5c550664d36d8272628526
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161735"
---
# <a name="handlenulltraits-structure"></a>HANDLENullTraits-Struktur

Definiert die allgemeinen Merkmale eines nicht initialisierten Handles.

## <a name="syntax"></a>Syntax

```cpp
struct HANDLENullTraits;
```

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

Name   | Beschreibung
------ | ---------------------
`Type` | Ein Synonym für den HANDLE.

### <a name="public-methods"></a>Öffentliche Methoden

Name                                                  | Beschreibung
----------------------------------------------------- | -----------------------------
[Handlenulltraits:: Close](#close)                     | Schließt das angegebene Handle.
[Handlenulltraits:: Getinvalidvalue](#getinvalidvalue) | Stellt ein ungültiges Handle dar.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`HANDLENullTraits`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="close"></a>Handlenulltraits:: Close

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

## <a name="getinvalidvalue"></a>Handlenulltraits:: Getinvalidvalue

Stellt ein ungültiges Handle dar.

```cpp
inline static Type GetInvalidValue();
```

### <a name="return-value"></a>Rückgabewert

Gibt immer `nullptr` zurück.
