---
title: "Microsoft.VisualBasic.ComClassAttribute und &#39;&lt;attribut&gt;&#39; k&#246;nnen nicht zusammen auf dieselbe Klasse angewendet werden."
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc32501"
  - "bc32501"
helpviewer_keywords: 
  - "BC32501"
ms.assetid: dc1bf4f1-f030-4df3-aae8-524af9c2fda7
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Microsoft.VisualBasic.ComClassAttribute und &#39;&lt;attribut&gt;&#39; k&#246;nnen nicht zusammen auf dieselbe Klasse angewendet werden.
Ein `COMClassAttribute`\-Attributblock wird in Verbindung mit einem Attribut verwendet, das nicht für COM\-Objekte gültig ist. Eine mögliche Ursache besteht in der Vermischung von [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)]\- und COM\-Attributen.  
  
 **Fehler\-ID:** BC32501  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie entweder den `COMClassAttribute`\-Attributblock oder das Attribut, das nicht für COM gilt.  
  
## Siehe auch  
 [NICHT IM BUILD: In Visual Basic verwendete Attribute](assetId:///22231318-8a40-49af-9245-e0aab723563b)   
 [NICHT IM BUILD: Anwendung von Attributen](assetId:///2b1703ed-4437-49b3-bc0b-568094324f47)   
 [ComClassAttribute\-Klasse](assetId:///5c2f0835-9210-47dc-bc59-5c1769953574)