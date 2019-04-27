---
title: is_error_condition_enum-Klasse
ms.date: 11/04/2016
f1_keywords:
- system_error/std::is_error_condition_enum
helpviewer_keywords:
- is_error_condition_enum class
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
ms.openlocfilehash: 1b5b55431db806bb109a58199ad9d2d7c16f38ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62162433"
---
# <a name="iserrorconditionenum-class"></a>is_error_condition_enum-Klasse

Stellt ein Typprädikat dar, das auf die [error_code](../standard-library/error-condition-class.md)-Enumeration testet.

## <a name="syntax"></a>Syntax

```cpp
template <_Enum>
class is_error_condition_enum;
```

## <a name="remarks"></a>Hinweise

Eine Instanz dieses [Typprädikats](../standard-library/type-traits.md) ist TRUE, wenn der Typ `_Enum` ein geeigneter Enumerationswert für das Speichern in einem Objekt vom Typ `error_condition` ist.

Es ist zulässig, Spezialisierungen zu dieser Art für benutzerdefinierte Typen hinzuzufügen.

## <a name="requirements"></a>Anforderungen

**Header:** \<system_error>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)<br/>
[<system_error>](../standard-library/system-error.md)<br/>
