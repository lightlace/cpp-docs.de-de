---
title: Platform::SizeT-Wertklasse
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformSizeT::SizeT constructor
helpviewer_keywords:
- Platform::SizeT Struct
ms.assetid: 0803612c-8ba1-430c-9b7b-1bebae88608d
ms.openlocfilehash: 02fe62165ce40d267f156eaeb3ad93f636c9ab73
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50604216"
---
# <a name="platformsizet-value-class"></a>Platform::SizeT-Wertklasse

Stellt die Größe eines Objekts dar. SizeT ist ein Datentyp ohne Vorzeichen.

## <a name="syntax"></a>Syntax

```cpp
public ref class SizeT sealed : ValueType
```

### <a name="members"></a>Member

|Member|Beschreibung|
|------------|-----------------|
|[SizeT::SizeT-Konstruktor](#ctor)|Initialisiert eine neue Instanz der Klasse mit dem angegebenen Wert.|

### <a name="requirements"></a>Anforderungen

**Unterstützter Client (Min.):** Windows 8

**Unterstützter Server (Min.):** Windows Server 2012

**Namespace:** Platform

**Metadaten:** platform.winmd

## <a name="ctor"></a>  Sizet:: Sizet-Konstruktor

Initialisiert eine neue Instanz von SizeT mit dem angegebenen Wert.

### <a name="syntax"></a>Syntax

```cpp
SizeT( uint32 value1 );   SizeT( void* value2 );
```

### <a name="parameters"></a>Parameter

*Wert1*<br/>
Ein nicht signierter 32-Bit-Wert.

*Wert2*<br/>
Zeiger auf einen nicht signierten 32-Bit-Wert.

## <a name="see-also"></a>Siehe auch

[Platform-namespace](../cppcx/platform-namespace-c-cx.md)