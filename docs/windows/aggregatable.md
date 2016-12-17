---
title: "aggregatable"
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
  - "vc-attr.aggregatable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregatable attribute"
ms.assetid: 9253a46a-cd76-41f2-b3b6-86f709bb069c
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# aggregatable
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass die Klasse Aggregation unterstützt.  
  
## Syntax  
  
```  
  
      [ aggregatable(   
   value  
) ]  
```  
  
#### Parameter  
 *Wert* \(optional\)  
 Ein Parameter, um anzugeben, wann das COM\-Objekt zusammengesetzt werden kann:  
  
-   **nie** das COM\-Objekt kann nicht aggregiert werden.  
  
-   **zulässigen** das COM\-Objekt kann direkt erstellt werden, oder er kann aggregiert werden.  Dies ist die Standardeinstellung.  
  
-   **stets** das COM\-Objekt kann nicht direkt erstellt werden und kann nur aggregiert werden.  Wenn Sie `CoCreateInstance` für dieses Objekt aufrufen, müssen Sie die aggregierenden **IUnknown**\-Schnittstelle des Objekts \(steuernde **IUnknown**\) angeben.  
  
## Hinweise  
 Das Attribut **aggregierbar** C\+\+ verfügt über die gleichen Funktionen wie das [aggregierbar](http://msdn.microsoft.com/library/windows/desktop/aa366721) MIDL\-Attribut.  Dies bedeutet, dass der Compiler das Attribut **aggregierbar** die generierten IDL\-Datei übergibt.  
  
 Dieses Attribut erfordert, dass [Co\-Klasse](../windows/coclass.md), [ProgID](../windows/progid.md)oder [vi\_progid](../windows/vi-progid.md)\-Attribut \(oder ein anderes Attribut, das ein solcher Test vorhanden\), bedeutet auch auf das gleiche Element übernommen werden.  Wenn ein einzelnes Attribut wird, die anderen zwei automatisch angewendet werden.  Wenn z. B. **progid** angewendet wird, werden **vi\_progid** und **coclass** ebenfalls angewendet.  
  
 **ATL\-Projekte**  
  
 Wenn dieses Attribut innerhalb eines Projekts verwendet wird, das ATL verwendet, ändert sich das Verhalten des Attributs.  Zusätzlich zu den zuvor beschriebenen Verhalten fügt das Attribut auch eines der folgenden Makros der Zielklasse hinzu:  
  
|Parameterwert|Eingefügtes Makro|  
|-------------------|-----------------------|  
|**Nie**|[DECLARE\_NOT\_AGGREGATABLE](../Topic/DECLARE_NOT_AGGREGATABLE.md)|  
|**Zulässig**|[DECLARE\_POLY\_AGGREGATABLE](../Topic/DECLARE_POLY_AGGREGATABLE.md)|  
|**Immer**|[DECLARE\_ONLY\_AGGREGATABLE](../Topic/DECLARE_ONLY_AGGREGATABLE.md)|  
  
## Beispiel  
  
```  
// cpp_attr_ref_aggregatable.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module(name="MyModule")];  
  
[ coclass, aggregatable(allowed),  
  uuid("1a8369cc-1c91-42c4-befa-5a5d8c9d2529")]  
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
 [IDL Attributes](../windows/idl-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Aggregation](http://msdn.microsoft.com/library/windows/desktop/ms686558)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)