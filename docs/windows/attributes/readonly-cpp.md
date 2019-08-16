---
title: schreibgeschützt (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.readonly
helpviewer_keywords:
- readonly attribute
ms.assetid: 1246cadd-5304-43a9-beea-51153d12704d
ms.openlocfilehash: 93f7393f76596766e841dfc25f6d12e20e3db618
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514136"
---
# <a name="readonly-c"></a>readonly (C++)

Verhindert die Zuweisung zu einem Datenelement

## <a name="syntax"></a>Syntax

```cpp
[readonly]
```

## <a name="remarks"></a>Hinweise

Das C++-Attribut **readonly** hat die gleiche Funktion wie das MIDL-Attribut [readonly](/windows/win32/Midl/readonly) .

Wenn Sie die Änderung eines Methodenparameters verhindern möchten, verwenden Sie das [in](in-cpp.md) -Attribut.

## <a name="example"></a>Beispiel

Der folgende Code zeigt die Verwendung des **readonly** -Attributs:

```cpp
// cpp_attr_ref_readonly.cpp
// compile with: /LD
[idl_quote("midl_pragma warning(disable:2461)")];
#include "unknwn.h"
[module(name="ATLFIRELib")];

[dispinterface, uuid(11111111-1111-1111-1111-111111111111)]
__interface IFireTabCtrl
{
   [readonly, id(1)] int i();
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
[Datenmemberattribute](data-member-attributes.md)