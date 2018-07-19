---
title: money_base-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocmon/std::money_base
dev_langs:
- C++
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3195d2c988abcfb2d62acb4ece957c8c5156bbd7
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965687"
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
