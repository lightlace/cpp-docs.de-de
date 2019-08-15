---
title: Pointer_default (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.pointer_default
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
ms.openlocfilehash: c70c372e5f1c3a9c2f620a1fa3505fb9d0436e79
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514257"
---
# <a name="pointer_default"></a>pointer_default

Gibt das Standard Zeiger Attribut für alle Zeiger an, ausgenommen Zeiger der obersten Ebene, die in Parameterlisten angezeigt werden.

## <a name="syntax"></a>Syntax

```cpp
[ pointer_default(value) ]
```

### <a name="parameters"></a>Parameter

*value*<br/>
Ein Wert, der den Zeigertyp beschreibt: " **ptr**", " **ref**" oder " **Unique**".

## <a name="remarks"></a>Hinweise

Das **Pointer_default** C++ -Attribut verfügt über die gleiche Funktionalität wie das [Pointer_default](/windows/win32/Midl/pointer-default) -Mittell-Attribut.

## <a name="example"></a>Beispiel

Im Beispiel für [DefaultValue](defaultvalue.md) finden Sie eine Beispiel Verwendung von **Pointer_default**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**interface**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|None|
|**Ungültige Attribute**|None|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Schnittstellenattribut](interface-attributes.md)