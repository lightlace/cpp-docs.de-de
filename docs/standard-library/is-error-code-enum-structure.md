---
title: is_error_code_enum-Struktur
ms.date: 11/04/2016
f1_keywords:
- future/std::is_error_code_enum
ms.assetid: 84ae4b99-66d2-41ba-9b50-645fcbe14630
ms.openlocfilehash: f2a9f0d6b812b430ba3fca2d39343f912791da6f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452611"
---
# <a name="iserrorcodeenum-structure"></a>is_error_code_enum-Struktur

Spezialisierung, die angibt, dass [future_errc](../standard-library/future-enums.md#future_errc) für das Speichern eines [error_code](../standard-library/error-code-class.md) geeignet ist.

## <a name="syntax"></a>Syntax

```cpp
template <>
struct is_error_code_enum<Future_errc> : public true_type;
```

## <a name="requirements"></a>Anforderungen

**Header:** \<future>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)\
[\<future>](../standard-library/future.md)
