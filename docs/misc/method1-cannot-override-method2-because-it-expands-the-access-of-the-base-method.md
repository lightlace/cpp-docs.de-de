---
title: "&#39;&lt;Methode1&gt;&#39; kann &#39;&lt;Methode2&gt;&#39; nicht &#252;berschrieben, da sie den Zugriff der Basismethode erweitert."
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
  - "vbc32203"
  - "bc32203"
helpviewer_keywords: 
  - "BC32203"
ms.assetid: ef7816a4-5f57-4346-80fc-9311bc150b6b
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;Methode1&gt;&#39; kann &#39;&lt;Methode2&gt;&#39; nicht &#252;berschrieben, da sie den Zugriff der Basismethode erweitert.
Eine Prozedur gibt `Overrides` an, deklariert den Zugriff aber weniger restriktiv als die zu überschreibende Methode. Sie können den Zugriff nicht erweitern, was bedeutet, dass Sie die überschreibende Methode nicht zugänglicher als die Methode machen können, die sie überschreibt. Wenn z. B. die Basisklassenmethode `Protected` ist, können Sie sie nicht mit einer `Public`\-Methode überschreiben.  
  
 **Fehler\-ID:** BC32203  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie das `Overrides`\-Schlüsselwort, oder ändern Sie den Zugriff, damit dieser mindestens so restriktiv wie bei der Basisklassenmethode ist.  
  
## Siehe auch  
 [NICHT IM BUILD: Überschreiben von Eigenschaften und Methoden](assetId:///2167e8f5-1225-4b13-9ebd-02591ba90213)   
 [Access Levels in Visual Basic](../Topic/Access%20Levels%20in%20Visual%20Basic.md)   
 [Shadowing in Visual Basic](../Topic/Shadowing%20in%20Visual%20Basic.md)