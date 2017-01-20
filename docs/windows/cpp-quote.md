---
title: "cpp_quote"
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
  - "vc-attr.cpp_quote"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cpp_quote attribute"
ms.assetid: f75327ff-42bd-498b-9177-7ffa25427e1f
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# cpp_quote
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt die angegebene Zeichenfolge in Anführungszeichen, ohne dass die generierten IDL\-Datei ab.  
  
## Syntax  
  
```  
  
      [ cpp_quote(  
   "statement"  
) ];  
```  
  
#### Parameter  
 *statement*  
 Wechselstrom\-Anweisung.  
  
## Hinweise  
 Das Attribut **cpp\_quote** C\+\+ ist nützlich, wenn Präprozessordirektiven in eine IDL\-Datei einfügen möchten.  
  
 Sie können auch **cpp\_quote** verwenden und eine H\-Datei als Teil der MIDL\-Kompilierung generieren.  Wenn Sie beispielsweise Headerdatei Ein C\+\+\-Compiler verfügen, die Attribute IDL C\+\+ verwendet, aber diese Datei für jede Aufgabe nicht verwenden können, können Sie sie kompilieren, um eine MIDL\-generierte H\-Datei erstellen, die Sie berücksichtigen sollten in Erwägung ziehen.  
  
 Das **cpp\_quote**\-Attribut verfügt über die gleichen Funktionen wie das [cpp\_quote](http://msdn.microsoft.com/library/windows/desktop/aa366765) MIDL\-Attribut.  
  
## Beispiel  
 Weitere Informationen finden Sie im Beispiel für die Verwendung [dual](../windows/dual.md) finden Sie ein Beispiel, wie **cpp\_quote**verwendet.  
  
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
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../windows/stand-alone-attributes.md)   
 [Attributes Samples](assetId:///558ebdb2-082f-44dc-b442-d8d33bf7bdb8)