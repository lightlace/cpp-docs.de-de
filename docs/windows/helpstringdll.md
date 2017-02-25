---
title: "helpstringdll | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.helpstringdll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "helpstringdll attribute [C++]"
ms.assetid: 121271fa-f061-492b-b87f-bbfcf4b02e7b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# helpstringdll
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt den Namen der DLL an, der verwendet wird, um Zeichenfolgen Dokumente Lokalisierung \(Discovery\) auszuführen.  
  
## Syntax  
  
```  
  
      [ helpstringdll(  
   "string"  
) ]  
```  
  
#### Parameter  
 `string`  
 Das Ausführen von Dokumenten verwendete Formatzeichenfolgen Suche zu verwendende DLL.  
  
## Hinweise  
 Das Attribut **helpstringdll** C\+\+ verfügt über die gleichen Funktionen wie das [helpstringdll](http://msdn.microsoft.com/library/windows/desktop/aa366860) MIDL\-Attribut.  
  
## Beispiel  
  
```  
// cpp_attr_ref_helpstringdll.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib", helpstringdll="xx.dll")];  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI   
{  
   HRESULT xxx();  
};  
```  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `interface`, Schnittstellenmethode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)