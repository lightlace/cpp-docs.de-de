---
title: time_base-Klasse
ms.date: 11/04/2016
f1_keywords:
- locale/std::time_base
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
ms.openlocfilehash: 85565dc0c0ec904551eb8dd981cfacc9a2e1f256
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460040"
---
# <a name="timebase-class"></a>time_base-Klasse

Die-Klasse fungiert als Basisklasse für Facetten der Vorlagen Klasse Time_get, die nur den enumerierten `dateorder` Typ und mehrere Konstanten dieses Typs definiert.

## <a name="syntax"></a>Syntax

```cpp
class time_base : public locale::facet {
public:
    enum dateorder {
        no_order,
        dmy,
        mdy,
        ymd,
        ydm
    };
    time_base(size_t _Refs = 0)
    ~time_base();
};
```

## <a name="remarks"></a>Hinweise

Jede Konstante kennzeichnet eine andere Möglichkeit, die Komponenten eines Datums zu ordnen. Es gibt folgende Konstanten:

- `no_order`gibt keine bestimmte Reihenfolge an.

- `dmy`Gibt den Bestell Tag, den Monat und das Jahr an, wie im 2. Dezember 1979.

- `mdy`Gibt den Bestell Monat, den Tag und das Jahr an, wie im 2. Dezember 1979.

- `ymd`Gibt das Bestell Jahr, den Monat, den Tag, wie in 1979/12/2 an.

- `ydm`Gibt das Bestell Jahr, den Tag, den Monat, wie in 1979 an: 2. Dez.

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
