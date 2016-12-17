---
title: "importlib"
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
  - "vc-attr.importlib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "importlib attribute"
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# importlib
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt Typen, die bereits in einer anderen Typbibliothek kompiliert wurden, der erstellten Typbibliothek zur Verfügung.  
  
## Syntax  
  
```  
  
        [ importlib(  
   "tlb_file"  
) ];  
```  
  
#### Parameter  
 *tlb\_file*  
 Der Name einer TLB\-Datei in Anführungszeichen, die in die Typbibliothek des aktuellen Projekts importiert werden soll.  
  
## Hinweise  
 Das C\+\+\-Attribut **importlib** bewirkt, dass eine `importlib`\-Anweisung in den Bibliotheksblock der generierten IDL\-Datei eingefügt wird.  Das C\+\+\-Attribut **importlib** hat die gleiche Funktion wie das MIDL\-Attribut [importlib](http://msdn.microsoft.com/library/windows/desktop/aa367050).  
  
## Beispiel  
 Der folgende Code zeigt ein Beispiel für die Verwendung von **importlib**:  
  
```  
// cpp_attr_ref_importlib.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[importlib("importlib.tlb")];  
```  
  
## Anforderungen  
  
### Attributkontext  
  
|||  
|-|-|  
|**Betrifft**|Überall|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|Keine|  
|**Ungültige Attribute**|Keine|  
  
 Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [import](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [include](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)