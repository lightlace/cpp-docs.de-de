---
title: vector&lt;bool&gt;::reference::operator bool
ms.date: 11/04/2016
f1_keywords:
- operatorbool
- vector<bool>::reference::operatorbool
- bool
- std::vector<bool>::reference::operatorbool
helpviewer_keywords:
- BOOL operator
- reference::operator bool
ms.assetid: b0e57869-18cc-4296-9061-da502f30120d
ms.openlocfilehash: ca2d21a7706248cd84ca3591eb717e4081972f9c
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452120"
---
# <a name="vectorltboolgtreferenceoperator-bool"></a>vector&lt;bool&gt;::reference::operator bool

Stellt eine implizite Konvertierung von `vector<bool>::reference` in **bool**bereit.

## <a name="syntax"></a>Syntax

```cpp
operator bool() const;
```

## <a name="return-value"></a>Rückgabewert

Der boolesche Wert des Elements des [vector\<bool>](../standard-library/vector-bool-class.md)-Objekts.

## <a name="remarks"></a>Hinweise

Das `vector<bool>`-Objekt kann von diesem Operator nicht geändert werden.

## <a name="requirements"></a>Anforderungen

**Header:** \<vector>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[vector\<bool>::reference-Klasse](../standard-library/vector-bool-reference-class.md)\
[C++ Standard Library Reference (C++-Standardbibliotheksreferenz)](../standard-library/cpp-standard-library-reference.md)
