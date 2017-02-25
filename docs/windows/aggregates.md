---
title: "Aggregate | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.aggregates"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregates-Attribut"
  - "Aggregation [C++]"
  - "Aggregieren von Objekten [C++], aggregates-Attribut"
  - "Aggregate [C++]"
ms.assetid: 67a084c9-941f-474b-a029-9c93b38ebe9a
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Aggregate
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass das Objekt das von der CLSID angegebene Objekt aggregiert.  
  
## Syntax  
  
```  
  
[ aggregates(  
clsid,  
variable_name  
) ]  
  
```  
  
#### Parameter  
 `clsid`  
 Gibt die CLSID des aggregierbaren Objekts an.  
  
 `variable_name`  
 Der Name der Variable, die eingefügt werden soll. Diese Variable enthält die **IUnknown**\-Schnittstelle des Objekts, die aggregiert wird.  
  
## Hinweise  
 Das C\+\+\-Attribut **aggregates** implementiert einen äußeren Wrapper für die Objekte, die aggregiert werden \(angegeben von `clsid`\), wenn es auf ein Objekt angewendet wird.  
  
 Dieses Attribut erfordert, dass die Attribute [coclass](../windows/coclass.md), [progid](../windows/progid.md), oder [vi\_progid](../windows/vi-progid.md) \(oder ein anderes Attribut, das eines der genannten impliziert\) auch auf demselben Element angewendet werden. Wenn ein einzelnes Attribut verwendet wird, werden die anderen beiden automatisch angewendet. Wenn z.B. **progid** angewendet wird, werden **vi\_progid** und **coclass** ebenso angewendet.  
  
 **ATL\-Projekte**  
  
 Wenn dieses Attribut in einem Projekt verwendet wird, das ATL verwendet, ändert sich das Verhalten des Attributs. Erstens wird der folgende Eintrag der COM\-Zuordnung des Zielobjekts hinzugefügt:  
  
```  
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(_m_spAttrXXX, clsid)  
```  
  
 Zweitens wird das Makro [DECLARE\_GET\_CONTROLLING\_UNKNOWN](../Topic/DECLARE_GET_CONTROLLING_UNKNOWN.md) ebenfalls hinzugefügt.  
  
## Beispiel  
  
```  
// cpp_attr_ref_aggregates.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
// requires 'aggregatable.dll'  
// see aggregatable attribute to create 'aggregatable.dll'  
class DECLSPEC_UUID("1a8369cc-1c91-42c4-befa-5a5d8c9d2529") CMyClass;  
  
[module (name="MYObject")];  
[object, uuid("ab006d85-e754-47c5-9ef4-2744ff32a20c")]  
__interface IObject  
{  
};  
  
[ coclass, aggregates(__uuidof(CMyClass)),   
  uuid("91cb2c06-8931-432a-baac-206e55c4edfb")]  
struct CObject : IObject  
{  
   int i;  
};  
```  
  
## Anforderungen  
  
### Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Ja|  
|**Erforderliche Attribute**|Ein Attribut oder mehrere Attribute der folgenden: **coclass**, **progid**, oder **vi\_progid**.|  
|**Ungültige Attribute**|Keine|  
  
 Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [COM Attributes](../windows/com-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Aggregation](http://msdn.microsoft.com/library/windows/desktop/ms686558)   
 [Aggregierbar](http://msdn.microsoft.com/library/windows/desktop/aa366721)   
 [COM\_INTERFACE\_ENTRY\_AUTOAGGREGATE\_BLIND](../Topic/COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)