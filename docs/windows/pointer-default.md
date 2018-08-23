---
title: Pointer_default | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 391b30251235fdd15ec1e96304e956740cb58f1f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610147"
---
# <a name="pointerdefault"></a>pointer_default

Gibt an, das Standardattribut für die Zeiger für alle Zeiger, mit Ausnahme der obersten Ebene Zeigern, die in der Parameterliste angezeigt werden.

## <a name="syntax"></a>Syntax

```cpp
[ pointer_default(
   value
) ]
```

### <a name="parameters"></a>Parameter

*Wert*  
Ein Wert, der der Zeigertyp beschreibt: **Ptr**, **Ref**, oder **eindeutige**.

## <a name="remarks"></a>Hinweise

Die **Pointer_default** C++-Attribut hat die gleiche Funktionalität wie die [Pointer_default](http://msdn.microsoft.com/library/windows/desktop/aa367141) MIDL-Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [Defaultvalue](../windows/defaultvalue.md) für ein Beispiel für die Verwendung von **Pointer_default**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**interface**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[Schnittstellenattribut](../windows/interface-attributes.md)  