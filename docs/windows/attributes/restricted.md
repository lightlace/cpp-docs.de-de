---
title: eingeschränkt (C++ COM-Attribut)
ms.date: 10/03/2018
f1_keywords:
- vc-attr.restricted
helpviewer_keywords:
- restricted attribute
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
ms.openlocfilehash: 86f40fa49daf88668e37bef07f0db33d01cf1942
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407353"
---
# <a name="restricted"></a>restricted

Gibt an, dass ein Mitglied aus einem Modul, Schnittstelle oder Disp-Schnittstelle nicht beliebig aufgerufen werden kann.

## <a name="syntax"></a>Syntax

```cpp
[ restricted(
   interfaces
) ]
```

### <a name="parameters"></a>Parameter

*interfaces*<br/>
Eine oder mehrere Schnittstellen, die auf ein COM-Objekt nicht beliebig aufgerufen werden können. Dieser Parameter ist nur gültig, wenn Sie auf eine Klasse angewendet werden.

## <a name="remarks"></a>Hinweise

Die **eingeschränkten** C++-Attribut hat die gleiche Funktionalität wie die [eingeschränkten](/windows/desktop/Midl/restricted) MIDL-Attribut.

## <a name="example"></a>Beispiel

Der folgende Code zeigt, wie Sie mit der **eingeschränkten** Attribut:

```cpp
// cpp_attr_ref_restricted.cpp
// compile with: /LD
#include "windows.h"
#include "unknwn.h"
[module(name="MyLib")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface a
{
};

[object, uuid("00000000-0000-0000-0000-000000000002")]
__interface b
{
};

[coclass, restricted(a,b), uuid("00000000-0000-0000-0000-000000000003")]
class c : public a, public b
{
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|-Schnittstellenmethode, **Schnittstelle**, **Klasse**, **Struktur**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|**Co-Klasse** (bei Anwendung auf **Klasse** oder **Struktur**)|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Schnittstellenattribut](interface-attributes.md)<br/>
[Methodenattribut](method-attributes.md)