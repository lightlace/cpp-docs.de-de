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
ms.openlocfilehash: 6e8ddf566082bfded1f20a2bfe04e7cef0b5dc14
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48790586"
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

Weitere Informationen zu den attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Schnittstellenattribut](interface-attributes.md)  