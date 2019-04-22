---
title: Pointer_default (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.pointer_default
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
ms.openlocfilehash: 37bd2b16fb7a7c1c186f59897898e08cc73fffae
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59022665"
---
# <a name="pointerdefault"></a>pointer_default

Gibt an, das Standardattribut für die Zeiger für alle Zeiger, mit Ausnahme der obersten Ebene Zeigern, die in der Parameterliste angezeigt werden.

## <a name="syntax"></a>Syntax

```cpp
[ pointer_default(value) ]
```

### <a name="parameters"></a>Parameter

*value*<br/>
Ein Wert, der der Zeigertyp beschreibt: **Ptr**, **Ref**, oder **eindeutige**.

## <a name="remarks"></a>Hinweise

Die **Pointer_default** C++ Attribut hat die gleiche Funktionalität wie die [Pointer_default](/windows/desktop/Midl/pointer-default) MIDL-Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [Defaultvalue](defaultvalue.md) für ein Beispiel für die Verwendung von **Pointer_default**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**interface**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Schnittstellenattribut](interface-attributes.md)