---
title: Oleautomation (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.oleautomation
dev_langs:
- C++
helpviewer_keywords:
- oleautomation attribute
ms.assetid: c1086c91-260b-4dc3-b244-662852d09906
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ccc83dd6f51c3b7072b17d141f29e93c63688fa1
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059531"
---
# <a name="oleautomation"></a>oleautomation

Gibt an, dass eine Schnittstelle mit der Automatisierung kompatibel ist.

## <a name="syntax"></a>Syntax

```cpp
[oleautomation]
```

## <a name="remarks"></a>Hinweise

Die **Oleautomation** C++-Attribut hat die gleiche Funktionalität wie die [Oleautomation](/windows/desktop/Midl/oleautomation) MIDL-Attribut.

## <a name="example"></a>Beispiel

Finden Sie unter den Beispielen für [Defaultvalue](defaultvalue.md) und [nonextensible](nonextensible.md) für ein Beispiel für die Verwendung von **Oleautomation**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**interface**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|**dispinterface**|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Schnittstellenattribut](interface-attributes.md)