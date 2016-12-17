---
title: "registration_script"
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
  - "vc-attr.registration_script"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "registration_script attribute"
ms.assetid: 786f8072-9187-4163-a979-7a604dd4c888
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# registration_script
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Führt die angegebene benutzerdefinierte Registrierung von Skripts aus.  
  
## Syntax  
  
```  
  
      [ registration_script(   
   script   
) ]  
```  
  
#### Parameter  
 *Skript*  
 Der vollständige Pfad einer benutzerdefinierten Datei des Registrierungsdaten skripts \(.rgs\).  Ein Wert aus **Nein**, wie `script = "none"`gibt an, dass die Registrierung keine Co\-Klasse Anforderungen verfügt.  
  
## Hinweise  
 Das Attribut **registration\_script** C\+\+ wird das benutzerdefinierte Registrierung von Skripts aus, das von **Skript**angegeben wird.  Wenn dieses Attribut nicht angegeben wird, wird eine Datei des Standards \(.rgs Informationen zum Registrieren einer Komponente enthalten\) verwendet.  Weitere Informationen zu .rgs\-Dateien finden Sie unter [Die Registrierungsstelle \(ATL\-Registrierungs\-Komponente\)](../atl/atl-registry-component-registrar.md).  
  
 Dieses Attribut erfordert, dass [Co\-Klasse](../windows/coclass.md), [ProgID](../windows/progid.md)oder [vi\_progid](../windows/vi-progid.md)\-Attribut \(oder ein anderes Attribut, das ein solcher Test vorhanden\), bedeutet auch auf das gleiche Element übernommen werden.  
  
## Beispiel  
 Der folgende Code gibt an, dass die Komponente ein Registrierung von Skripts, die cpp\_attr\_ref\_registration\_script.rgs aufgerufen wird.  
  
```  
// cpp_attr_ref_registration_script.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name="REG")];  
  
[object, uuid("d9cd196b-6836-470b-9b9b-5b04b828e5b0")]  
__interface IFace {};  
  
// requires "cpp_attr_ref_registration_script.rgs"  
// create sample .RGS file "cpp_attr_ref_registration_script.rgs" if it does not exist  
[ coclass, registration_script(script="cpp_attr_ref_registration_script.rgs"),  
  uuid("50d3ad42-3601-4f26-8cfe-0f1f26f98f67")]  
class CMyClass:public IFace {};  
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
 [Class Attributes](../windows/class-attributes.md)   
 [rdx](../windows/rdx.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)