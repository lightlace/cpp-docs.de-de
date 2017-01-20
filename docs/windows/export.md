---
title: "export"
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
  - "vc-attr.export"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "export attribute"
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# export
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bewirkt, dass eine Datenstruktur, in die IDL\-Datei abgelegt werden.  
  
## Syntax  
  
```  
  
[export]  
  
```  
  
## Hinweise  
 Das Attribut **export** C\+\+ wird eine Datenstruktur, in die IDL\-Datei abgelegt und in der Typbibliothek verfügbar sein soll dann in einem BINARY\-kompatiblen Format, in dem sie zur Verwendung mit einer beliebigen Sprache bereitstellt.  
  
 Sie können das **export**\-Attribut nicht auf eine Klasse anwenden, selbst wenn die Klasse nur öffentliche Member aufweist \(das Äquivalent der `struct`\).  
  
 Wenn Sie unbenanntes `enum`s oder `struct`s exportieren, werden sie dem angegebenen Namen, die mit **\_\_unnamed***x*beginnen, wobei *x* eine laufende Nummer ist.  
  
 Die Typdefinitionen sind gültig sind für den Export, Basistypen, Strukturen, Unions, Enumerationen oder Typbezeichner.  Weitere Informationen finden Sie unter [Typedef](http://msdn.microsoft.com/library/windows/desktop/aa367287) .  
  
## Beispiel  
 Im folgenden Code wird gezeigt, wie das **export**\-Attribut verwendet:  
  
```  
// cpp_attr_ref_export.cpp  
// compile with: /LD  
[module(name="MyLibrary")];  
  
[export]  
struct MyStruct {  
   int i;  
};  
```  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|**Union**, `typedef`, `enum`, `struct`oder `interface`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)