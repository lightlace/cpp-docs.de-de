---
title: "call_as"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.call_as"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "call_as attribute"
ms.assetid: a09d7f1f-353b-4870-9b45-f0284161695d
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# call_as
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Aktiviert eine Funktion zu einer Remotewebsite [Lokal](../windows/local-cpp.md)\-Funktion zugeordnet werden, damit, wenn die remote Funktion aufgerufen wird, die lokale Funktion aufgerufen wird.  
  
## Syntax  
  
```  
  
      [ call_as(  
   function  
) ]  
```  
  
#### Parameter  
 *Funktion*  
 Die lokale Funktion, die aufgerufen werden soll, wenn eine remote Funktion aufgerufen wird.  
  
## Hinweise  
 Das Attribut **call\_as** C\+\+ verfügt über die gleichen Funktionen wie das [call\_as](http://msdn.microsoft.com/library/windows/desktop/aa366748) MIDL\-Attribut.  
  
## Beispiel  
 Der folgende Code zeigt, wie Sie verwenden können, um eine **call\_as** nicht remotefähig**f1**\(Funktion\) für eine Funktion \(remotefähigen**Remf1**\) zuzuordnen:  
  
```  
// cpp_attr_ref_call_as.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
[dual, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMInterface {  
   [local] HRESULT f1 ( int i );  
   [call_as(f1)] HRESULT Remf1 ( int i );   
};  
```  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|Schnittstellenmethode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [local](../windows/local-cpp.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)