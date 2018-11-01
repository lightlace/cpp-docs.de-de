---
title: '&lt;sstem_error&gt; Typdefinitionen'
ms.date: 11/04/2016
f1_keywords:
- system_error/std::generic_errno
ms.assetid: 28cf9f7d-9c28-4baa-a297-67c8260b07fb
ms.openlocfilehash: 95b2cb22d4fbff4f92cf28041e70ae599c318cbc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531055"
---
# <a name="ltsystemerrorgt-typedefs"></a>&lt;sstem_error&gt; Typdefinitionen

||
|-|
|[generic_errno](#generic_errno)|

## <a name="generic_errno"></a> generic_errno

Ein Typ, der die Enumeration darstellt, die die symbolischen Namen für alle von Posix in `<errno.h>` definierten Fehlercodemakros bietet.

```cpp
typedef errc generic_error;
```

### <a name="remarks"></a>Hinweise

Der Typ ist ein Synonym für [errc](../standard-library/system-error-enums.md#errc).

## <a name="see-also"></a>Siehe auch

[<system_error>](../standard-library/system-error.md)<br/>
