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
ms.openlocfilehash: 18308cc66e2a01aa5e0396f098096ee9d49416bf
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644329"
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
  
 Das Beispiel für die Verwendung von [dispinterface](http://msdn.microsoft.com/library/windows/desktop/aa366802) in der MIDL-Dokumentation:  
  
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
 [UUID](../windows/uuid-cpp-attributes.md)   
 [Dual](../windows/dual.md)   
 [Benutzerdefinierte](../windows/custom-cpp.md)   
 [Objekt](../windows/object-cpp.md)   
 [__interface](../cpp/interface.md)   