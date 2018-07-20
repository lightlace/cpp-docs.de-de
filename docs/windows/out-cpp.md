---
title: Out (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.out
dev_langs:
- C++
helpviewer_keywords:
- out attribute
ms.assetid: 5051b1bf-4949-4bf1-b82f-35e14f0f244b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b23ff91a67962ec36cf6a9c2f5ebbf8122ab73c1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876812"
---
# <a name="out-c"></a>out (C++)
Gibt die Zeigerparameter an, die von der aufgerufenen Prozedur an die aufrufende Prozedur zurückgegeben werden (vom Server an den Client).  
  
## <a name="syntax"></a>Syntax  
  
```  
  
[out]  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Das C++-Attribut **out** hat die gleiche Funktion wie das MIDL-Attribut [out](http://msdn.microsoft.com/library/windows/desktop/aa367136) .  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel für die Verwendung von [bindable](../windows/bindable.md) finden Sie im Beispiel für **out**.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Schnittstellenparameter|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Parameterattribute](../windows/parameter-attributes.md)   
 ["DefaultValue"](../windows/defaultvalue.md)   
 [ID](../windows/id.md)   
