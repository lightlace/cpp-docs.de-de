---
title: Pointer_default (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.pointer_default
dev_langs:
- C++
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 994a4a48c5199c3efb05a00331656b3b23a2a0c0
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50067041"
---
# <a name="pointerdefault"></a>pointer_default

Gibt an, das Standardattribut für die Zeiger für alle Zeiger, mit Ausnahme der obersten Ebene Zeigern, die in der Parameterliste angezeigt werden.

## <a name="syntax"></a>Syntax

```cpp
[ pointer_default(value) ]
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Wert, der der Zeigertyp beschreibt: **Ptr**, **Ref**, oder **eindeutige**.

## <a name="remarks"></a>Hinweise

Die **Pointer_default** C++-Attribut hat die gleiche Funktionalität wie die [Pointer_default](/windows/desktop/Midl/pointer-default) MIDL-Attribut.

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