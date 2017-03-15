---
title: "licensed | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.licensed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "licensed attribute"
ms.assetid: 09cf3b4a-d3f2-43e3-9180-d420333b23bf
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# licensed
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass das COM\-Objekt, auf das es angewendet wird, lizenziert ist, und muss mithilfe **IClassFactory2**instanziiert werden.  
  
## Syntax  
  
```  
  
[licensed]  
  
```  
  
## Hinweise  
 Das Attribut **licensed** C\+\+ verfügt über die gleichen Funktionen wie das [lizenziert](http://msdn.microsoft.com/library/windows/desktop/aa367070) MIDL\-Attribut.  
  
## Beispiel  
  
```  
// cpp_attr_ref_licensed.cpp  
// compile with: /LD  
#include "unknwn.h"  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI : IUnknown {  
   HRESULT f();  
};  
  
[coclass, version("2.1"), uuid(12345678-1111-2222-3333-123456789012),   
licensed, threading(free), progid(some.name)]  
class CSample : public IMyI {  
public:  
   int nSize;  
};  
  
[module(name="MyLibrary", version="1.0", helpstring="My Library Block")];  
```  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**Co\-Klasse**|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)