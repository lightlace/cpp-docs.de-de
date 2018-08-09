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
ms.openlocfilehash: 8522b3af527267706a2e2697b88049a38b0f092f
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017190"
---
# <a name="in-c"></a>in (C++)
Gibt an, dass ein Parameter, die von der aufrufenden Prozedur an die aufgerufene Prozedur übergeben werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
[in]  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **in** C++-Attribut hat die gleiche Funktionalität wie die [in](http://msdn.microsoft.com/library/windows/desktop/aa367051) MIDL-Attribut.  
  
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
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Parameterattribute](../windows/parameter-attributes.md)   
 [Methodenattribute](../windows/method-attributes.md)   
 [DefaultValue](../windows/defaultvalue.md)   
 [ID](../windows/id.md)   
 [out](../windows/out-cpp.md)   