---
title: Ausgeblendete | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.hidden
dev_langs:
- C++
helpviewer_keywords:
- hidden attribute
ms.assetid: 199c96dd-fc07-46c7-af93-92020aebebe7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c038eb4869cb3191dd26b5c4ea8e1c6cc182e366
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="hidden"></a>hidden
Gibt an, dass das Element vorhanden ist, aber nicht in einem Browser benutzerorientierte angezeigt werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
[hidden]  
  
```  
  
## <a name="remarks"></a>Hinweise  
 Die **ausgeblendete** C++-Attribut hat die gleiche Funktionalität wie die [ausgeblendete](http://msdn.microsoft.com/library/windows/desktop/aa366861) MIDL-Attribut.  
  
## <a name="example"></a>Beispiel  
 Siehe das Beispiel für [bindbare](../windows/bindable.md) ein Beispiel zur Verwendung **ausgeblendete**.  
  
## <a name="requirements"></a>Anforderungen  
  
### <a name="attribute-context"></a>Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|`interface`, **Klasse**, `struct`, Methode, Eigenschaft|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**coclass** (bei Anwendung auf **class** oder `struct`)|  
|**Ungültige Attribute**|Keiner|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Siehe auch  
 [IDL-Attribute](../windows/idl-attributes.md)   
 [Schnittstellenattribut](../windows/interface-attributes.md)   
 [Klassenattribute](../windows/class-attributes.md)   
 [Methodenattribut](../windows/method-attributes.md)   
