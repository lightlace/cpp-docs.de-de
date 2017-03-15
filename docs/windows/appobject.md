---
title: "appobject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.appobject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "appobject attribute"
ms.assetid: 8ce30b73-e945-403e-a755-6bc78078a695
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# appobject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Identifiziert die Co\-Klasse als Anwendungsobjekt, das einer vollständigen EXE\-Anwendung zugeordnet ist, und gibt an, dass Features und Eigenschaften der Co\-Klasse in diesem [Typbibliothek](../mfc/automation-clients-using-type-libraries.md)global verfügbar sind.  
  
## Syntax  
  
```  
  
[appobject]  
  
```  
  
## Hinweise  
 Das Attribut **appobject** C\+\+ verfügt über die gleichen Funktionen wie das [appobject](http://msdn.microsoft.com/library/windows/desktop/aa366726) MIDL\-Attribut.  
  
## Beispiel  
 Der folgende Code zeigt eine einfache Klassendefinition an, die von einem Attributblock vorausgeht, der **appobject**enthält:  
  
```  
// cpp_attr_ref_appobject.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib", uuid="f1ce17f0-a5df-4d26-95f6-0a122197ac5b")];  
  
[object, uuid="905de6db-7a12-45ab-9f8b-b39f5112f010"]  
__interface ICustom {};  
  
[coclass, appobject,uuid="00395340-745f-4b69-bd58-e2921452b9fc"]  
class A : public ICustom {  
   int i;  
};  
```  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**Co\-Klasse**|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)