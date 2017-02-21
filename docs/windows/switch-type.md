---
title: "switch_type | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.switch_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "switch_type attribute"
ms.assetid: e24544dc-b3bc-48ae-b249-f967db49271e
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# switch_type
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt den Typ der Variablen, die als diskriminierende Union verwendet wird.  
  
## Syntax  
  
```  
  
[switch_type(  
type  
}]  
  
```  
  
#### Parameter  
 `type`  
 Der Schaltertyp, kann eine ganze Zahl, ein Zeichen ein boolescher Wert oder ein Enumerationstyp sein.  
  
## Hinweise  
 Das Attribut **switch\_type** C\+\+ verfügt über die gleichen Funktionen wie das [switch\_type](http://msdn.microsoft.com/library/windows/desktop/aa367276) MIDL\-Attribut.  
  
 C\+\+\-Attribute unterstützen keine [gekapselte Unions](http://msdn.microsoft.com/library/windows/desktop/aa366811).  [Nonencapsulated\-Unionen](http://msdn.microsoft.com/library/windows/desktop/aa367119) werden nur in der folgenden Form unterstützt:  
  
```  
// cpp_attr_ref_switch_type.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLibrary")];  
[ export ]  
struct SizedValue2 {  
   [switch_type("char"), switch_is(kind)] union {  
      [case(1), string]  
         wchar_t* wval;  
      [default, string]  
         char* val;  
   };  
   char kind;  
};  
```  
  
## Beispiel  
 Weitere Informationen finden Sie im [Fall](../windows/case-cpp.md) Beispiel für eine Beispiel verwenden aus **switch\_type**.  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|`typedef`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [export](../windows/export.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)