---
title: "local (C++)"
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
  - "vc-attr.local"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "local attribute"
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# local (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie im Header des Schnittstellen verwendet werden, können Sie den Generator als Header MIDL\-Compiler zu verwenden.  Wenn in einer einzelnen Funktion verwendet werden, legt eine lokale Prozedur fest, für die keine Stubs generiert werden.  
  
## Syntax  
  
```  
  
[local]  
  
```  
  
## Hinweise  
 Das Attribut `local` C\+\+ verfügt über die gleichen Funktionen wie das [Lokal](http://msdn.microsoft.com/library/windows/desktop/aa367071) MIDL\-Attribut.  
  
## Beispiel  
 Weitere Informationen finden Sie unter [call\_as](../windows/call-as.md) als Beispiel zur Verwendung `local`verwendet.  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|`interface`, Schnittstellenmethode|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|**dispinterface**|  
  
 Weitere Informationen finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Interface Attributes](../windows/interface-attributes.md)   
 [Method Attributes](../windows/method-attributes.md)   
 [call\_as](../windows/call-as.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)