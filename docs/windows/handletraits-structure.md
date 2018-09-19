---
title: HANDLETraits-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits
dev_langs:
- C++
helpviewer_keywords:
- HANDLETraits structure
ms.assetid: 22963e88-d857-4624-9182-7c986daff722
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c2193743da9e7b5667714650660cd8e1efdb5cf4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610980"
---
# <a name="handletraits-structure"></a>HANDLETraits-Struktur

Definiert die allgemeinen Merkmale eines Handles.

## <a name="syntax"></a>Syntax

```cpp
struct HANDLETraits;
```

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`Type`|Ein Synonym für den HANDLE.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[HANDLETraits::Close-Methode](../windows/handletraits-close-method.md)|Schließt das angegebene Handle.|
|[HANDLETraits::GetInvalidValue-Methode](../windows/handletraits-getinvalidvalue-method.md)|Stellt ein ungültiges Handle dar.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`HANDLETraits`

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Wrappers::HandleTraits-Namespace](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)