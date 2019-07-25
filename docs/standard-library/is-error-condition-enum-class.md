---
title: is_error_condition_enum-Klasse
ms.date: 11/04/2016
f1_keywords:
- system_error/std::is_error_condition_enum
helpviewer_keywords:
- is_error_condition_enum class
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
ms.openlocfilehash: c40f8f6eb93a33098cfbcf8133f08c56285abb43
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452607"
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

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
