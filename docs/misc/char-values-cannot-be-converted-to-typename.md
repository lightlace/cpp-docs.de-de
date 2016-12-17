---
title: "&#39;Char&#39;-Werte k&#246;nnen nicht in &#39;&lt;Typname&gt;&#39; konvertiert werden."
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
  - "bc32006"
  - "vbc32006"
helpviewer_keywords: 
  - "BC32006"
ms.assetid: c033f65e-a315-47fc-be2e-ed371847a221
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Char&#39;-Werte k&#246;nnen nicht in &#39;&lt;Typname&gt;&#39; konvertiert werden.
'Char'\-Werte können nicht in '\<Typname\>' konvertiert werden. Verwenden Sie „Microsoft.VisualBasic.AscW“, um ein Zeichen als Unicode\-Wert zu interpretieren, oder „Microsoft.VisualBasic.Val“, um es als Ziffer zu interpretieren.  
  
 Ein Ausdruck versucht, einen `Char`\-Wert in einen anderen Datentyp als `String` oder `Object` zu konvertieren.  
  
 **Fehler\-ID:** BC32006  
  
### So beheben Sie diesen Fehler  
  
-   Verwenden Sie die `AscW`\-Funktion, um einen `Char`\-Wert als Unicode\-Zeichencode zu interpretieren, oder verwenden Sie die `Val`\-Funktion, um ihn als numerische Ziffer zu interpretieren.  
  
## Siehe auch  
 [NICHT IM BUILD: Asc\-, AscW\-Funktionen](assetId:///6814bfec-12ba-41fb-b10e-bec99750d5e1)   
 [NICHT IM BUILD: Val\-Funktion](assetId:///81650f77-9242-4ec1-8e04-e93b5daa451d)   
 [Char Data Type](../Topic/Char%20Data%20Type%20\(Visual%20Basic\).md)