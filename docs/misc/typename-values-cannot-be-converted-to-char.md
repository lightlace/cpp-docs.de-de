---
title: "&#39;&lt;typname&gt;&#39;-Werte k&#246;nnen nicht in &#39;Char&#39; konvertiert werden"
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
  - "bc32007"
  - "vbc32007"
helpviewer_keywords: 
  - "BC32007"
ms.assetid: b04212da-57ac-4493-9480-04c12b50f875
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typname&gt;&#39;-Werte k&#246;nnen nicht in &#39;Char&#39; konvertiert werden
'\<typname\>'\-Werte können nicht in 'Char' konvertiert werden. Verwenden Sie Microsoft.VisualBasic.ChrW, um einen numerischen Wert als Unicode\-Zeichen zu interpretieren, oder konvertieren Sie ihn zuerst in 'String', um eine Ziffer zu erzeugen.  
  
 Ein Ausdruck versucht, einen anderen Datentyp als `String` oder `Object` in `Char` zu konvertieren.  
  
 **Fehler\-ID:** BC32007  
  
### So beheben Sie diesen Fehler  
  
-   Verwenden Sie die `ChrW`\-Funktion, um einen numerischen Wert in ein Unicode\-Zeichen oder den Wert zuerst in `String` und dann in `Char` zu konvertieren.  
  
## Siehe auch  
 [NICHT IM BUILD: Funktionen 'Chr', 'ChrW'](assetId:///37f3c707-8a6f-4c51-9b02-9e634c4299ab)   
 [Implicit and Explicit Conversions](../Topic/Implicit%20and%20Explicit%20Conversions%20\(Visual%20Basic\).md)   
 [Char Data Type](../Topic/Char%20Data%20Type%20\(Visual%20Basic\).md)