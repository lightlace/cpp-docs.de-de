---
title: is_error_code_enum-Struktur
ms.date: 11/04/2016
f1_keywords:
- future/std::is_error_code_enum
ms.assetid: 84ae4b99-66d2-41ba-9b50-645fcbe14630
ms.openlocfilehash: 54def287aa6b4bbb06d88006615b5df45b482051
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676420"
---
# <a name="iserrorcodeenum-structure"></a>is_error_code_enum-Struktur

Spezialisierung, die angibt, dass [future_errc](../standard-library/future-enums.md#future_errc) für das Speichern eines [error_code](../standard-library/error-code-class.md) geeignet ist.

## <a name="syntax"></a>Syntax

```cpp
template <>
struct is_error_code_enum<Future_errc> : public true_type;
```

## <a name="requirements"></a>Anforderungen

**Header:** \<zukünftige >

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<future>](../standard-library/future.md)<br/>
