---
title: Dispinterface | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.dispinterface
dev_langs:
- C++
helpviewer_keywords:
- dispinterface attribute
ms.assetid: 61c5a4a1-ae92-47e9-8ee4-f847be90172b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cf7fb54b4059bc56aea967f03b9e4c2874f84e82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="dispinterface"></a>dispinterface
Fügt eine Schnittstelle in die IDL-Datei als Verteilschnittstelle ein.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
[dispinterface]  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Wenn das C++-Attribut **dispinterface** einer Schnittstelle vorangeht, wird die Schnittstelle dadurch in den Bibliotheksblock in der generierten IDL-Datei eingefügt.  
  
 Solange Sie keine Basisklasse festlegen, wird eine Verteilschnittstelle von `IDispatch`abgeleitet. Sie müssen eine [ID](../windows/id.md) für die Member einer Verteilschnittstelle angeben.  
  
 Das Beispiel für die Verwendung von [dispinterface](http://msdn.microsoft.com/library/windows/desktop/aa366802) in der MIDL-Dokumentation:  
  
```  
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
|**Betrifft**|`interface`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|**dual**, **object**, **oleautomation**, `local`, **ms_union**|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Attribute nach Verwendung](../windows/attributes-by-usage.md)   
 [UUID](../windows/uuid-cpp-attributes.md)   
 [Duale](../windows/dual.md)   
 [benutzerdefinierte](../windows/custom-cpp.md)   
 [Objekt](../windows/object-cpp.md)   
 [__interface](../cpp/interface.md)   
