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
ms.openlocfilehash: aac6e0456bf8a63712c498114d403c05af5ccddb
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212207"
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

Die **Pointer_default** C++-Attribut hat die gleiche Funktionalität wie die [Pointer_default](/windows/desktop/Midl/pointer-default) MIDL-Attribut.

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