---
title: "&quot;#Region&quot; muss mit einem entsprechenden &quot;#End Region&quot; abgeschlossen werden."
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "bc30681"
  - "vbc30681"
helpviewer_keywords: 
  - "BC30681"
ms.assetid: 05a0402b-da68-4ab8-b6d6-940379bc5973
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;#Region&quot; muss mit einem entsprechenden &quot;#End Region&quot; abgeschlossen werden.
Mit der `#Region`\-Direktive können Sie einen Codeblock festlegen, der bei Verwendung der Gliederungsfunktion des Code\-Editors von [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] erweitert oder reduziert werden kann. Start und Ende von `#Region`\-Anweisungen müssen sich im selben Codeblock befinden.  
  
 **Fehler\-ID:** BC30681  
  
### So beheben Sie diesen Fehler  
  
1.  Fügen Sie `#End Region` an der geeigneten Stelle im Code nach der `#Region`\-Anweisung ein.  
  
## Siehe auch  
 [\#Region Directive](../Topic/%23Region%20Directive.md)