---
title: IsSame-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsSame
- internal/Microsoft::WRL::Details::IsSame::value
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Details::IsSame structure
- Microsoft::WRL::Details::IsSame::value constant
ms.assetid: 1eddbc3f-3cc5-434f-8495-e4477e1f868e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2af59860016835f8e8dfddc9d0a77204ff866bd3
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161852"
---
# <a name="issame-structure"></a>IsSame-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <typename T1, typename T2>
struct IsSame;

template <typename T1>
struct IsSame<T1, T1>;
```

### <a name="parameters"></a>Parameter

*T1*<br/>
Ein Typ.

*T2*<br/>
Einen anderen Typ.

## <a name="remarks"></a>Hinweise

Überprüft, ob es sich bei einem Typ angegeben ist identisch mit einer anderen angegebenen Typ.

## <a name="members"></a>Member

### <a name="public-constants"></a>Öffentliche Konstanten

name                    | Beschreibung
----------------------- | --------------------------------------------------
[Issame:: value](#value) | Gibt an, ob ein Typ mit einer anderen identisch ist.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IsSame`

## <a name="requirements"></a>Anforderungen

**Header:** internal.h

**Namespace:** Microsoft::WRL::Details

## <a name="value"></a>Issame:: value

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
template <typename T1, typename T2>
struct IsSame
{
    static const bool value = false;
};

template <typename T1>
struct IsSame<T1, T1>
{
    static const bool value = true;
};
```

### <a name="remarks"></a>Hinweise

Gibt an, ob ein Typ mit einer anderen identisch ist.

`value` ist **"true"** , wenn die Vorlagenparameter identisch sind und **"false"** Wenn sich die Vorlagenparameter unterscheiden.
