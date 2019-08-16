---
title: nicht browsetierbarC++ (com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.nonbrowsable
helpviewer_keywords:
- nonbrowsable attribute
ms.assetid: e71a98e7-4b65-454a-9829-342b9f2a84be
ms.openlocfilehash: 8b1849aa75e61ea5e369a277cab0b1327f48a28a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514386"
---
# <a name="nonbrowsable"></a>nonbrowsable

Gibt an, dass ein Schnittstellenmember nicht in einem Eigenschaften Browser angezeigt werden soll.

## <a name="syntax"></a>Syntax

```cpp
[nonbrowsable]
```

## <a name="remarks"></a>Hinweise

Das **nicht** C++ browsefähige Attribut verfügt über die gleiche Funktionalität wie das [nicht](/windows/win32/Midl/nonbrowsable) browsefähige Mittel l-Attribut.

## <a name="example"></a>Beispiel

```cpp
// cpp_attr_ref_nonbrowsable.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[object, helpstring("help string"), helpstringcontext(1),
uuid="11111111-1111-1111-1111-111111111111"]
__interface IMyI
{
   [nonbrowsable] HRESULT xx();
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
[Methodenattribut](method-attributes.md)