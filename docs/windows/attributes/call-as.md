---
title: Call_as (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.call_as
helpviewer_keywords:
- call_as attribute
ms.assetid: a09d7f1f-353b-4870-9b45-f0284161695d
ms.openlocfilehash: f36cf8d1be589cc614a6def583b00af00aabdb61
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501806"
---
# <a name="call_as"></a>call_as

Ermöglicht, dass eine [lokale](local-cpp.md) Funktion einer Remote Funktion zugeordnet werden kann, sodass die lokale Funktion aufgerufen wird, wenn die Remote Funktion aufgerufen wird.

## <a name="syntax"></a>Syntax

```cpp
[ call_as(function) ]
```

### <a name="parameters"></a>Parameter

*function*<br/>
Die lokale Funktion, die aufgerufen werden soll, wenn eine Remote Funktion aufgerufen wird.

## <a name="remarks"></a>Hinweise

Das **Call_as** C++ -Attribut verfügt über die gleiche Funktionalität wie das [Call_as](/windows/win32/Midl/call-as) -Mittell-Attribut.

## <a name="example"></a>Beispiel

Der folgende Code zeigt, wie Sie **Call_as** verwenden können, um einer Remote fähigen Funktion (`f1``Remf1`) eine nicht Remote fähige Funktion () zuzuordnen:

```cpp
// cpp_attr_ref_call_as.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];
[dual, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMInterface {
   [local] HRESULT f1 ( int i );
   [call_as(f1)] HRESULT Remf1 ( int i );
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|None|
|**Ungültige Attribute**|None|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[local](local-cpp.md)