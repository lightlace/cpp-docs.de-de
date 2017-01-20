---
title: "Analysefehler in XML-Dokumentation: F&#252;r das Starttag &quot;&lt;Tag&gt;&quot; ist kein entsprechendes Endtag vorhanden."
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
  - "vbc42316"
  - "BC42316"
helpviewer_keywords: 
  - "BC42316"
ms.assetid: 45b68176-ebf6-43af-820e-6801aabb6c57
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "shoag"
manager: "wpickett"
---
# Analysefehler in XML-Dokumentation: F&#252;r das Starttag &quot;&lt;Tag&gt;&quot; ist kein entsprechendes Endtag vorhanden.
Analysefehler in XML\-Dokumentation: Für das Starttag "\<Tag\>" ist kein entsprechendes Endtag vorhanden. Der XML\-Kommentar wird ignoriert.  
  
 Der XML\-Kommentar enthält ein Starttag, jedoch keine entsprechendes Endtag.  
  
 **Fehler\-ID:** BC42316  
  
### So beheben Sie diesen Fehler  
  
-   Fügen Sie ein Endtag hinzu, das dem Starttag entspricht.  
  
     Oder...  
  
-   Wenn das Tag keinen inneren Text \(z. B. [\<seealso\>](../Topic/%3Cseealso%3E%20\(Visual%20Basic\).md)\) enthält, geben Sie vor der schließenden Winkelklammer einen Schrägstrich ein.  
  
## Siehe auch  
 [XML Comment Tags](../Topic/Recommended%20XML%20Tags%20for%20Documentation%20Comments%20\(Visual%20Basic\).md)   
 [Documenting Your Code with XML](../Topic/Documenting%20Your%20Code%20with%20XML%20\(Visual%20Basic\).md)