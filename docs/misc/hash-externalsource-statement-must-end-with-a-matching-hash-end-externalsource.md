---
title: "&quot;#ExternalSource&quot; muss mit einem entsprechenden &quot;#End ExternalSource&quot; abgeschlossen werden."
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc30579"
  - "bc30579"
helpviewer_keywords: 
  - "BC30579"
ms.assetid: 8d658008-eddc-4b7d-a8d4-036da42957bf
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;#ExternalSource&quot; muss mit einem entsprechenden &quot;#End ExternalSource&quot; abgeschlossen werden.
Die `#ExternalSource`\-Direktive verweist auf äußeren Code, sodass der Compiler genau melden kann, wenn Ausnahmen innerhalb dieses Codes auftreten. Ein `#ExternalSource`\-Block muss mit `#ExternalSource` beginnen und mit `#End ExternalSource` enden.  
  
 **Fehler\-ID:** BC30579  
  
### So beheben Sie diesen Fehler  
  
1.  Fügen Sie `#End ExternalSource` an der gewünschten Stelle im Code hinzu.  
  
2.  Entfernen Sie `#ExternalSource` am Anfang, falls nicht erforderlich.  
  
## Siehe auch  
 [\#ExternalSource Directive](../Topic/%23ExternalSource%20Directive.md)   
 [NOTINBUILD: Bedingte Kompilierung \(Visual Basic\)](assetId:///ad1e35e0-935e-4a35-a2ae-738bcf2a9240)