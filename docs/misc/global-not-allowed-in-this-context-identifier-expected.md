---
title: "„Global“ ist in diesem Kontext nicht zul&#228;ssig. Es wird ein Bezeichner erwartet."
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
  - "vbc36001"
  - "bc36001"
helpviewer_keywords: 
  - "BC36001"
ms.assetid: d515daa2-f53d-424c-81fd-e9c4b12f331b
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# „Global“ ist in diesem Kontext nicht zul&#228;ssig. Es wird ein Bezeichner erwartet.
Das `Global`\-Schlüsselwort wird in einer Anweisung verwendet, in der es nicht zulässig ist.  
  
 Das `Global`\-Schlüsselwort ermöglicht Ihnen den Zugriff auf einen Namespace, der außerhalb der Namespacehierarchie definiert ist, in der der Code kompiliert werden soll.`Global` startet den Qualifizierungspfad auf der äußersten Namespaceebene der .NET Framework\-Klassenbibliothek. Eine Veranschaulichung finden Sie unter [Global – Löschen](assetId:///18c8ba14-40f6-4978-8096-6a5852324635).  
  
 Bestimmte Anweisungen, wie z. B. `Imports` und `Namespace`, sind unabhängig vom Namespace, in dem der Code kompiliert werden soll. Es ist ein vollständiger Qualifizierungspfad erforderlich, beginnend mit dem Namespace auf Stammebene, z. B. <xref:System> oder <xref:Microsoft.VisualBasic>. In solchen Aussagen ist das `Global`\-Schlüsselwort überflüssig und nicht erlaubt.  
  
 **Fehler\-ID:** BC36001  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie das `Global`\-Schlüsselwort aus der Anweisung. Es ist nicht erforderlich.  
  
## Siehe auch  
 [Global – Löschen](assetId:///18c8ba14-40f6-4978-8096-6a5852324635)   
 [Imports Statement \(.NET Namespace and Type\)](../Topic/Imports%20Statement%20\(.NET%20Namespace%20and%20Type\).md)   
 [Namespace Statement](../Topic/Namespace%20Statement.md)   
 [References and the Imports Statement](../Topic/References%20and%20the%20Imports%20Statement%20\(Visual%20Basic\).md)