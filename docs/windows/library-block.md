---
title: "library_block"
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
  - "vc-attr.library_block"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "library_block attribute"
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# library_block
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Platziert ein Konstrukt innerhalb des IDL\-Library\-Blocks.  
  
## Syntax  
  
```  
  
[library_block]  
  
```  
  
## Hinweise  
 Wenn Sie ein Konstrukt innerhalb des Library\-Blocks platzieren, stellen Sie sicher, dass er in der Typbibliothek übergeben wird, unabhängig davon, ob sie verwiesen wird.  Standardmäßig werden nur Konstrukte, die von [Co\-Klasse](../windows/coclass.md), [Dispatchschnittstelle](../windows/dispinterface.md)und [idl\_module](../windows/idl-module.md)\-Attribute geändert werden, Library\-Block platziert.  
  
## Beispiel  
 Im folgenden Code wird eine benutzerdefinierte Oberfläche innerhalb des Library\-Blocks platziert.  
  
```  
// cpp_attr_ref_library_block.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib")];  
[object, library_block, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface IMyInterface {  
   HRESULT f1();  
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
  
 Weitere Informationen finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)