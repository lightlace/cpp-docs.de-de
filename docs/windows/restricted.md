---
title: "restricted | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.restricted"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "restricted attribute"
ms.assetid: 504a96be-b904-4269-8be1-920feba201b4
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# restricted
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass ein Member eines Moduls, Schnittstellen\- oder Dispatchschnittstelle nicht willkürlich aufgerufen werden kann.  
  
## Syntax  
  
```  
  
      [ restricted(  
   interfaces  
) ]  
```  
  
#### Parameter  
 `interfaces`  
 Eine oder mehrere Schnittstellen, die möglicherweise nicht willkürlich für ein COM\-Objekt aufgerufen werden.  Dieser Parameter ist nur gültig, wenn er auf eine Klasse angewendet wird.  
  
## Hinweise  
 Das Attribut **restricted** C\+\+ verfügt über die gleichen Funktionen wie das [Einschränkung](http://msdn.microsoft.com/library/windows/desktop/aa367157) MIDL\-Attribut.  
  
## Beispiel  
 Im folgenden Code wird gezeigt, wie das **restricted**\-Attribut verwendet:  
  
```  
// cpp_attr_ref_restricted.cpp  
// compile with: /LD  
#include "windows.h"  
#include "unknwn.h"  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface a  
{  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000002")]  
__interface b  
{  
};  
  
[coclass, restricted(a,b), uuid("00000000-0000-0000-0000-000000000003")]  
class c : public a, public b  
{  
};  
```  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|Schnittstellenmethode, `struct`, **Klasse**, `interface`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**coclass** \(wenn Sie **Klasse** oder `struct`angewendet werden\)|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)