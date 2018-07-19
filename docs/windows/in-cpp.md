---
title: in (C++) | Microsoft Docs
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
ms.openlocfilehash: 0cb730163b9048005d3af64bb42ae9113681d52b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874017"
---
# <a name="in-c"></a>in (C++)
Gibt an, dass ein Parameter von der aufrufenden Prozedur an die aufgerufene Prozedur übergeben werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
[in]  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **in** C++-Attribut hat die gleiche Funktionalität wie die [in](http://msdn.microsoft.com/library/windows/desktop/aa367051) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [bindbare](../windows/bindable.md) ein Beispiel zum Verwenden von **in**.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Parameter, für die Schnittstellen-Methode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keiner|  
|**Ungültige Attribute**|**retval**|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Parameterattribute](../windows/parameter-attributes.md)   
 [Methodenattribut](../windows/method-attributes.md)   
 ["DefaultValue"](../windows/defaultvalue.md)   
 [ID](../windows/id.md)   
 [out](../windows/out-cpp.md)   
