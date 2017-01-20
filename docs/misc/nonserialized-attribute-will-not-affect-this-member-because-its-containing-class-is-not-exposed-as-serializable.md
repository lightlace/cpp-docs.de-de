---
title: "Das NonSerialized-Attribut hat auf diesen Member keine Auswirkungen, da die enthaltende Klasse nicht als &quot;Serializable&quot; verf&#252;gbar gemacht wurde."
ms.custom: na
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc30772"
  - "bc30772"
helpviewer_keywords: 
  - "BC30772"
ms.assetid: 1014e944-40c1-4078-8a38-139736ef89da
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Das NonSerialized-Attribut hat auf diesen Member keine Auswirkungen, da die enthaltende Klasse nicht als &quot;Serializable&quot; verf&#252;gbar gemacht wurde.
Standardmäßig sind die Klassen und ihre Member nicht serialisierbar. Das <xref:System.NonSerializedAttribute>\-Attribut ist nur erforderlich, wenn ein Member einer serialisierbaren Klasse nicht serialisiert werden soll.  
  
 **Fehler\-ID:** BC30772  
  
### So beheben Sie diesen Fehler  
  
-   Fügen Sie der Klasse das <xref:System.SerializableAttribute>\-Attribut hinzu.  
  
     – oder –  
  
-   Entfernen Sie das <xref:System.NonSerializedAttribute>\-Attribut von dem Member.  
  
## Siehe auch  
 <xref:System.NonSerializedAttribute>   
 <xref:System.SerializableAttribute>   
 [NICHT IM BUILD: Attribute in Visual Basic](assetId:///620bfc0e-4582-4c8b-8432-ebc5c3dccc22)