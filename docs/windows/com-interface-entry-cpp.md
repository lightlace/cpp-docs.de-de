---
title: "com_interface_entry (C++)"
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
  - "vc-attr.com_interface_entry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "com_interface_entry attribute"
ms.assetid: 10368f81-b99b-4a0f-ba4f-a142e6911a5c
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# com_interface_entry (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fügt einen Eintrag Schnittstellen in die COM\-Zuordnung der Zielklasse hinzu.  
  
## Syntax  
  
```  
  
     [ com_interface_entry(   
  com_interface_entry  
) ]  
```  
  
#### Parameter  
 *com\_interface\_entry*  
 Eine Zeichenfolge, die den tatsächlichen Text des Eintrags enthält.  Eine Liste der möglichen Werte finden Sie unter [COM\_INTERFACE\_ENTRY\-Makros](../Topic/COM_INTERFACE_ENTRY%20Macros.md).  
  
## Hinweise  
 Das Attribut `com_interface_entry` C\+\+ fügt die ungekürzten Inhalt einer Zeichenfolge in die COM\-Schnittstellenzuordnung des Zielobjekts.  Wenn das Attribut auf das Zielobjekt einmal angewendet wurde, wird der Eintrag in den Beginn der vorhandenen Schnittstellen eingefügt zugeordnet.  Wenn das Attribut wiederholt auf dasselbe Zielobjekt angewendet wird, werden die Einträge am Anfang der Schnittstellen in der Reihenfolge zugeordnet eingefügt, die sie empfangen werden.  
  
 Dieses Attribut erfordert, dass [Co\-Klasse](../windows/coclass.md), [ProgID](../windows/progid.md)oder [vi\_progid](../windows/vi-progid.md)\-Attribut \(oder ein anderes Attribut, das ein solcher Test vorhanden\), bedeutet auch auf das gleiche Element übernommen werden.  Wenn ein einzelnes Attribut wird, die anderen zwei automatisch angewendet werden.  Wenn z. B. **progid** angewendet wird, werden **vi\_progid** und **coclass** ebenfalls angewendet.  
  
 Da die erste Verwendung von `com_interface_entry` bewirkt, dass die neue Schnittstelle zugeordnet zu Beginn der Schnittstellen eingefügt werden soll, muss sie eine der folgenden COM\_INTERFACE\_ENTRY\-Typen sein:  
  
-   COM\_INTERFACE\_ENTRY  
  
-   COM\_INTERFACE\_ENTRY\_IID  
  
-   COM\_INTERFACE\_ENTRY2  
  
-   COM\_INTERFACE\_ENTRY2\_IID  
  
 Zusätzliche Verwendung des `com_interface_entry`\-Attributs kann alle unterstützten COM\_INTERFACE\_ENTRY\-Typen verwenden.  
  
 Diese Einschränkung ist erforderlich, da ATL den ersten Eintrag in der Schnittstellen als Identität zugeordnet **IUnknown**verwendet. Daher muss der Eintrag eine gültige Schnittstelle sein.  Beispielsweise ist das folgende Codebeispiel ungültig, da der erste Eintrag in der Schnittstellen keine wirkliche COM\-Schnittstelle zugeordnet.  
  
```  
[ coclass, com_interface_entry =  
    "COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"  
]  
   class CMyClass  
   {  
   };  
```  
  
## Beispiel  
 Der folgende Code fügt zwei Einträge in der vorhandenen COM\-Schnittstellenzuordnung von **CMyBaseClass**hinzu.  Das erste Element ist eine Standardschnittstelle und die zweite blendet die **IDebugTest**\-Schnittstelle aus.  
  
```  
// cpp_attr_ref_com_interface_entry.cpp  
// compile with: /LD  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
#include "atlcom.h"  
  
[module (name ="ldld")];  
  
[ object,  
  uuid("7dbebed3-d636-4917-af62-c767a720a5b9")]  
__interface IDebugTest{};  
  
[ object,  
  uuid("2875ceac-f94b-4087-8e13-d13dc167fcfc")]  
__interface IMyClass{};  
  
[ coclass,  
  com_interface_entry ("COM_INTERFACE_ENTRY (IMyClass)"),  
  com_interface_entry ("COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"),  
  uuid("b85f8626-e76e-4775-b6a0-4826a9e94af2")  
]  
  
class CMyClass: public IMyClass, public IDebugTest  
{  
};  
```  
  
 Die resultierende COM\-Objekt\-Karte für **CMyBaseClass** lautet wie folgt:  
  
```  
BEGIN_COM_MAP(CMyClass)  
    COM_INTERFACE_ENTRY (IMyClass)  
    COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)  
    COM_INTERFACE_ENTRY(IMyClass)  
    COM_INTERFACE_ENTRY2(IDispatch, IMyClass)  
    COM_INTERFACE_ENTRY(IDebugTest)  
    COM_INTERFACE_ENTRY(IProvideClassInfo)  
END_COM_MAP()  
```  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Ja|  
|**Erforderliche Attribute**|Ein oder mehrere der folgenden Schritte aus: **coclass**, **progid**oder **vi\_progid**.|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [COM Attributes](../windows/com-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)