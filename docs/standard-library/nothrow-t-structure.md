---
title: nothrow_t-Struktur
ms.date: 11/04/2016
f1_keywords:
- nothrow_t
helpviewer_keywords:
- nothrow_t class
ms.assetid: dc7d5d42-ed5a-4919-88fe-bbad519b7a1d
ms.openlocfilehash: bd65b5006326850522a251cbcf7d655133a1aa8a
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245583"
---
# <a name="nothrowt-structure"></a>nothrow_t-Struktur

Die Struktur wird als Funktionsparameter für „operator new“ verwendet, um anzugeben, dass die Funktion zum Melden eines Zuordnungsfehlers keine Ausnahme auslösen, sondern einen NULL-Zeiger zurückgeben soll.

## <a name="syntax"></a>Syntax

```cpp
struct std::nothrow_t {};
```

## <a name="remarks"></a>Hinweise

Die Struktur hilft dem Compiler beim Auswählen der richtigen Version des Konstruktors. [nothrow](../standard-library/new-functions.md#nothrow) ist ein Synonym für Objekte des Typs `std::nothrow_t`.

## <a name="example"></a>Beispiel

Beispiele zur Verwendung von `std::nothrow_t` als Funktionsparameter finden Sie unter [operator new](../standard-library/new-operators.md#op_new) und [operator new&#91;&#93;](../standard-library/new-operators.md#op_new_arr).
