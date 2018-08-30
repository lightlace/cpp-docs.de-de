---
title: in (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.in
dev_langs:
- C++
helpviewer_keywords:
- in attribute
ms.assetid: 7b450cc4-4d2e-4910-a195-7487c6b7c373
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6c447147802d91df0f280a82c61d919ee673970a
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222989"
---
# <a name="in-c"></a>in (C++)

Gibt an, dass ein Parameter, die von der aufrufenden Prozedur an die aufgerufene Prozedur übergeben werden.

## <a name="syntax"></a>Syntax

```cpp
[in]
```

## <a name="remarks"></a>Hinweise

Die **in** C++-Attribut hat die gleiche Funktionalität wie die [in](/windows/desktop/Midl/in) MIDL-Attribut.

## <a name="example"></a>Beispiel

Finden Sie unter [bindbare](../windows/bindable.md) ein Beispiel zur Verwendung für **in**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Parameter, für die Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|**retval**|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[Parameterattribute](../windows/parameter-attributes.md)  
[Methodenattribut](../windows/method-attributes.md)  
[defaultvalue](../windows/defaultvalue.md)  
[ID](../windows/id.md)  
[out](../windows/out-cpp.md)  