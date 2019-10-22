---
title: money_base-Klasse
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::money_base
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
ms.openlocfilehash: c614832b0cbb1cc23e42ecb3a939ccf1334a5cea
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689326"
---
# <a name="money_base-class"></a>money_base-Klasse

Die Klasse beschreibt eine Enumeration und eine Struktur, die für alle Spezialisierungs Klassen der Klassen Vorlage [Moneypunct](../standard-library/moneypunct-class.md)gemeinsam ist.

## <a name="syntax"></a>Syntax

```cpp
struct pattern
{
   char field[_PATTERN_FIELD_SIZE];
};
```

## <a name="remarks"></a>Hinweise

Das-Enumerations`part` beschreibt die möglichen Werte in Elementen des Array Felds im Struktur Muster. Die Werte `part` lauten wie folgt:

- `none`, um NULL oder mehr Leerzeichen abzugleichen oder nichts zu generieren.

- `sign`, um ein positives oder negatives Vorzeichen abzugleichen oder zu generieren.

- `space`, um NULL oder mehr Leerzeichen abzugleichen oder ein Leerzeichen zu generieren.

- `symbol`, um ein Währungssymbol abzugleichen oder zu generieren.

- `value`, um einen monetären Wert abzugleichen oder zu generieren.

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)
