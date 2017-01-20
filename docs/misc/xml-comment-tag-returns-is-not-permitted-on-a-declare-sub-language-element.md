---
title: "Das XML-Kommentartag &quot;returns&quot; ist f&#252;r ein &quot;declare sub&quot;-Sprachelement nicht zul&#228;ssig."
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
  - "bc42315"
  - "vbc42315"
helpviewer_keywords: 
  - "BC42315"
ms.assetid: 55ba3e8a-ba7f-42e3-a4a7-b22844e72564
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "shoag"
manager: "wpickett"
---
# Das XML-Kommentartag &quot;returns&quot; ist f&#252;r ein &quot;declare sub&quot;-Sprachelement nicht zul&#228;ssig.
Das XML\-Kommentartag "returns" ist für ein "declare sub"\-Sprachelement nicht zulässig. Der XML\-Kommentar wird ignoriert.  
  
 Ein XML\-Kommentar für eine `Declare Sub`\-Deklaration darf kein `<`returns`>`\-Tag enthalten.  
  
 **Fehler\-ID:** BC42315  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie das nicht unterstützte `<`returns`>`\-Tag.  
  
## Siehe auch  
 [\<returns\>](../Topic/%3Creturns%3E%20\(Visual%20Basic\).md)   
 [XML Comment Tags](../Topic/Recommended%20XML%20Tags%20for%20Documentation%20Comments%20\(Visual%20Basic\).md)   
 [Documenting Your Code with XML](../Topic/Documenting%20Your%20Code%20with%20XML%20\(Visual%20Basic\).md)   
 [Declare Statement](../Topic/Declare%20Statement.md)