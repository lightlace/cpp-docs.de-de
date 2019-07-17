---
title: is_error_code_enum-Klasse
ms.date: 11/04/2016
f1_keywords:
- system_error/std::is_error_code_enum
helpviewer_keywords:
- is_error_code_enum class
ms.assetid: cee5be2d-7c20-4cec-a352-1ab8b7d32601
ms.openlocfilehash: bc4ed7cd2e058414448c9366011b9efab97ee3d5
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245188"
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

[<type_traits>](../standard-library/type-traits.md)<br/>
