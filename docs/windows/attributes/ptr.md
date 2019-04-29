---
title: PTR (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.ptr
helpviewer_keywords:
- ptr attribute
ms.assetid: 95eaea57-a5be-45f6-a612-ba2c9bc4645a
ms.openlocfilehash: 2c712a2d9c85e0fe8fd8c4dbad5c7f48812ab1a2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407392"
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