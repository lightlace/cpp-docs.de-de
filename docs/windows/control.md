---
title: "control | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.control"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Control attribute"
ms.assetid: 3d046bb2-4afe-4cb8-a762-233b296e1975
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# control
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass der benutzerdefinierte Typ ein Steuerelement befindet.  
  
## Syntax  
  
```  
  
[control]  
  
```  
  
## Hinweise  
 Das bedeutet, **Steuerelement**\-Attribut [Co\-Klasse](../windows/coclass.md)\-Attribut.  Das Attribut **Steuerelement** C\+\+ verfügt über die gleichen Funktionen wie das [Steuerelement](http://msdn.microsoft.com/library/windows/desktop/aa366764) MIDL\-Attribut.  
  
## Beispiel  
  
```  
// cpp_attr_ref_control.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="Test", control=true)];  
  
[object, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb")]  
__interface ICustom {  
   HRESULT Custom([in] long l, [out, retval] long *pLong);  
};  
  
[coclass, control, appobject, uuid("9e66a294-4365-11d2-a997-00c04fa37ddb")]  
class CTest : public ICustom {};  
```  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)