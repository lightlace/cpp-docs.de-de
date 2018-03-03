---
title: Retval | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.retval
dev_langs:
- C++
helpviewer_keywords:
- retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cf7aa0cf8dd9767f603807ee18e23fe02d3446c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="retval"></a>retval
Kennzeichnet den Parameter, der den Rückgabewert des Members empfängt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
[retval]  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **Retval** C++-Attribut hat die gleiche Funktionalität wie die [Retval](http://msdn.microsoft.com/library/windows/desktop/aa367158) MIDL-Attribut.  
  
 **Retval** muss für das letzte Argument in der Deklaration einer Funktion angezeigt werden.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [bindbare](../windows/bindable.md) für ein Beispiel für die Verwendung von **Retval**.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Parameter, für die Schnittstellen-Methode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**out**|  
|**Ungültige Attribute**|**in**|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Parameterattribute](../windows/parameter-attributes.md)   
 [Methodenattribut](../windows/method-attributes.md)   
