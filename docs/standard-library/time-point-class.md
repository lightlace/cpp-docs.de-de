---
title: time_point-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- chrono/std::chrono::time_point
- chrono/std::chrono::time_point::time_point
- chrono/std::chrono::time_point::max
- chrono/std::chrono::time_point::min
- chrono/std::chrono::time_point::time_since_epoch
dev_langs:
- C++
ms.assetid: 18be1e52-57b9-489a-8a9b-f58894f0aaad
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::chrono [C++], time_point
ms.workload:
- cplusplus
ms.openlocfilehash: 72ce06a3f722bca0147d220fb8602ab9e30f8751
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44319018"
---
# <a name="timepoint-class"></a>time_point-Klasse

Mit `time_point` wird ein Typ beschrieben, der einen bestimmten Zeitpunkt darstellt. Er enthält ein Objekt des Typs [duration](../standard-library/duration-class.md), in dem die verstrichene Zeit seit dem vom Vorlagenargument `Clock` dargestellten Zeitraum gespeichert ist.

## <a name="syntax"></a>Syntax

```cpp
template <class Clock,
    class Duration = typename Clock::duration>
class time_point;
```

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`time_point::clock`|Synonym für den Vorlagenparameter `Clock`.|
|`time_point::duration`|Synonym für den Vorlagenparameter `Duration`.|
|`time_point::period`|Synonym für den Namen `duration::period` des geschachtelten Typ.|
|`time_point::rep`|Synonym für den Namen `duration::rep` des geschachtelten Typ.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[time_point](#time_point)|Erstellt ein `time_point`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[max](#max)|Gibt die Obergrenze für `time_point::ref` an.|
|[Min.](#min)|Gibt die Untergrenze für `time_point::ref` an.|
|[time_since_epoch](#time_since_epoch)|Gibt den gespeicherten `duration`-Wert zurück.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[time_point::operator+=](#op_add_eq)|Fügt der gespeicherten Dauer einen angegebenen Wert hinzu.|
|[time_point::operator-=](#operator-_eq)|Subtrahiert einen angegebenen Wert von der gespeicherten Dauer.|

## <a name="requirements"></a>Anforderungen

**Header:** \<chrono>

**Namespace:** std::chrono

## <a name="max"></a>  time_point:: Max

Statische Methode, von der die Obergrenze für Werte vom Typ `time_point::ref` zurückgegeben wird.

```cpp
static constexpr time_point max();
```

### <a name="return-value"></a>Rückgabewert

Tatsächlich wird `time_point(duration::max())` zurückgegeben.

## <a name="min"></a>  time_point:: Min

Statische Methode, von der die Untergrenze für Werte vom Typ `time_point::ref` zurückgegeben wird.

```cpp
static constexpr time_point min();
```

### <a name="return-value"></a>Rückgabewert

Tatsächlich wird `time_point(duration::min())` zurückgegeben.

## <a name="op_add_eq"></a> time_point::operator+=

Fügt dem gespeicherten [duration](../standard-library/duration-class.md)-Wert einen angegebenen Wert hinzu.

```cpp
time_point& operator+=(const duration& Dur);
```

### <a name="parameters"></a>Parameter

*Abfragedauer*  
 Ein `duration`-Objekt.

### <a name="return-value"></a>Rückgabewert

Das `time_point`-Objekt nach Ausführung der Addition.

## <a name="time_point__operator-_eq"></a> time_point::operator-=

Subtrahiert einen angegebenen Wert vom gespeicherten [duration](../standard-library/duration-class.md)-Wert.

```cpp
time_point& operator-=(const duration& Dur);
```

### <a name="parameters"></a>Parameter

*Abfragedauer*  
 Ein `duration`-Objekt.

### <a name="return-value"></a>Rückgabewert

Das `time_point`-Objekt nach Ausführung der Subtraktion.

## <a name="time_point"></a> time_point::time_point-Konstruktor

Erstellt ein `time_point`-Objekt.

```cpp
constexpr time_point();

constexpr explicit time_point(const duration& Dur);

template <class Duration2>
constexpr time_point(const time_point<clock, Duration2>& Tp);
```

### <a name="parameters"></a>Parameter

*Abfragedauer*  
 Ein [duration](../standard-library/duration-class.md)-Objekt.

*TP*  
 Ein `time_point`-Objekt.

### <a name="remarks"></a>Hinweise

Mit dem ersten Konstruktor wird ein Objekt erstellt, dessen gespeicherter `duration`-Wert [duration::zero](../standard-library/duration-class.md#zero) entspricht.

Der zweite Konstruktor erstellt ein Objekt, dessen gespeicherte Duration-Wert gleich ist *Dur*. Es sei denn, `is_convertible<Duration2, duration>` enthält "true", der zweite Konstruktor nicht an der überladungsauflösung beteiligt. Weitere Informationen finden Sie unter [<type_traits>](../standard-library/type-traits.md).

Mit dem dritten Konstruktor wird der `duration`-Wert initialisiert, indem `Tp.time_since_epoch()` verwendet wird.

## <a name="time_since_epoch"></a>  time_point:: time_since_epoch

Ruft den gespeicherten [duration](../standard-library/duration-class.md)-Wert ab.

```cpp
constexpr duration time_since_epoch() const;
```

## <a name="see-also"></a>Siehe auch

[Headerdateienreferenz](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono>](../standard-library/chrono.md)<br/>
