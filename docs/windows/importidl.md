---
title: "importidl"
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
  - "vc-attr.importidl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "importidl attribute"
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# importidl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fügt die angegebene IDL\-Datei in der generierten IDL\-Datei ein.  
  
## Syntax  
  
```  
  
      [ importidl(  
   idl_file  
) ];  
```  
  
#### Parameter  
 `idl_file`  
 Identifiziert den Namen der IDL\-Datei, die Sie der IDL\-Datei zusammenführen möchten, die für die Anwendung generiert wird.  
  
## Hinweise  
 Das Attribut **importidl** C\+\+ legt den Abschnitt außerhalb des Library\-Blocks \(in `idl_file`\) in der generierten IDL\-Datei des Programms und den Abschnitt Bibliothek \(in `idl_file`\) in der Bibliothek generierten IDL\-Datei des Programms.  
  
 Sie sollten **importidl**verwenden, z. B. wenn Sie eine hand\-codierte IDL\-Datei mit der generierten IDL\-Datei verwenden möchten.  
  
## Beispiel  
  
```  
// cpp_attr_ref_importidl.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[importidl("import.idl")];  
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
 [import](../windows/import.md)   
 [importlib](../windows/importlib.md)   
 [include](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)