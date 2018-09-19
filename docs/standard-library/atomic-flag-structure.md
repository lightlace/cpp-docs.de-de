---
title: atomic_flag-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- atomic/std::atomic_flag
- atomic/std::atomic_flag::clear
- atomic/std::atomic_flag::test_and_set
dev_langs:
- C++
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f763181424bafc4b8b3af41c135753dbe2f2577b
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44110317"
---
# <a name="atomicflag-structure"></a>atomic_flag-Struktur

Beschreibt ein Objekt, das atomisch festlegt und löscht eine **"bool"** Flag. Vorgänge auf atomischen Flags sind immer sperrenfrei.

## <a name="syntax"></a>Syntax

```cpp
struct atomic_flag;
```

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[clear](#clear)|Legt das gespeicherte Flag auf **"false"**.|
|[test_and_set](#test_and_set)|Legt das gespeicherte Flag auf **"true"** und gibt Sie den ursprünglichen Flagwert zurück.|

## <a name="remarks"></a>Hinweise

`atomic_flag`-Objekte können den Nicht-Member-Funktionen [atomic_flag_clear](../standard-library/atomic-functions.md#atomic_flag_clear), [atomic_flag_clear_explicit](../standard-library/atomic-functions.md#atomic_flag_clear_explicit), [atomic_flag_test_and_set](../standard-library/atomic-functions.md#atomic_flag_test_and_set) und [atomic_flag_test_and_set_explicit](../standard-library/atomic-functions.md#atomic_flag_test_and_set_explicit) übergeben werden. Sie können mithilfe des `ATOMIC_FLAG_INIT`-Werts initialisiert werden.

## <a name="requirements"></a>Anforderungen

**Header:** \<atomic >

**Namespace:** std

## <a name="clear"></a>  atomic_flag:: Clear

Legt die **"bool"** Flag, das in gespeichert ist `*this` zu **"false"**, innerhalb des angegebenen [Memory_order](../standard-library/atomic-enums.md#memory_order_enum) Einschränkungen.

```cpp
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) volatile noexcept;
void atomic_flag::clear(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>Parameter

*Reihenfolge*<br/>
Ein [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

## <a name="test_and_set"></a>  atomic_flag:: test_and_set

Legt die **"bool"** Flag, das in gespeichert ist `*this` zu **"true"**, innerhalb des angegebenen [Memory_order](../standard-library/atomic-enums.md#memory_order_enum) Einschränkungen.

```cpp
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) volatile noexcept;
bool atomic_flag::test_and_set(memory_order Order = memory_order_seq_cst) noexcept;
```

### <a name="parameters"></a>Parameter

*Reihenfolge*<br/>
Ein [memory_order](../standard-library/atomic-enums.md#memory_order_enum).

### <a name="return-value"></a>Rückgabewert

Der Anfangswert des im `*this` gespeicherten Flags.

## <a name="see-also"></a>Siehe auch

[\<atomic>](../standard-library/atomic.md)<br/>
