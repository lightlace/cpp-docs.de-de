---
title: Disp-Schnittstelle (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.dispinterface
dev_langs:
- C++
helpviewer_keywords:
- dispinterface attribute
ms.assetid: 61c5a4a1-ae92-47e9-8ee4-f847be90172b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3b02244e0576f99cc0a6940f2ee4a13511cfbe6f
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48790582"
---
# <a name="dispinterface"></a>dispinterface

Fügt eine Schnittstelle in die IDL-Datei als Verteilschnittstelle ein.

## <a name="syntax"></a>Syntax

```cpp
[dispinterface]
```

## <a name="remarks"></a>Hinweise

Wenn das C++-Attribut **dispinterface** einer Schnittstelle vorangeht, wird die Schnittstelle dadurch in den Bibliotheksblock in der generierten IDL-Datei eingefügt.

Solange Sie keine Basisklasse festlegen, wird eine Verteilschnittstelle von `IDispatch`abgeleitet. Sie müssen angeben, ein [Id](id.md) für die Member einer Verteilschnittstelle.

Das Beispiel für die Verwendung [Dispinterface](/windows/desktop/Midl/dispinterface) in der MIDL-Dokumentation:

```cpp
dispinterface helloPro
   { interface hello; };
```

ist nicht gültig für das Attribut **dispinterface** .

## <a name="example"></a>Beispiel

Siehe das Beispiel für [bindbare](bindable.md) ein Beispiel zur Verwendung für **Dispinterface**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**interface**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|`dual`, `object`, `oleautomation`, `local`, `ms_union`|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Attribute nach Verwendung](attributes-by-usage.md)<br/>
[uuid](uuid-cpp-attributes.md)<br/>
[dual](dual.md)<br/>
[Benutzerdefinierte](custom-cpp.md)<br/>
[object](object-cpp.md)<br/>
[__interface](../../cpp/interface.md)  