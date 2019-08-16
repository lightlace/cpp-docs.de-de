---
title: Quelle (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.source
helpviewer_keywords:
- source attribute
ms.assetid: 1878d05d-7709-4e97-b114-c62f38f5140e
ms.openlocfilehash: 79614a345e6c07b03df351da93a847fe12e4b110
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514021"
---
# <a name="source-c"></a>source (C++)

Gibt für eine Klasse die Quell Schnittstellen der COM-Objekte für Verbindungspunkte an. Gibt für eine Eigenschaft oder Methode an, dass der Member ein Objekt oder eine Variante zurückgibt, das eine Quelle von Ereignissen ist.

## <a name="syntax"></a>Syntax

```cpp
[ source(interfaces) ]
```

### <a name="parameters"></a>Parameter

*interfaces*<br/>
Eine oder mehrere Schnittstellen, die Sie angeben, wenn Sie das Quell Attribut auf eine Klasse anwenden. Dieser Parameter wird nicht verwendet, wenn die Quelle auf eine Eigenschaft oder Methode angewendet wird.

## <a name="remarks"></a>Hinweise

Das **Quell** C++ Attribut verfügt über die gleiche Funktionalität wie das Mittel l- [Quell](/windows/win32/Midl/source) Attribut.

Sie können das [default](default-cpp.md) -Attribut verwenden, um die standardmäßige Quell Schnittstelle für ein Objekt anzugeben.

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
|**Erforderliche Attribute**|`coclass`(bei Anwendung auf Klasse oder Struktur)|
|**Ungültige Attribute**|None|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[coclass](coclass.md)