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
ms.openlocfilehash: a3a0ec5a39d6e99e5ceb6ec4ed089373e3057c1e
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791201"
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

Weitere Informationen zu den attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Schnittstellenattribut](interface-attributes.md)  