---
title: "case (C++)"
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
  - "vc-attr.case"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "case attribute"
ms.assetid: 6fb883c3-0526-4932-a901-b4564dcaeb7d
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# case (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wird mit dem [switch\_type](../windows/switch-type.md)\-Attribut in **Union**.  
  
## Syntax  
  
```  
  
      [ case(  
   value  
) ]  
```  
  
#### Parameter  
 *Wert*  
 Ein möglicher Eingabewert, für den Sie die Verarbeitung bereitstellen möchten.  Der Typ der **Wert** kann einer der folgenden Typen sein:  
  
-   `int`  
  
-   `char`  
  
-   **boolean**  
  
-   `enum`  
  
 oder ein Bezeichner eines solchen Typs.  
  
## Hinweise  
 Das Attribut **Fall** C\+\+ verfügt über die gleichen Funktionen wie das **Fall** MIDL\-Attribut.  Dieses Attribut wird nur mit dem [switch\_type](../windows/switch-type.md)\-Attribut verwendet wird.  
  
## Beispiel  
 Im folgenden Code wird die Verwendung des **Fall**\-Attribut angezeigt:  
  
```  
// cpp_attr_ref_case.cpp  
// compile with: /LD  
#include <unknwn.h>  
[export]  
struct SizedValue2 {  
   [switch_type(char), switch_is(kind)] union {  
      [case(1), string]  
          wchar_t* wval;  
      [default, string]  
          char* val;  
   };  
    char kind;  
};  
[module(name="ATLFIRELib")];  
```  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|Member **Klasse** oder `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Typedef, Enum, Union, and Struct Attributes](../windows/typedef-enum-union-and-struct-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)