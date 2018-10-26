---
title: Objekt (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
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
ms.openlocfilehash: 8828ada429875245d583c30d65259300a01f6a5d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50067435"
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

Finden Sie unter [Nonbrowsable](nonbrowsable.md) ein Beispiel zur Verwendung für **Objekt**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**interface**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Schnittstellenattribut](interface-attributes.md)<br/>
[dual](dual.md)<br/>
[dispinterface](dispinterface.md)<br/>
[custom](custom-cpp.md)<br/>
[__interface](../../cpp/interface.md)