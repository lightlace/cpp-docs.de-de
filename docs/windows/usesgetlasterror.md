---
title: "usesgetlasterror"
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
  - "vc-attr.usesgetlasterror"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "usesgetlasterror attribute"
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# usesgetlasterror
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erklärt den Aufrufer, dass bei einem Fehler auftreten, falls diese Funktion aufruft, gibt der Aufrufer `GetLastError` aufrufen kann, um den Fehlercode abzurufen.  
  
## Syntax  
  
```  
  
[usesgetlasterror]  
  
```  
  
## Hinweise  
 Das Attribut **usesgetlasterror** C\+\+ verfügt über die gleichen Funktionen wie das [usesgetlasterror](http://msdn.microsoft.com/library/windows/desktop/aa367297) MIDL\-Attribut.  
  
## Beispiel  
 Weitere Informationen finden Sie im [idl\_module](../windows/idl-module.md) Beispiel für ein Beispiel dafür, wie **usesgetlasterror**verwendet.  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|Modulattribut|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)