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
ms.openlocfilehash: 2c0705c5d841b63cd3f537ab39dbbe9122fea869
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607909"
---
# <a name="object-c"></a>object (C++)
Gibt eine benutzerdefinierte Schnittstelle an.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
 [Dual](../windows/dual.md)   
 [Disp-Schnittstelle](../windows/dispinterface.md)   
 [Benutzerdefinierte](../windows/custom-cpp.md)   
 [__interface](../cpp/interface.md)   