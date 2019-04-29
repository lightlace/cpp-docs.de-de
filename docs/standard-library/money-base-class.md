---
title: money_base-Klasse
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::money_base
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
ms.openlocfilehash: b0c77b523dbe31bc5b07ae3d736441880fe04546
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383567"
---
# <a name="moneybase-class"></a>money_base-Klasse

Die Klasse beschreibt eine Enumeration und eine Struktur, die für alle Spezialisierungen der Vorlagenklasse [moneypunct](../standard-library/moneypunct-class.md) gebräuchlich ist.

## <a name="syntax"></a>Syntax

```cpp
struct pattern
{
   char field[_PATTERN_FIELD_SIZE];
};
```

## <a name="remarks"></a>Hinweise

Die Enumeration `part` beschreibt die möglichen Werte in Elementen des Array-Felds im strukturmuster. Die Werte der `part` sind:

- `none` auf NULL oder mehr Leerzeichen abzustimmen bzw. nichts zu generieren.

- `sign` übereinstimmen oder ein positiven oder negativen Vorzeichen zu generieren.

- `space` NULL oder mehr Leerzeichen abzustimmen, oder ein Leerzeichen zu generieren.

- `symbol` übereinstimmen oder ein Währungssymbol zu generieren.

- `value` Um abzustimmen bzw. einen monetären Wert zu generieren.

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
