---
title: "pragma | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.pragma"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pragma attribute"
ms.assetid: 3f90d023-b8b5-4007-8311-008bb72cbea1
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# pragma
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt die angegebene Zeichenfolge in die generierten IDL\-Datei ohne die Verwendung von Anführungszeichen ab.  .  
  
## Syntax  
  
```  
  
      [ pragma(  
   pragma_statement  
) ];  
```  
  
#### Parameter  
 *pragma\_statement*  
 Das Pragma, die in der generierten IDL\-Datei aufgenommen werden sollen.  
  
## Hinweise  
 Das Attribut **Pragma** C\+\+ verfügt über die gleichen Funktionen wie das [Pragma](http://msdn.microsoft.com/library/windows/desktop/aa367143) MIDL\-Attribut.  
  
## Beispiel  
  
```  
// cpp_attr_ref_pragma.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyLib")];  
[pragma(pack(4))];  
  
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]  
__interface A  
{  
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);  
};  
```  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|Überall|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [pack](../preprocessor/pack.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)