---
title: Dispinterface | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 6a98c9016281a67211a41d1c63fcb9886a0b3c35
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222509"
---
# <a name="dispinterface"></a>dispinterface

Fügt eine Schnittstelle in die IDL-Datei als Verteilschnittstelle ein.

## <a name="syntax"></a>Syntax

```cpp
[dispinterface]
```

## <a name="remarks"></a>Hinweise

Wenn das C++-Attribut **dispinterface** einer Schnittstelle vorangeht, wird die Schnittstelle dadurch in den Bibliotheksblock in der generierten IDL-Datei eingefügt.

Solange Sie keine Basisklasse festlegen, wird eine Verteilschnittstelle von `IDispatch`abgeleitet. Sie müssen eine [ID](../windows/id.md) für die Member einer Verteilschnittstelle angeben.

Das Beispiel für die Verwendung [Dispinterface](/windows/desktop/Midl/dispinterface) in der MIDL-Dokumentation:

```cpp
dispinterface helloPro
   { interface hello; };
```

ist nicht gültig für das Attribut **dispinterface** .

## <a name="example"></a>Beispiel

Sehen Sie sich das Beispiel für [bindable](../windows/bindable.md) für ein Beispiel für die Verwendung von **dispinterface**an.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**interface**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|`dual`, `object`, `oleautomation`, `local`, `ms_union`|

Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[Attribute nach Verwendung](../windows/attributes-by-usage.md)  
[uuid](../windows/uuid-cpp-attributes.md)  
[dual](../windows/dual.md)  
[Benutzerdefinierte](../windows/custom-cpp.md)  
[object](../windows/object-cpp.md)  
[__interface](../cpp/interface.md)  