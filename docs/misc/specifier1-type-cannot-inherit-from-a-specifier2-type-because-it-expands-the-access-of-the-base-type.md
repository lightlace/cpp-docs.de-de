---
title: "&lt;Bezeichner1&gt; &lt;Typ&gt; erweitert den Zugriff von Basis-&lt;Typ&gt; und kann nicht von &lt;Bezeichner2&gt; &lt;Typ&gt; erben."
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
  - "bc30509"
  - "vbc30509"
helpviewer_keywords: 
  - "BC30509"
ms.assetid: 53594d6e-5e6d-463d-aa68-e2d41e152da7
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;Bezeichner1&gt; &lt;Typ&gt; erweitert den Zugriff von Basis-&lt;Typ&gt; und kann nicht von &lt;Bezeichner2&gt; &lt;Typ&gt; erben.
Sie haben versucht, für eine öffentliche Klasse zu veranlassen, dass sie von einer Basisklasse erbt, die als `Private` oder `Friend` gekennzeichnet ist.  
  
 **Fehler\-ID:** BC30509  
  
### So beheben Sie diesen Fehler  
  
-   Deklarieren Sie die Basisklasse als `Public`, oder deklarieren Sie die erbende Klasse als `Private` oder `Friend`.  
  
## Siehe auch  
 [NICHT IM BUILD: Vererbung in Visual Basic](assetId:///e5e6e240-ed31-4657-820c-079b7c79313c)