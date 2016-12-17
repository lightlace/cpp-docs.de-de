---
title: "SimplifiedChinese und VbStrConv.TraditionalChinese k&#246;nnen nicht kombiniert werden."
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
  - "vbrArgument_StrConvSCandTC"
ms.assetid: d8e6a11b-f549-43b5-8337-0594340e1325
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "shoag"
manager: "wpickett"
---
# SimplifiedChinese und VbStrConv.TraditionalChinese k&#246;nnen nicht kombiniert werden.
Die Anwendung versucht, die sich gegenseitig ausschließenden `VbStrConv`\-Enumerationsmember `SimplifiedChinese` und `TraditionalChinese` zu kombinieren.  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie entweder  `VbStrConv.SimplifiedChinese` oder `VbStrConv.TraditionalChinese`.  
  
## Siehe auch  
 <xref:System.Globalization>   
 [NICHT IM BUILD: VbStrConv\-Enumeration](assetId:///59f83dd9-6361-47df-a836-02ba9d4cb936)   
 [Einführung in internationale Anwendungen basierend auf .NET Framework](../Topic/Introduction%20to%20International%20Applications%20Based%20on%20the%20.NET%20Framework.md)