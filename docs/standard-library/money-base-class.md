---
title: money_base-Klasse
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::money_base
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
ms.openlocfilehash: 5b19635cf4d2cce58ec50226c463a075cfac5b0f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455565"
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

In der- `part` Enumeration werden die möglichen Werte in Elementen des Arrayfelds im Struktur Muster beschrieben. Die Werte von `part` lauten:

- `none`, wenn NULL oder mehr Leerzeichen abgeglichen werden sollen

- `sign`, um ein positives oder negatives Vorzeichen abzugleichen oder zu generieren.

- `space`, wenn NULL oder mehr Leerzeichen gefunden werden oder ein Leerzeichen generiert werden soll

- `symbol`, um ein Währungssymbol abzugleichen oder zu generieren.

- `value`, um einen monetären Wert abzugleichen oder zu generieren.

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
