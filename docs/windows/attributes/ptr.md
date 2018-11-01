---
title: PTR (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.ptr
helpviewer_keywords:
- ptr attribute
ms.assetid: 95eaea57-a5be-45f6-a612-ba2c9bc4645a
ms.openlocfilehash: 7ed08403f32e5e4609266975c5c479a7b758fe89
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506209"
---
# <a name="ptr"></a>ptr

Kennzeichnet einen Zeiger als vollständige Zeiger.

## <a name="syntax"></a>Syntax

```cpp
[ptr]
```

## <a name="remarks"></a>Hinweise

Die **Ptr** C++-Attribut hat die gleiche Funktionalität wie die [Ptr](/windows/desktop/Midl/ptr) MIDL-Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [Defaultvalue](defaultvalue.md) für ein Beispiel für die Verwendung von **Ptr**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Schnittstellenparameter, Schnittstellenmethode **Typedef**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Schnittstellenattribut](interface-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)