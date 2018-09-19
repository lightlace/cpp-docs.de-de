---
title: _variant_t-Operatoren (relational) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::operator==
- _variant_t::operator!=
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 95cb1ac663607f26c4f168c2e98910f5b41963c0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040149"
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