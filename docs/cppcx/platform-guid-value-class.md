---
title: 'Platform:: GUID-Wertklasse | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Guid
dev_langs:
- C++
helpviewer_keywords:
- Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b09fe303cb69cb36d04d696af2b83b30b8378f70
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49083449"
---
# <a name="platformguid-value-class"></a>Platform::Guid-Wertklasse

Stellt einen [GUID](https://msdn.microsoft.com/library/windows/desktop/aa373931) -Typ im Windows Runtime-Typsystem dar.

## <a name="syntax"></a>Syntax

```cpp
public value struct Guid
```

### <a name="members"></a>Member

GUID enthält die Methoden Equals(), GetHashCode() und ToString(), die von der [Platform::Object Class](../cppcx/platform-object-class.md), und die GetTypeCode()-Methode, die von der [Platform::Type Class](../cppcx/platform-type-class.md). Der Guid verfügt auch über die folgenden Member.

|Member|Beschreibung|
|------------|-----------------|
|[Guid](#ctor)|Initialisiert eine neue Instanz der Guid-Struktur.|
|[operator==](#operator-equality)|Entspricht Operator.|
|[Operator!=](#operator-not-equal)|Entspricht nicht Operator.|
|[Operator()](#operator-call)|Konvertiert ein GUID in ein GUID.|

### <a name="remarks"></a>Hinweise

Ein Beispiel für das Generieren einer neuen Platform::Guid mithilfe der Windows-Funktion [CoCreateGuid](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateguid)finden Sie unter [WinRT-Komponente: Wie generiert man eine GUID?](http://blogs.msdn.com/b/eternalcoding/archive/2013/03/25/winrt-component-how-to-generate-a-guid.aspx)

### <a name="requirements"></a>Anforderungen

**Unterstützter Client (Min.):** Windows 8

**Unterstützter Server (Min.):** Windows Server 2012

**Namespace:** Platform

**Metadaten:** platform.winmd

## <a name="ctor"></a> GUID:: GUID-Konstruktoren

Initialisiert eine neue Instanz einer GUID-Struktur.

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
Die ersten 4 Bytes der GUID.

*b*<br/>
Die nächsten 2 Bytes der GUID.

*c*<br/>
Die nächsten 2 Bytes der GUID.

*d*<br/>
Das nächste Byte der GUID.

*e*<br/>
Das nächste Byte der GUID.

*f*<br/>
Das nächste Byte der GUID.

*g*<br/>
Das nächste Byte der GUID.

*h*<br/>
Das nächste Byte der GUID.

*i*<br/>
Das nächste Byte der GUID.

*j*<br/>
Das nächste Byte der GUID.

*k*<br/>
Das nächste Byte der GUID.

*m*<br/>
Eine GUID definiert.

*n*<br/>
Die restlichen 8 Bytes der GUID.

## <a name="operator-equality"></a> GUID::Operator ==-Operator

Vergleicht zwei Guids.

### <a name="syntax"></a>Syntax

```cpp
Platform::Guid::operator==
```

### <a name="return-value"></a>Rückgabewert

True, wenn zwei Guids identisch sind.

## <a name="operator-inequality"></a> GUID::Operator! =-Operator

Vergleicht zwei Guids.

### <a name="syntax"></a>Syntax

```cpp
Platform::Guid::operator!=
```

### <a name="return-value"></a>Rückgabewert

True, wenn die zwei Guids nicht gleich sind.

## <a name="operator-call"></a> GUID::Operator()-Operator

Konvertiert implizit eine [GUID-Struktur](https://msdn.microsoft.com/library/windows/desktop/aa373931)GUID in eine Platform:: GUID.

### <a name="syntax"></a>Syntax

```cpp
Platform::Guid operator();
```

### <a name="return-value"></a>Rückgabewert

Eine GUID-Struktur.

## <a name="see-also"></a>Siehe auch

[Platform-namespace](../cppcx/platform-namespace-c-cx.md)