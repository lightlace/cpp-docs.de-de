---
title: ReadOnly (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.readonly
helpviewer_keywords:
- readonly attribute
ms.assetid: 1246cadd-5304-43a9-beea-51153d12704d
ms.openlocfilehash: 7eea071b62130c65fbb46ebc8827fc2b428c4c0c
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59036907"
---
# <a name="readonly-c"></a>readonly (C++)

Verhindert die Zuweisung zu einem Datenelement

## <a name="syntax"></a>Syntax

```cpp
[readonly]
```

## <a name="remarks"></a>Hinweise

Das C++-Attribut **readonly** hat die gleiche Funktion wie das MIDL-Attribut [readonly](/windows/desktop/Midl/readonly) .

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
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Datenmemberattribute](data-member-attributes.md)