---
title: Platform::Guid-Wertklasse
ms.date: 01/15/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Guid
helpviewer_keywords:
- Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
ms.openlocfilehash: f63b2bb4fd5f809861622a4f6b255ee3725564b6
ms.sourcegitcommit: 4517932a67bbf2db16cfb122d3bef57a43696242
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/02/2019
ms.locfileid: "71816590"
---
# <a name="platformguid-value-class"></a>Platform::Guid-Wertklasse

Stellt einen [GUID](/previous-versions/cc317743(v%3dmsdn.10)) -Typ im Windows Runtime-Typsystem dar.

## <a name="syntax"></a>Syntax

```cpp
public value struct Guid
```

### <a name="members"></a>Member

`Platform::Guid` verfügt über die Methoden `Equals()`, `GetHashCode()`und `ToString()`, die von der [Platform:: Object-Klasse](../cppcx/platform-object-class.md)abgeleitet werden, und die `GetTypeCode()`-Methode, die von der [Platform:: Type-Klasse](../cppcx/platform-type-class.md)abgeleitet wurde. `Platform::Guid` verfügt auch über die folgenden Member.

|Member|Beschreibung|
|------------|-----------------|
|[Guid](#ctor)|Initialisiert eine neue Instanz von `Platform::Guid`.|
|[operator==](#operator-equality)|Entspricht Operator.|
|[operator!=](#operator-inequality)|Entspricht nicht Operator.|
|[operator&lt;](#operator-less)|Kleiner als-Operator.|
|[Operator()](#operator-call)|Konvertiert ein `Platform::Guid` -Element in ein `GUID`-Element.|

### <a name="remarks"></a>Hinweise

Verwenden Sie die statische Methode [Windows:: Foundation:: GuidHelper:: kreatenewguid](/uwp/api/windows.foundation.guidhelper.createnewguid#Windows_Foundation_GuidHelper_CreateNewGuid) , um eine neue `Platform::Guid`zu generieren.

### <a name="requirements"></a>Voraussetzungen

**Mindestens unterstützter Client:** Windows 8

**Mindestens unterstützter Server:** Windows Server 2012

**Namespace:** Platform

**Metadaten:** platform.winmd

## <a name="ctor"></a>GUID:: GUID-Konstruktoren

Initialisiert eine neue Instanz von `Platform::Guid`.

### <a name="syntax"></a>Syntax

```cpp
Guid(
    unsigned int a,
    unsigned short b,
    unsigned short c,
    unsigned char d,
    unsigned char e,
    unsigned char f,
    unsigned char g,
    unsigned char h,
    unsigned char i,
    unsigned char j,
    unsigned char k );

Guid(GUID m);

Guid(
    unsigned int a,
    unsigned short b,
    unsigned short c,
    Array<unsigned char>^ n );
```

### <a name="parameters"></a>Parameter

*a*<br/>
Die ersten 4 Bytes der `GUID`.

*b*<br/>
Die nächsten 2 Bytes der `GUID`.

*c*<br/>
Die nächsten 2 Bytes der `GUID`.

*d*<br/>
Das nächste Byte der `GUID`.

*e*<br/>
Das nächste Byte der `GUID`.

*f*<br/>
Das nächste Byte der `GUID`.

*g*<br/>
Das nächste Byte der `GUID`.

*h*<br/>
Das nächste Byte der `GUID`.

*i*<br/>
Das nächste Byte der `GUID`.

*j*<br/>
Das nächste Byte der `GUID`.

*k*<br/>
Das nächste Byte der `GUID`.

*m*<br/>
Eine `GUID` in der Form einer [GUID-Struktur](/previous-versions/cc317743(v%3dmsdn.10)).

*n*<br/>
Die restlichen 8 Bytes der `GUID`.

## <a name="operator-equality"></a>GUID:: Operator = =-Operator

Überprüft zwei `Platform::Guid`-Instanzen auf Gleichheit.

### <a name="syntax"></a>Syntax

```cpp
static bool Platform::Guid::operator==(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Parameter

*guid1*<br/>
Der erste zu vergleichende `Platform::Guid`.

*guid2*<br/>
Der zweite zu vergleichende `Platform::Guid`.

### <a name="return-value"></a>Rückgabewert

True, wenn die beiden `Platform::Guid` Instanzen gleich sind.

### <a name="remarks"></a>Hinweise

Bevorzugen Sie die Verwendung des `==` Operators anstelle der statischen Methode [Windows:: Foundation:: GuidHelper:: Gleichheits](/uwp/api/windows.foundation.guidhelper.equals) Methode.

## <a name="operator-inequality"></a>GUID:: Operator! =-Operator

Vergleicht zwei `Platform::Guid`-Instanzen auf Ungleichheit.

### <a name="syntax"></a>Syntax

```cpp
static bool Platform::Guid::operator!=(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Parameter

*guid1*<br/>
Der erste zu vergleichende `Platform::Guid`.

*guid2*<br/>
Der zweite zu vergleichende `Platform::Guid`.

### <a name="return-value"></a>Rückgabewert

True, wenn die beiden `Platform::Guid` Instanzen nicht gleich sind.

## <a name="operator-less"></a>GUID:: Operator&lt;-Operator

Vergleicht zwei `Platform::Guid`-Instanzen für die Reihenfolge.

### <a name="syntax"></a>Syntax

```cpp
static bool Platform::Guid::operator<(Platform::Guid guid1, Platform::Guid guid2);
```

### <a name="parameters"></a>Parameter

*guid1*<br/>
Der erste zu vergleichende `Platform::Guid`.

*guid2*<br/>
Der zweite zu vergleichende `Platform::Guid`.

### <a name="return-value"></a>Rückgabewert

True, wenn *guid1* vor *GUID2*geordnet ist. Die Reihenfolge ist lexikografisch, nachdem Sie die einzelnen `Platform::Guid` behandelt haben, als ob es sich um ein Array von 4 32-Bit-Werten ohne Vorzeichen handelt. Dabei handelt es sich nicht um die Reihenfolge, die von SQL Server oder der .NET Framework verwendet wird, ebenso wie die lexikografische Reihenfolge nach Zeichen folgen Darstellung.

Dieser Operator wird bereitgestellt, damit `Guid` Objekte leichter von der C++ Standardbibliothek genutzt werden können.

## <a name="operator-call"></a>GUID:: Operator ()-Operator

Konvertiert eine `Platform::Guid` implizit in eine [GUID-Struktur](/previous-versions/cc317743(v%3dmsdn.10)).

### <a name="syntax"></a>Syntax

```cpp
const GUID& Platform::Guid::operator();
```

### <a name="return-value"></a>Rückgabewert

Eine [GUID-Struktur](/previous-versions/cc317743(v%3dmsdn.10)).

## <a name="see-also"></a>Siehe auch

[Plattformnamespace](../cppcx/platform-namespace-c-cx.md)
