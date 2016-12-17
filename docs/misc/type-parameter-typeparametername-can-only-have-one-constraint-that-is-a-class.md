---
title: "Der Typparameter &#39;&lt;typparametername&gt;&#39; kann maximal eine Einschr&#228;nkung haben, die eine Klasse ist."
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
  - "bc32047"
  - "vbc32047"
helpviewer_keywords: 
  - "BC32047"
ms.assetid: ac7ab76b-5300-4c79-b519-5a1287ed5fa9
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Der Typparameter &#39;&lt;typparametername&gt;&#39; kann maximal eine Einschr&#228;nkung haben, die eine Klasse ist.
Eine Einschränkungsliste enthält mehr als eine Klasse.  
  
 Eine Einschränkungsliste für einen Typparameter kann eine beliebige Anzahl von Schnittstellen, aber höchstens eine Klasse akzeptieren. Ein für den Typparameter angegebenes Typargument muss von dieser Klasse erben, und [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] unterstützt keine Mehrfachvererbung.  
  
 **Fehler\-ID:** BC32047  
  
### So beheben Sie diesen Fehler  
  
-   Wählen Sie eine Klasse aus, und schließen Sie nur diese Klasse in die Einschränkungsliste ein.  
  
-   Möglicherweise können Sie weitere Typparameter definieren, um die Klasse oder Klassen zu berücksichtigen, die Sie in diese Einschränkungsliste nicht einschließen konnten.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)