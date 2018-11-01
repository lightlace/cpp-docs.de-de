---
title: _variant_t-Operatoren (relational)
ms.date: 11/04/2016
f1_keywords:
- _variant_t::operator==
- _variant_t::operator!=
helpviewer_keywords:
- '!= operator'
- relational operators [C++], _variant_t class
- operator!= [C++], variant
- operator!= [C++], relational operators
- operator != [C++], variant
- operator == [C++], variant
- operator== [C++], variant
- operator != [C++], relational operators
- == operator [C++], with specific Visual C++ objects
ms.assetid: 141bacb8-41a2-44dd-b3c0-4ad1f884f4ea
ms.openlocfilehash: e0d26247868440f47c73422510ac0e998f8e8dee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431648"
---
# <a name="variantt-relational-operators"></a>_variant_t-Operatoren (relational)

**Microsoft-spezifisch**

Überprüft zwei `_variant_t`-Objekte auf Gleichheit bzw. Ungleichheit.

## <a name="syntax"></a>Syntax

```
bool operator==(
   const VARIANT& varSrc) const;
bool operator==(
   const VARIANT* pSrc) const;
bool operator!=(
   const VARIANT& varSrc) const;
bool operator!=(
   const VARIANT* pSrc) const;
```

#### <a name="parameters"></a>Parameter

*varSrc*<br/>
Ein `VARIANT` mit verglichen werden soll die `_variant_t` Objekt.

*pSrc*<br/>
Zeiger auf die `VARIANT` mit verglichen werden soll die `_variant_t` Objekt.

## <a name="return-value"></a>Rückgabewert

Gibt **"true"** enthielte Vergleich **"false"** Wenn nicht.

## <a name="remarks"></a>Hinweise

Vergleicht einen `_variant_t` Objekt mit einem `VARIANT`, testet auf Gleichheit oder Ungleichheit.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[_variant_t-Klasse](../cpp/variant-t-class.md)