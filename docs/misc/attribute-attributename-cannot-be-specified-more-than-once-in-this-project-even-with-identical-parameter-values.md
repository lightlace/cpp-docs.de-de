---
title: "Das Attribut &quot;&lt;Attributname&gt;&quot; kann in diesem Projekt nicht mehrmals angegeben werden, selbst wenn die Parameterwerte identisch sind."
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "bc41000"
  - "vbc41000"
helpviewer_keywords: 
  - "BC41000"
ms.assetid: 7e846177-7b89-44da-8f17-cdc8606ef148
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Das Attribut &quot;&lt;Attributname&gt;&quot; kann in diesem Projekt nicht mehrmals angegeben werden, selbst wenn die Parameterwerte identisch sind.
Ein benutzerdefiniertes Attribut ist für dasselbe Programmierelement mehrmals angegeben. <xref:System.AttributeUsageAttribute> wird jedoch auf das benutzerdefinierte Attribut angewendet, und die <xref:System.AttributeUsageAttribute.AllowMultiple*>\-Eigenschaft wird auf `False` festgelegt.<xref:System.AttributeUsageAttribute.AllowMultiple*> steuert, ob das Attribut mehrmals verwendet werden kann.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md).  
  
 **Fehler\-ID:** BC41000  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie die zusätzliche Angabe des benutzerdefinierten Attributs, oder legen Sie im darauf angewendeten <xref:System.AttributeUsageAttribute><xref:System.AttributeUsageAttribute.AllowMultiple*> auf `True` fest.  
  
## Siehe auch  
 <xref:System.AttributeUsageAttribute>   
 <xref:System.AttributeUsageAttribute.AllowMultiple*>   
 [NICHT IM BUILD: Anwendung von Attributen](assetId:///2b1703ed-4437-49b3-bc0b-568094324f47)