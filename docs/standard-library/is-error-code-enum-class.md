---
title: is_error_code_enum-Klasse
ms.date: 11/04/2016
f1_keywords:
- system_error/std::is_error_code_enum
helpviewer_keywords:
- is_error_code_enum class
ms.assetid: cee5be2d-7c20-4cec-a352-1ab8b7d32601
ms.openlocfilehash: 4080c62034b224a9553eca2787aa1c2f2cf69ab8
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454630"
---
# <a name="iserrorcodeenum-class"></a>is_error_code_enum-Klasse

Stellt ein Typprädikat dar, das auf die [error_code](../standard-library/error-code-class.md)-Enumeration testet.

## <a name="syntax"></a>Syntax

```cpp
template <_Enum>
    class is_error_code_enum;
```

## <a name="remarks"></a>Hinweise

Eine Instanz dieses [Typprädikats](../standard-library/type-traits.md) ist TRUE, wenn der Typ `_Enum` ein geeigneter Enumerationswert für das Speichern in einem Objekt vom Typ `error_code` ist.

Es ist zulässig, Spezialisierungen zu dieser Art für benutzerdefinierte Typen hinzuzufügen.

## <a name="see-also"></a>Siehe auch

[<type_traits>](../standard-library/type-traits.md)
