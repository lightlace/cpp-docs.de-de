---
title: nullopt_t-Struktur
ms.date: 08/04/2019
f1_keywords:
- optional/std::nullopt_t
- optional/std::nullopt
ms.openlocfilehash: 1f453a5d75de3f6dedb133d55c094a4f4274e08f
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2019
ms.locfileid: "68957045"
---
# <a name="nullopt_t-struct"></a>nullopt_t-Struktur

Der `nullopt_t` Typ ist ein eindeutiger, leerer Typ, mit dem angegeben wird, dass ein [optionales](optional-class.md) Objekt keinen Wert enthält.

Die Konstante `nullopt` vom Typ `nullopt_t` gibt an `optional` , dass ein Typ einen nicht initialisierten Zustand aufweist. Sie kann verwendet werden, um ein `optional` Objekt zu initialisieren oder mit einem Objekt zu vergleichen.

## <a name="syntax"></a>Syntax

```cpp
struct nullopt_t;
inline constexpr nullopt_t nullopt{ /*implementation-defined*/ };
```

## <a name="see-also"></a>Siehe auch

[\<optionale >](optional.md)\
[optionale Klasse](optional-class.md)
