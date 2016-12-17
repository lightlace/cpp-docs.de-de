---
title: "requires_category"
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
  - "vc-attr.requires_category"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "requires_category attribute"
ms.assetid: a645fdc6-1ef5-414d-8c56-5fe2686d4687
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# requires_category
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt die Kategorien erforderlicher Teil der Zielklasse an.  
  
## Syntax  
  
```  
  
     [ requires_category(   
  requires_category  
) ]  
```  
  
#### Parameter  
 *requires\_category*  
 Die ID der erforderlichen Kategorie.  
  
## Hinweise  
 Das Attribut **requires\_category** C\+\+ gibt die Kategorien an, die von der Zielklasse erforderlich sind.  Weitere Informationen finden Sie unter [REQUIRED\_CATEGORY](../Topic/REQUIRED_CATEGORY.md).  
  
 Dieses Attribut erfordert, dass [Co\-Klasse](../windows/coclass.md), [ProgID](../windows/progid.md)oder [vi\_progid](../windows/vi-progid.md)\-Attribut \(oder ein anderes Attribut, das ein solcher Test vorhanden\), bedeutet auch auf das gleiche Element übernommen werden.  
  
## Beispiel  
 Der folgende Code erfordert, dass das Objekt implementieren die Kategorie Steuerelements.  
  
```  
// cpp_attr_ref_requires_category.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="MyLibrary")];  
  
[ coclass, requires_category("CATID_Control"),  
  uuid("1e1a2436-f3ea-4ff3-80bf-5409370e8144")]  
class CMyClass {};  
```  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Ein oder mehrere der folgenden Schritte aus: **coclass**, **progid**oder **vi\_progid**.|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [COM Attributes](../windows/com-attributes.md)   
 [implements\_category](../windows/implements-category.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)