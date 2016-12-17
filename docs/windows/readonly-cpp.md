---
title: "readonly (C++)"
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
  - "vc-attr.readonly"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "readonly-Attribut"
ms.assetid: 1246cadd-5304-43a9-beea-51153d12704d
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# readonly (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verhindert die Zuweisung zu einem Datenelement  
  
## Syntax  
  
```  
  
[readonly]  
  
```  
  
## Hinweise  
 Das C\+\+\-Attribut **readonly** hat die gleiche Funktion wie das MIDL\-Attribut [readonly](http://msdn.microsoft.com/library/windows/desktop/aa367152).  
  
 Wenn Sie die Änderung eines Methodenparameters verhindern möchten, verwenden Sie das [in](../windows/in-cpp.md)\-Attribut.  
  
## Beispiel  
 Der folgende Code zeigt die Verwendung des **readonly**\-Attributs:  
  
```  
// cpp_attr_ref_readonly.cpp  
// compile with: /LD  
[idl_quote("midl_pragma warning(disable:2461)")];  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
  
[dispinterface, uuid(11111111-1111-1111-1111-111111111111)]  
__interface IFireTabCtrl  
{  
   [readonly, id(1)] int i();  
};  
```  
  
## Anforderungen  
  
### Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Schnittstellenmethode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keine|  
|**Ungültige Attribute**|Keine|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Data Member Attributes](../windows/data-member-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)