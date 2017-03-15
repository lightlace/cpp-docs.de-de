---
title: "include (C++)"
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
  - "vc-attr.include"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "include attribute"
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# include (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt eine oder mehrere in der generierten IDL\-Datei Headerdateien eingefügt werden soll.  
  
## Syntax  
  
```  
  
      [ include(  
   header_file  
) ];  
```  
  
#### Parameter  
 *header\_file*  
 Der Name einer Datei, die Sie enthaltenes in der generierten IDL\-Datei soll.  
  
## Hinweise  
 Das Attribut **include** C\+\+ wird eine `#include` unterhalb der Anweisung `import "docobj.idl"`\-Anweisung in der generierten IDL\-Datei abgelegt werden soll.  
  
 Das Attribut **include** C\+\+ verfügt über die gleichen Funktionen wie das [Einschließen](http://msdn.microsoft.com/library/windows/desktop/aa367052) MIDL\-Attribut.  
  
## Beispiel  
 Der folgende Code zeigt ein Beispiel dafür gezeigt, wie **include**verwendet.  In diesem Beispiel enthält die Datei nur eine include.h \#include Anweisung.  
  
```  
// cpp_attr_ref_include.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[include(cpp_attr_ref_include.h)];  
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
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [import](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [includelib](../windows/includelib-cpp.md)   
 [importlib](../windows/importlib.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)