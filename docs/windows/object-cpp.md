---
title: Objekt (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.object
dev_langs:
- C++
helpviewer_keywords:
- object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e8d69ccb0b5a0c0f0dd13d377841732d9f663e91
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607584"
---
# <a name="object-c"></a>object (C++)

Gibt eine benutzerdefinierte Schnittstelle an.

## <a name="syntax"></a>Syntax

```cpp
[object]
```

## <a name="remarks"></a>Hinweise

Wenn eine Schnittstellendefinition, vor der **Objekt** C++-Attribut wird die Schnittstelle in der IDL-Datei als eine benutzerdefinierte Schnittstelle platziert werden.

Alle mit Objekt markierte Schnittstelle erben muss `IUnknown`. Diese Bedingung erfüllt wird, wenn einer der Basisschnittstellen erben `IUnknown`. Wenn keine Basisschnittstellen erben `IUnknown`, der Compiler führt dazu, dass die Schnittstelle, die mit markierten **Objekt** für die Ableitung `IUnknown`.

## <a name="example"></a>Beispiel

Finden Sie unter [Nonbrowsable](../windows/nonbrowsable.md) ein Beispiel zur Verwendung für **Objekt**.

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
[dual](../windows/dual.md)  
[dispinterface](../windows/dispinterface.md)  
[Benutzerdefinierte](../windows/custom-cpp.md)  
[__interface](../cpp/interface.md)  