---
title: "vararg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.vararg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "vararg attribute"
ms.assetid: 20fc3244-18e9-411c-990e-d5b4fa29a570
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# vararg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass die Funktion eine variable Anzahl von Argumenten annimmt.  
  
## Syntax  
  
```  
  
[vararg]  
  
```  
  
## Hinweise  
 Das Attribut **vararg** C\+\+ verfügt über die gleichen Funktionen wie das [vararg](http://msdn.microsoft.com/library/windows/desktop/aa367304) MIDL\-Attribut.  
  
## Beispiel  
 Im folgenden Code wird die Verwendung von **vararg**an:  
  
```  
// cpp_attr_ref_vararg.cpp  
// compile with: /LD  
#include "unknwn.h"  
#include "oaidl.h"  
[module(name="MyLibrary")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface X : public IUnknown   
{  
   [vararg] HRESULT Button([in, satype(VARIANT)]SAFEARRAY *psa);  
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
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)