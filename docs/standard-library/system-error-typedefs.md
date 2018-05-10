---
title: '&lt;system_error&gt;-Typdefinitionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- system_error/std::generic_errno
ms.assetid: 28cf9f7d-9c28-4baa-a297-67c8260b07fb
ms.openlocfilehash: 6dab6e379d2b36ff7e4c2e7cdee581bd43488e41
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
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
