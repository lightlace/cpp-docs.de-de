---
title: bad_optional_access-Klasse
ms.date: 08/06/2019
f1_keywords:
- optional/std::bad_optional_access
ms.openlocfilehash: 043b0360c7e0be48267c8f406dbfea50eeb5a8e3
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2019
ms.locfileid: "68957104"
---
# <a name="bad_optional_access-class"></a>bad_optional_access-Klasse

Definiert den Typ von Objekten, die als Ausnahmen ausgelöst werden, um die Situation zu melden, in der versucht wird, `optional` auf den Wert eines Objekts zuzugreifen, das keinen Wert enthält.

## <a name="syntax"></a>Syntax

```cpp
class bad_optional_access : public exception
{
public:
    bad_optional_access() noexcept;
    bad_optional_access(const bad_optional_access&) noexcept;
    bad_optional_access& operator=(const bad_optional_access&) noexcept;
    const char* what() const noexcept override;
};
```

## <a name="see-also"></a>Siehe auch

[\<optionale >](optional.md)\
[optionale Klasse](optional-class.md)
