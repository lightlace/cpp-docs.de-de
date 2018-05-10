---
title: duration_values-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- chrono/std::chrono::duration_values
- chrono/std::chrono::duration_values::max
- chrono/std::chrono::duration_values::min
- chrono/std::chrono::duration_values::zero
dev_langs:
- C++
ms.assetid: 7f66d2e3-1faf-47c3-b47e-08f2a87f20e8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d781d04097b205750e7ac65529cfa8ad7b37f9c7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="durationvalues-structure"></a>duration_values-Struktur

Stellt bestimmte Werte für den [duration](../standard-library/duration-class.md)-Vorlagenparameter `Rep` bereit.

## <a name="syntax"></a>Syntax

```cpp
template <class Rep>
struct duration_values;
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[max](#max)|Statisch Gibt die Obergrenze für einen Wert des Typs `Rep` an.|
|[Min.](#min)|Statisch Gibt die Untergrenze für einen Wert des Typs `Rep` an.|
|[zero](#zero)|Statisch Gibt `Rep(0)`zurück.|

## <a name="requirements"></a>Anforderungen

**Header:** \<chrono>

**Namespace:** std::chrono

## <a name="max"></a> duration_values::max

Statische Methode, von der die Obergrenze für Werte vom Typ `Ref` zurückgegeben wird.

```cpp
static constexpr Rep max();
```

### <a name="return-value"></a>Rückgabewert

Tatsächlich wird `numeric_limits<Rep>::max()` zurückgegeben.

### <a name="remarks"></a>Hinweise

Wenn `Rep` ein benutzerdefinierter Typ ist, muss der Rückgabewert größer als [duration_values::zero](#zero) sein.

## <a name="min"></a> duration_values::min

Statische Methode, von der die Untergrenze für Werte vom Typ `Ref` zurückgegeben wird.

```cpp
static constexpr Rep min();
```

### <a name="return-value"></a>Rückgabewert

Tatsächlich wird `numeric_limits<Rep>::lowest()` zurückgegeben.

### <a name="remarks"></a>Hinweise

Wenn `Rep` ein benutzerdefinierter Typ ist, muss der Rückgabewert kleiner oder gleich [duration_values::zero](#zero) sein.

## <a name="zero"></a> duration_values::zero

Gibt `Rep(0)`zurück.

```cpp
static constexpr Rep zero();
```

### <a name="remarks"></a>Hinweise

Wenn `Rep` ein benutzerdefinierter Typ ist, muss der Rückgabewert die additive Infinity darstellen.

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono>](../standard-library/chrono.md)<br/>
