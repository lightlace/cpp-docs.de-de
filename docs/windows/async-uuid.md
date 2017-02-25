---
title: "async_uuid | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.async_uuid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "async_uuid attribute"
ms.assetid: 235cb0d7-be58-4dd9-983c-e2a21bbc42c6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# async_uuid
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt das UUID an, das den MIDL\-Compiler, weist die synchronen und asynchronen Versionen einer COM\-Schnittstelle zu definieren.  
  
## Syntax  
  
```  
  
      [async_uuid (  
   uuid  
)]  
```  
  
#### Parameter  
 *uuid*  
 Ein UUID, das die Version der Schnittstelle identifiziert.  
  
## Hinweise  
 Das Attribut **async\_uuid** C\+\+ verfügt über die gleichen Funktionen wie das [async\_uuid](http://msdn.microsoft.com/library/windows/desktop/aa366735) MIDL\-Attribut.  
  
## Beispiel  
  
```  
// cpp_attr_ref_async_uuid.cpp  
// compile with: /LD  
#include <Windows.h>  
[module(name="Test")];  
[object, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb"),   
async_uuid("e8583106-38fd-487e-912e-4fc8645c677e")]  
__interface ICustom {  
   HRESULT Custom([in] long l, [out, retval] long *pLong);  
};  
```  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|`interface`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|**dual**, **dispinterface**|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)