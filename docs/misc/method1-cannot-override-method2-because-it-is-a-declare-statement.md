---
title: "&#39;&lt;Methode1&gt;&#39; kann &#39;&lt;Methode2&gt;&#39; nicht &#252;berschreiben, da sie eine &#39;Declare&#39;-Anweisung ist"
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
  - "vbc30474"
  - "bc30474"
helpviewer_keywords: 
  - "BC30474"
ms.assetid: 7277e8cc-aa3c-40c3-8682-c8c42d2ee921
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;Methode1&gt;&#39; kann &#39;&lt;Methode2&gt;&#39; nicht &#252;berschreiben, da sie eine &#39;Declare&#39;-Anweisung ist
Sie haben versucht, einen Delegat im Basisklassennamen zu überschreiben, der mit einer `Declare`\-Anweisung deklariert wurde.  
  
 **Fehler\-ID:** BC30474  
  
### So beheben Sie diesen Fehler  
  
1.  Ändern Sie das überschriebene Member, sodass es keine `Declare`\-Anweisung ist.  
  
2.  Versuchen Sie nicht, diese Methode überschreiben.  
  
## Siehe auch  
 [Declare Statement](../Topic/Declare%20Statement.md)   
 [NICHT IM BUILD: Überschreiben von Eigenschaften und Methoden](assetId:///2167e8f5-1225-4b13-9ebd-02591ba90213)