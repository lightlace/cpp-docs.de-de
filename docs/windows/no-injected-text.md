---
title: "no_injected_text | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.no_injected_text"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "no_injected_text attribute"
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# no_injected_text
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verhindert, dass der Compiler Code aufgrund der Attributverwendung einfügt.  
  
## Syntax  
  
```  
  
      [ no_injected_text(  
   boolean  
) ];  
```  
  
#### Parameter  
 `boolean`\(optional\)  
 **true** , wenn Sie keinen eingefügten Code sollen, **false** eingefügt werden soll, um den Code zu ermöglichen.  **true** ist die Standardeinstellung.  
  
## Hinweise  
 Die häufigste Verwendung des Attributs **no\_injected\_text** C\+\+ wurde durch die [\/Fx](../build/reference/fx-merge-injected-code.md)\-Compileroption, die das **no\_injected\_text**\-Attribut in die MRG\-Datei einfügt.  
  
## Anforderungen  
  
### Attribut\-Kontext  
  
|||  
|-|-|  
|**Betrifft**|Überall|  
|**Wiederholbar**|Nein|  
|**Erforderliche Attribute**|None|  
|**Ungültige Attribute**|None|  
  
 Weitere Informationen über das kontexte finden Sie unter [Attribut\-Kontexte](../windows/attribute-contexts.md).  
  
## Siehe auch  
 [Compiler Attributes](../windows/compiler-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)