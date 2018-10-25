---
title: eingeschränkt (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.restricted
dev_langs:
- C++
helpviewer_keywords:
- restricted attribute
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb13132c651323fcdffef2c06215314ad193c91d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071101"
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