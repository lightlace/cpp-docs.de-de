---
title: Propputref (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.propputref
dev_langs:
- C++
helpviewer_keywords:
- propputref attribute
ms.assetid: 9b0aed74-fdc7-4e59-9117-949bea4f86dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 147b46a3081f842b247ac7a2227bd07bb75d8fe6
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48790625"
---
# <a name="propputref"></a>propputref

Gibt eine eigenschaftseinstellungsfunktion an, die einen Verweis anstelle eines Werts verwendet.

## <a name="syntax"></a>Syntax

```cpp
[propputref]
```

## <a name="remarks"></a>Hinweise

Die **Propputref** C++-Attribut hat die gleiche Funktionalität wie die [Propputref](/windows/desktop/Midl/propputref) MIDL-Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [bindbare](bindable.md) für ein Beispiel für die Verwendung von **Propputref**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Methode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|`propget`, `propput`|

Weitere Informationen zu den attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[propget](propget.md)<br/>
[propput](propput.md)  