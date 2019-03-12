---
title: Platform::Guid-Wertklasse
ms.date: 01/15/2019
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Guid
helpviewer_keywords:
- Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
ms.openlocfilehash: 64c70b619380d7c2ed4aaaecad3ee01a1d0f79c7
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57743804"
---
# <a name="platformguid-value-class"></a>Platform::Guid-Wertklasse

Stellt einen [GUID](https://msdn.microsoft.com/library/windows/desktop/aa373931) -Typ im Windows Runtime-Typsystem dar.

## <a name="syntax"></a>Syntax

```cpp
public value struct Guid
```

### <a name="members"></a>Member

`Platform::Guid` hat die `Equals()`, `GetHashCode()`, und `ToString()` ToString()", die von der [Platform:: Object Class](../cppcx/platform-object-class.md), und die `GetTypeCode()` Methode abgeleitet der [Platform:: Type Class](../cppcx/platform-type-class.md). `Platform::Guid` Außerdem weist die folgenden Member.

|Member|Beschreibung|
|------------|-----------------|
|[Guid](#ctor)|Initialisiert eine neue Instanz von `Platform::Guid`.|
|[operator==](#operator-equality)|Entspricht Operator.|
|[Operator!=](#operator-inequality)|Entspricht nicht Operator.|
|[operator&lt;](#operator-less)|Kleiner als-Operator.|
|[Operator()](#operator-call)|Konvertiert ein `Platform::Guid` -Element in ein `GUID`-Element.|

### <a name="remarks"></a>Hinweise

Um eine neue `Platform::Guid`, verwenden Sie die [Windows::Foundation::GuidHelper::CreateNewGuid](/uwp/api/windows.foundation.guidhelper.createnewguid#Windows_Foundation_GuidHelper_CreateNewGuid) statische Methode.

### <a name="requirements"></a>Anforderungen

**Unterstützter Client (Min.):** Windows 8

**Unterstützter Server (Min.):** Windows Server 2012

**Namespace:** Plattform

**Metadaten:** platform.winmd

## <a name="ctor"></a> GUID:: GUID-Konstruktoren

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
Die ersten 4 Bytes, der die `GUID`.

*b*<br/>
Die nächsten 2 Bytes, der die `GUID`.

*c*<br/>
Die nächsten 2 Bytes, der die `GUID`.

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
Ein `GUID` in Form einer [GUID-Struktur](https://msdn.microsoft.com/library/windows/desktop/aa373931).

*n*<br/>
Die restlichen 8 Bytes, der die `GUID`.

## <a name="operator-equality"></a> GUID::Operator ==-Operator

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

True, wenn die beiden `Platform::Guid` -Instanzen gleich sind.

### <a name="remarks"></a>Hinweise

Lieber die `==` Operator anstelle des dem [Windows::Foundation::GuidHelper::Equals](/uwp/api/windows.foundation.guidhelper.equals) statische Methode.

## <a name="operator-inequality"></a> GUID::Operator! =-Operator

Vergleicht zwei `Platform::Guid` -Instanzen auf Ungleichheit.

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

True, wenn die beiden `Platform::Guid` -Instanzen ungleich sind.

## <a name="operator-less"></a> GUID::Operator&lt; Operator

Vergleicht zwei `Platform::Guid` Instanzen für die Sortierung.

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

True, wenn *guid1* sortiert ist, bevor Sie *guid2*. Die Sortierung nach behandelt jede lexikografischen ist `Platform::Guid` , als ob es sich um ein Array von vier 32-Bit-Werten ohne Vorzeichen ist. Dies ist nicht die Sortierung von SQL Server oder .NET Framework verwendet werden, noch entspricht sie dem lexikografische Reihenfolge durch die Zeichenfolgendarstellung.

Dieser Operator wird bereitgestellt, damit `Guid` Objekte können leichter von der C++-Standardbibliothek genutzt werden.

## <a name="operator-call"></a> GUID::Operator()-Operator

Konvertiert implizit eine `Platform::Guid` zu einem [GUID-Struktur](https://msdn.microsoft.com/library/windows/desktop/aa373931).

### <a name="syntax"></a>Syntax

```cpp
const GUID& Platform::Guid::operator();
```

### <a name="return-value"></a>Rückgabewert

Ein [GUID-Struktur](https://msdn.microsoft.com/library/windows/desktop/aa373931).

## <a name="see-also"></a>Siehe auch

[Platform-namespace](../cppcx/platform-namespace-c-cx.md)
