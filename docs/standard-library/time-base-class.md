---
title: time_base-Klasse
ms.date: 11/04/2016
f1_keywords:
- locale/std::time_base
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
ms.openlocfilehash: ddaf9905e859c062031940d35adfa2a3393dbb5a
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2019
ms.locfileid: "72685787"
---
# <a name="time_base-class"></a>time_base-Klasse

Die-Klasse fungiert als Basisklasse für Facetten der Klassen Vorlagen Time_get, die nur den enumerierten Typ `dateorder` und mehrere Konstanten dieses Typs definiert.

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

- `no_order` gibt keine bestimmte Reihenfolge an.

- `dmy` gibt den Order Day, month, year, wie in 2. Dezember 1979 an.

- `mdy` gibt den Bestell Monat, den Tag und das Jahr an, wie im 2. Dezember 1979.

- `ymd` gibt das Bestell Jahr, den Monat, den Tag, wie in 1979/12/2 an.

- `ydm` gibt das Bestell Jahr, den Tag, den Monat, wie in 1979:2 Dec an.

## <a name="requirements"></a>Anforderungen

**Header:** \<locale>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Thread Safety in the C++ Standard Library (Threadsicherheit in der C++-Standardbibliothek)](../standard-library/thread-safety-in-the-cpp-standard-library.md)
