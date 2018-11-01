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
ms.openlocfilehash: 7fa95b3037538ccbbf27fa5b9749dc21f72670cd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492694"
---
# <a name="vectorltboolgtreferenceoperator-bool"></a>vector&lt;bool&gt;::reference::operator bool

Stellt eine implizite Konvertierung von `vector<bool>::reference` zu **"bool"**.

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

[Vektor\<Bool >:: reference-Klasse](../standard-library/vector-bool-reference-class.md)<br/>
[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)<br/>
