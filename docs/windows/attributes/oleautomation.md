---
title: Oleautomation (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.oleautomation
helpviewer_keywords:
- oleautomation attribute
ms.assetid: c1086c91-260b-4dc3-b244-662852d09906
ms.openlocfilehash: 74701742de904b76e7b1152c8ddb3f2f5dd953c2
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59031711"
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