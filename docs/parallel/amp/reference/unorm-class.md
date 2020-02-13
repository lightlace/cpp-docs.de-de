---
title: unorm-Klasse
ms.date: 11/04/2016
f1_keywords:
- unorm
- AMP_SHORT_VECTORS/unorm
- AMP_SHORT_VECTORS/Concurrency::graphics::unorm Constructor
ms.assetid: bc30bd20-6452-4d5f-9158-3b11c4c16ed2
ms.openlocfilehash: 7c9ec967be8be618e5f8ab3bad1bfd940bfeaef4
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126304"
---
# <a name="unorm-class"></a>unorm-Klasse

Stellt eine unorm-Zahl dar. Jedes Element ist eine Gleit Komma Zahl im Bereich von [0,0 f, 1.0 f].

## <a name="syntax"></a>Syntax

```cpp
class unorm;
```

## <a name="members"></a>Members

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|[unorm-Konstruktor](#ctor)|Ist überladen. Der Standardkonstruktor. Initialisieren Sie den Wert 0,0 f.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|BESCHREIBUNG|
|----------|-----------------|
|unorm:: Operator--||
|unorm:: Operator float|Konvertierungs Operator. Konvertieren Sie die unorm-Zahl in einen Gleit Komma Wert.|
|unorm:: Operator * =||
|unorm:: Operator/=||
|unorm::operator++||
|unorm::operator+=||
|unorm::operator=||
|unorm:: Operator-=||

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`unorm`

## <a name="requirements"></a>Requirements (Anforderungen)

**Header:** amp_short_vectors. h

**Namespace:** Parallelität:: Grafiken

## <a name="ctor"></a>unorm

Der Standardkonstruktor. Initialisieren Sie den Wert 0,0 f.

```cpp
unorm(
    void) restrict(amp,
    cpu);

explicit unorm(
    float _V) restrict(amp,
    cpu);

explicit unorm(
    unsigned int _V) restrict(amp,
    cpu);

explicit unorm(
    int _V) restrict(amp,
    cpu);

explicit unorm(
    double _V) restrict(amp,
    cpu);

unorm(
    const unorm& _Other) restrict(amp,
    cpu);

inline explicit unorm(
    const norm& _Other) restrict(amp,
    cpu);
```

### <a name="parameters"></a>Parameter

*_V*<br/>
Der Wert, der zum Initialisieren von verwendet wird.

*_Other*<br/>
Das Norm Objekt, das zum Initialisieren von verwendet wird.

## <a name="see-also"></a>Weitere Informationen

[Concurrency::graphics Namespace](concurrency-graphics-namespace.md)
