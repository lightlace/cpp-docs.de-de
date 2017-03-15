---
title: "entry | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.entry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "entry attribute"
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# entry
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt eine exportierte Funktion oder einer Konstanten in einem Modul indem die Bestimmung des Einstiegspunktes in der DLL an.  
  
## Syntax  
  
```  
  
      [ entry(  
   id  
) ]  
```  
  
#### Parameter  
 `id`  
 Die ID des Einstiegspunktes.  
  
## Hinweise  
 Das Attribut **Eingabe** C\+\+ verfügt über die gleichen Funktionen wie das [Eingabe](http://msdn.microsoft.com/library/windows/desktop/aa366815) MIDL\-Attribut.  
  
## Beispiel  
 Weitere Informationen finden Sie im Beispiel für die Verwendung [idl\_module](../windows/idl-module.md) als Beispiel für **Eingabe**.  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|`idl_module`\-Attribut|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)