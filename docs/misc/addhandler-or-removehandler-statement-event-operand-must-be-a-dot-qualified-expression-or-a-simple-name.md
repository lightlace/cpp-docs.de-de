---
title: "Der AddHandler- oder RemoveHandler-Anweisungsereignisoperand muss ein punktqualifizierter Ausdruck oder ein einfacher Name sein."
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
  - "vbc30677"
  - "bc30677"
helpviewer_keywords: 
  - "BC30677"
ms.assetid: b71eb2f0-0bb2-4aeb-94ec-5c37ab960d9e
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "shoag"
manager: "wpickett"
---
# Der AddHandler- oder RemoveHandler-Anweisungsereignisoperand muss ein punktqualifizierter Ausdruck oder ein einfacher Name sein.
Das für das Ereignisargument für `AddHandler` oder `RemoveHandler` angegebene Element wurde nicht als Ereignis erkannt.  
  
 **Fehler\-ID:** BC30677  
  
### So beheben Sie diesen Fehler  
  
-   Geben Sie den Namen des Objekts, das das Ereignis auslöst, gefolgt von einem Punkt \(`.`\) und den Ereignisnamen wie im folgenden Beispiel an.  
  
     [!CODE [VbVbalrEventError#30](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEventError#30)]  
  
## Siehe auch  
 [AddHandler Statement](../Topic/AddHandler%20Statement.md)   
 [RemoveHandler Statement](../Topic/RemoveHandler%20Statement.md)   
 [NICHT IM BUILD: AddHandler und RemoveHandler](assetId:///a7a24bd2-519a-46fe-8a2c-2b9df2ca28ef)   
 [Events](../Topic/Events%20\(Visual%20Basic\).md)