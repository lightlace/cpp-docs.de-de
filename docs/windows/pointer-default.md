---
title: "pointer_default"
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
  - "vc-attr.pointer_default"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pointer_default attribute"
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# pointer_default
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt die Standardzeiger Attribut für alle Zeiger, außer Zeiger auf oberster Ebene angezeigt, die in den Parameterlisten enthalten sein.  
  
## Syntax  
  
```  
  
      [ pointer_default(  
   value  
) ]  
```  
  
#### Parameter  
 *Wert*  
 Ein Wert, der den Zeigertyp beschrieben werden: **PTR**, `ref`oder **eindeutig**.  
  
## Hinweise  
 Das Attribut **pointer\_default** C\+\+ verfügt über die gleichen Funktionen wie das [pointer\_default](http://msdn.microsoft.com/library/windows/desktop/aa367141) MIDL\-Attribut.  
  
## Beispiel  
 Weitere Informationen finden Sie im Beispiel für [defaultvalue](../windows/defaultvalue.md) B. für eine Verwendung von **pointer\_default**.  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|`interface`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)