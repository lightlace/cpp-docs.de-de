---
title: Propputref | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: c0903c4d6165ec511d35f7aac13deca06a704c31
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42571275"
---
# <a name="propputref"></a>propputref

Gibt eine eigenschaftseinstellungsfunktion an, die einen Verweis anstelle eines Werts verwendet.

## <a name="syntax"></a>Syntax

```cpp
[propputref]
```

## <a name="remarks"></a>Hinweise

Die **Propputref** C++-Attribut hat die gleiche Funktionalität wie die [Propputref](http://msdn.microsoft.com/library/windows/desktop/aa367147) MIDL-Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [bindbare](../windows/bindable.md) für ein Beispiel für die Verwendung von **Propputref**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Methode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|`propget`, `propput`|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[Methodenattribut](../windows/method-attributes.md)  
[propget](../windows/propget.md)  
[propput](../windows/propput.md)  