---
title: in (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.in
dev_langs: C++
helpviewer_keywords: in attribute
ms.assetid: 7b450cc4-4d2e-4910-a195-7487c6b7c373
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ba7999f9834b0efc100fc66f19506a6f25843f9c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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
|**Erforderliche Attribute**|Keine|  
|**Ungültige Attribute**|**retval**|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Parameterattribute](../windows/parameter-attributes.md)   
 [Methodenattribut](../windows/method-attributes.md)   
 ["DefaultValue"](../windows/defaultvalue.md)   
 [ID](../windows/id.md)   
 [out](../windows/out-cpp.md)   
