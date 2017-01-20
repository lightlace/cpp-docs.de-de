---
title: "Der Custom-Modifizierer ist f&#252;r Ereignisse, die in Schnittstellen deklariert sind, nicht g&#252;ltig."
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
  - "bc31121"
  - "vbc31121"
helpviewer_keywords: 
  - "BC31121"
ms.assetid: b5687034-a2b2-4961-88b7-0ba73023573e
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Der Custom-Modifizierer ist f&#252;r Ereignisse, die in Schnittstellen deklariert sind, nicht g&#252;ltig.
Ein benutzerdefiniertes Ereignis kann nicht in einer Schnittstelle deklariert werden, da ein benutzerdefiniertes Ereignis eine Implementierung seiner `AddHandler`\-, `RemoverHandler`\- und `RaiseEvent`\-Methoden bereitstellen muss.  
  
 Das `Custom`\-Schlüsselwort kann in einer abgeleiteten Klasse verwendet werden, die das Ereignis implementiert.  
  
 **Fehler\-ID:** BC31121  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie das `Custom`\-Schlüsselwort aus der Ereignisdeklaration in der Schnittstelle.  
  
## Beispiel  
 In diesem Beispiel wird veranschaulicht, wie ein in einer Schnittstelle deklariertes Ereignis als benutzerdefiniertes Ereignis implementiert wird.  
  
 [!CODE [VbVbalrEventError#3](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEventError#3)]  
  
## Siehe auch  
 [Benutzerdefiniert – Löschen](assetId:///dc62be07-c896-4866-a533-982a661d143f)   
 [Event Statement](../Topic/Event%20Statement.md)   
 [Delegate Statement](../Topic/Delegate%20Statement.md)   
 [Class Statement](../Topic/Class%20Statement%20\(Visual%20Basic\).md)   
 [Interface Statement](../Topic/Interface%20Statement%20\(Visual%20Basic\).md)   
 [Events](../Topic/Events%20\(Visual%20Basic\).md)