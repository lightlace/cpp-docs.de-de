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
ms.openlocfilehash: cd6b79d84e4737cdbeb670bdd31b8cacf35cf8f1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373386"
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

[IDL-Attribute](../windows/idl-attributes.md)<br/>
[Parameterattribute](../windows/parameter-attributes.md)<br/>
[Methodenattribut](../windows/method-attributes.md)<br/>
[defaultvalue](../windows/defaultvalue.md)<br/>
[ID](../windows/id.md)<br/>
[out](../windows/out-cpp.md)  