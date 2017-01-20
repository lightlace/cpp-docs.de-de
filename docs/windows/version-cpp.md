---
title: "version (C++)"
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
  - "vc-attr.version"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "version attribute"
  - "version information, version attribute"
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# version (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Identifiziert eine bestimmte Version für mehrere Versionen einer Klasse.  
  
## Syntax  
  
```  
  
      [ version(  
   "version"  
) ]  
```  
  
#### Parameter  
 *Version*  
 Die Versionsnummer der Co\-Klasse.  Wenn sie nicht angegeben wird, werden 1.0 in die IDL\-Datei abgelegt.  
  
## Hinweise  
 Das Attribut **Version** C\+\+ verfügt über die gleichen Funktionen wie das [Version](http://msdn.microsoft.com/library/windows/desktop/aa367306) MIDL\-Attribut und wird von der generierten IDL\-Datei übergeben.  
  
## Beispiel  
 Weitere Informationen finden Sie im [bindbar](../windows/bindable.md) Beispiel für eine Beispiel verwenden aus **Version**.  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|**Klasse**, `struct`|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|**Co\-Klasse**|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Class Attributes](../windows/class-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)