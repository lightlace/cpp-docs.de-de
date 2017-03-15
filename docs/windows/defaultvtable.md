---
title: "defaultvtable | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.defaultvtable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "defaultvtable attribute"
ms.assetid: 5b3ed483-f69e-44dd-80fc-952028eb9d73
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# defaultvtable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert eine Schnittstelle als die standardmäßige vtable Schnittstelle für ein COM\-Objekt.  
  
## Syntax  
  
```  
  
      [ defaultvtable(  
   interface  
) ]  
```  
  
#### Parameter  
 `interface`  
 Die festgelegte Schnittstelle, dass Sie die Standardeinstellung verfügen möchten, der für das COM\-Objekt vtable ist.  
  
## Hinweise  
 Das Attribut **defaultvtable** C\+\+ verfügt über die gleichen Funktionen wie das [defaultvtable](http://msdn.microsoft.com/library/windows/desktop/aa366795) MIDL\-Attribut.  
  
## Beispiel  
 Im folgenden Code werden Attribute auf eine Klasse an, die **defaultvtable** verwenden, um eine Standardschnittstelle angegeben werden:  
  
```  
// cpp_attr_ref_defaultvtable.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI1 {  
   HRESULT x();  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000002")]  
__interface IMyI2 {  
   HRESULT x();  
};  
  
[object, uuid("00000000-0000-0000-0000-000000000003")]  
__interface IMyI3 {  
   HRESULT x();  
};  
  
[coclass, source(IMyI3, IMyI1), default(IMyI3, IMyI2), defaultvtable(IMyI1),  
uuid("00000000-0000-0000-0000-000000000004")]  
class CMyC3 : public IMyI3 {};  
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