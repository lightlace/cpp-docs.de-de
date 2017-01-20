---
title: "object (C++)"
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
  - "vc-attr.object"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "object attribute"
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# object (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Identifiziert eine benutzerdefinierte Schnittstelle.  
  
## Syntax  
  
```  
  
[object]  
  
```  
  
## Hinweise  
 Wenn einer Schnittstellendefinition vorangestellt ist, wird das Attribut **Objekt** C\+\+ Schnittstelle in die IDL\-Datei als benutzerdefinierte Oberfläche abgelegt werden.  
  
 Alle Schnittstellen, die mit Objekt gekennzeichnet wird, muss der **IUnknown**erben.  Diese Bedingung ist wenn eine der Basisschnittstellen erben von **IUnknown**erfüllt.  Wenn keine Basisschnittstellen von **IUnknown**erben, führt der Compiler die Schnittstelle, die mit **Objekt** gekennzeichnet ist, um von **IUnknown**zu berechnen.  
  
## Beispiel  
 Weitere Informationen finden Sie unter [nonbrowsable](../windows/nonbrowsable.md) als Beispiel zur Verwendung **Objekt**verwendet.  
  
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
 [dual](../windows/dual.md)   
 [dispinterface](../windows/dispinterface.md)   
 [custom](../windows/custom-cpp.md)   
 [\_\_interface](../cpp/interface.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)