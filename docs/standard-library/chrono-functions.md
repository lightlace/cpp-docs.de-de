---
title: '&lt;chrono&gt;-Funktionen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- chrono/std::duration_cast
- chrono/std::time_point_cast
ms.assetid: d6800e15-77a1-4df3-900e-d8b2fee190c7
caps.latest.revision: 10
manager: ghogen
ms.openlocfilehash: 91ea7bbec0f86d74cf87ee06b8ec130b13ede83e
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="ltchronogt-functions"></a>&lt;chrono&gt;-Funktionen

||||
|-|-|-|
|[duration_cast](#duration_cast)|[time_point_cast](#time_point_cast)|


## <a name="duration_cast"></a>  duration_cast

Wandelt einen `duration`-Objekt in einen angegebenen Typ um.

```cpp
template <class To, class Rep, class Period>
constexpr To duration_cast(const duration<Rep, Period>& Dur);
```

### <a name="return-value"></a>Rückgabewert

Ein `duration`-Objekt des Typs `To`, der das `Dur` Zeitintervall darstellt, das abgeschnitten wird, wenn es in den Zieltyp passen muss.

### <a name="remarks"></a>Hinweise

Wenn `To` eine Instanziierung von `duration` ist, wird diese Funktion nicht an der Überladungsauflösung beteiligt.

## <a name="time_point_cast"></a>  time_point_cast

Wandelt ein [time_point](../standard-library/time-point-class.md)-Objekt in einen angegebenen Typ um.

```cpp
template <class To, class Clock, class Duration>
time_point<Clock, To> time_point_cast(const time_point<Clock, Duration>& Tp);
```

### <a name="return-value"></a>Rückgabewert

Ein `time_point`-Objekt, das über eine Dauer des Typs `To` verfügt.

### <a name="remarks"></a>Hinweise

Sofern `To` keine Instanziierung von [Dauer](../standard-library/duration-class.md) ist, wird diese Funktion nicht an der Überladungsauflösung beteiligt.

## <a name="see-also"></a>Siehe auch

[\<chrono>](../standard-library/chrono.md)<br/>
