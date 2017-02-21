---
title: "wire_marshal | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.wire_marshal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wire_marshal attribute"
ms.assetid: 244f9d72-776d-4ebd-b60a-cee600a126b5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# wire_marshal
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt einen Datentyp an, der für die Übertragung anstelle eines anwendungsspezifischen Datentyps verwendet wird.  
  
## Syntax  
  
```  
  
[wire_marshal]  
  
```  
  
## Hinweise  
 Das Attribut **wire\_marshal** C\+\+ verfügt über die gleichen Funktionen wie das [wire\_marshal](http://msdn.microsoft.com/library/windows/desktop/aa367309) MIDL\-Attribut.  
  
## Beispiel  
 Im folgenden Code wird die Verwendung von **wire\_marshal**an:  
  
```  
// cpp_attr_ref_wire_marshal.cpp  
// compile with: /LD  
#include "windows.h"  
[module(name="MyLibrary")];  
  
[export, public] typedef unsigned long _FOUR_BYTE_DATA;  
  
[export] typedef struct _TWO_X_TWO_BYTE_DATA {  
   unsigned short low;  
   unsigned short high;  
} TWO_X_TWO_BYTE_DATA ;  
  
[export, wire_marshal(TWO_X_TWO_BYTE_DATA)] typedef _FOUR_BYTE_DATA FOUR_BYTE_DATA;  
```  
  
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
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)