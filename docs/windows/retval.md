---
title: "retval"
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
  - "vc-attr.retval"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "retval attribute"
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# retval
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Legt den Parameter ab, der den Rückgabewert des Members erhält.  
  
## Syntax  
  
```  
  
[retval]  
  
```  
  
## Hinweise  
 Das Attribut **retval** C\+\+ verfügt über die gleichen Funktionen wie das [retval](http://msdn.microsoft.com/library/windows/desktop/aa367158) MIDL\-Attribut.  
  
 **retval** muss auf dem letzten Argument in einer Deklaration der Funktion angezeigt werden.  
  
## Beispiel  
 Weitere Informationen finden Sie im Beispiel für [bindbar](../windows/bindable.md) B. für eine Verwendung von **retval**.  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|Schnittstellen für, Schnittstellenmethode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**out**|  
|**Ungültige Attribute**|**in**|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Parameter Attributes](../windows/parameter-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)