---
title: is_error_code_enum-Struktur
ms.date: 11/04/2016
f1_keywords:
- future/std::is_error_code_enum
ms.assetid: 84ae4b99-66d2-41ba-9b50-645fcbe14630
ms.openlocfilehash: 54def287aa6b4bbb06d88006615b5df45b482051
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62336582"
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

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<future>](../standard-library/future.md)<br/>
