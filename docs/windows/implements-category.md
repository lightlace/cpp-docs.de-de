---
title: "implements_category"
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
  - "vc-attr.implements_category"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "implements_category attribute"
ms.assetid: fb162df3-1ebe-43dc-a084-668d7ef8c03f
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# implements_category
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt die Kategorien an, die von der Zielklasse implementiert werden.  
  
## Syntax  
  
```  
  
      [ implements_category(  
   implements_category="uuid"  
) ]  
```  
  
#### Parameter  
 **implements\_category**  
 Die ID der implementierten Kategorie.  
  
## Hinweise  
 Das Attribut **implements\_category** C\+\+ gibt die Kategorien an, die von der Zielklasse implementiert werden.  Dies geschieht, indem eine KATEGORIEN erstellt und die anderen Einträge zugeordnet, die durch das Hinzufügen **implements\_category**\-Attribut angegeben werden.  Weitere Informationen finden Sie unter [Was sind Teil von Kategorien und ihrer Funktionsweise?](http://msdn.microsoft.com/library/windows/desktop/ms694322).  
  
 Dieses Attribut erfordert, dass [Co\-Klasse](../windows/coclass.md), [ProgID](../windows/progid.md)oder [vi\_progid](../windows/vi-progid.md)\-Attribut \(oder ein anderes Attribut, das ein solcher Test vorhanden\), bedeutet auch auf das gleiche Element übernommen werden.  Wenn ein einzelnes Attribut wird, die anderen zwei automatisch angewendet werden.  Wenn z. B. **progid** angewendet wird, werden **vi\_progid** und **coclass** ebenfalls angewendet.  
  
## Beispiel  
 Der folgende Code gibt an, dass das nächste Objekt die Kategorie Steuerelements implementiert.  
  
```  
// cpp_attr_ref_implements_category.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="MyLib")];  
[ coclass, implements_category("CATID_Control"),  
  uuid("20a0d0cc-5172-40f5-99ae-5e032f3205ae")]  
class CMyClass {};  
```  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Ja|  
|**Erforderliche Attribute**|Eines der folgenden Schritte aus: **coclass**, **progid**oder **vi\_progid**|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [COM Attributes](../windows/com-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [IMPLEMENTED\_CATEGORY](../Topic/IMPLEMENTED_CATEGORY.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)