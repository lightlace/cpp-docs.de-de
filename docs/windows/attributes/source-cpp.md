---
title: Quelle (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.source
helpviewer_keywords:
- source attribute
ms.assetid: 1878d05d-7709-4e97-b114-c62f38f5140e
ms.openlocfilehash: 59ed66acbbd6ef876e6052767dc5a5243d4b8dd6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476526"
---
# <a name="source-c"></a>source (C++)

Gibt an für eine Klasse das COM-Objekt-Schnittstellen für Verbindungspunkte aus. Auf eine Eigenschaft oder Methode gibt Sie an, dass das Element zurückgibt, ein Objekt oder eine Variante, die eine Ereignisquelle ist.

## <a name="syntax"></a>Syntax

```cpp
[ source(interfaces) ]
```

### <a name="parameters"></a>Parameter

*interfaces*<br/>
Eine oder mehrere Schnittstellen, die Sie angeben, wenn Sie die Quelle anwenden Attribut auf eine Klasse. Dieser Parameter wird nicht verwendet werden, wenn Quelle auf eine Eigenschaft oder Methode angewendet wird.

## <a name="remarks"></a>Hinweise

Die **Quelle** C++-Attribut hat die gleiche Funktionalität wie die [Quelle](/windows/desktop/Midl/source) MIDL-Attribut.

Können Sie die [Standard](default-cpp.md) Attribut, um die Standard-Quellschnittstelle für ein Objekt anzugeben.

## <a name="example"></a>Beispiel

```cpp
// cpp_attr_ref_source.cpp
// compile with: /LD
#include "windows.h"
#include "unknwn.h"
[module(name="MyLib")];

[object, uuid(11111111-1111-1111-1111-111111111111)]
__interface b
{
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]
   HRESULT get_I([out, retval]long *i);
};

[object, uuid(11111111-1111-1111-1111-111111111131)]
__interface c
{
   [id(0), propget, bindable, displaybind, defaultbind, requestedit]
   HRESULT et_I([out, retval]long *i);
};

[coclass, default(c), uuid(11111111-1111-1111-1111-111111111132)]
class N : public b
{
};

[coclass, source(c), default(b, c), uuid(11111111-1111-1111-1111-111111111133)]
class NN : public b
{
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**, **Schnittstelle**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|`coclass` (wenn es sich um eine Klasse oder Struktur angewendet wird)|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[coclass](coclass.md)