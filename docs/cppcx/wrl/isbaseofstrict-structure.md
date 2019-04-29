---
title: IsBaseOfStrict-Struktur
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict
- internal/Microsoft::WRL::Details::IsBaseOfStrict::value
helpviewer_keywords:
- Microsoft::WRL::Details::IsBaseOfStrict structure
- Microsoft::WRL::Details::IsBaseOfStrict::value constant
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
ms.openlocfilehash: 85aeb71ceaa162cc6366836dd286f2f9983d34e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386017"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <typename Base, typename Derived>
struct IsBaseOfStrict;

template <typename Base>
struct IsBaseOfStrict<Base, Base>;
```

### <a name="parameters"></a>Parameter

*Basis*<br/>
Der Basistyp.

*Abgeleitete*<br/>
Der abgeleitete Typ.

## <a name="remarks"></a>Hinweise

Testet, ob ein Typ die Basis eines anderen ist.

Die erste Vorlage testet, ob ein Typ von einem Basistyp abgeleitet ist, die ergeben können **"true"** oder **"false"**. Die zweite Vorlage testet, ob ein Typ von sich selbst zu abgeleitet ist, die führt zu immer **"false"**.

## <a name="members"></a>Member

### <a name="public-constants"></a>Öffentliche Konstanten

Name                            | Beschreibung
------------------------------- | --------------------------------------------------
[IsBaseOfStrict::value](#value) | Gibt an, ob ein Typ die Basis eines anderen ist.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`IsBaseOfStrict`

## <a name="requirements"></a>Anforderungen

**Header:** internal.h

**Namespace:** Microsoft::WRL::Details

## <a name="value"></a>IsBaseOfStrict::value

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

```cpp
static const bool value = __is_base_of(Base, Derived);
```

### <a name="remarks"></a>Hinweise

Gibt an, ob ein Typ die Basis eines anderen ist.

`value` ist **"true"** Wenn Typ `Base` ist eine Basisklasse des Typs `Derived`, ansonsten ist der **"false"**.
