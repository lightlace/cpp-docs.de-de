---
title: "Die AddHandler-Methode und die RemoveHandler-Methode m&#252;ssen genau einen Parameter aufweisen."
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
  - "vbc31133"
  - "bc31133"
helpviewer_keywords: 
  - "BC31133"
ms.assetid: f6295626-dd63-408c-ab5f-76367f94d6ca
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "shoag"
manager: "wpickett"
---
# Die AddHandler-Methode und die RemoveHandler-Methode m&#252;ssen genau einen Parameter aufweisen.
Eine benutzerdefinierte Ereignisdeklaration muss `AddHandler`\- oder `RemoveHandler`\-Deklarationen aufweisen, von denen jede einen einzelnen Parameter des Delegattyps übernimmt, der durch die `As`Klausel des benutzerdefinierten Ereignisses angegeben wird.  
  
 **Fehler\-ID:** BC31133  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie die zusätzlichen Parameter aus der Parameterliste, und ändern Sie den Parametertyp in denselben Typ wie den Delegattyp, der von der `As`\-Klausel des benutzerdefinierten Ereignisses angegeben ist.  
  
## Beispiel  
 Dieses Beispiel zeigt ein benutzerdefiniertes Ereignis mit den richtigen Parametertypen für die Deklarationen `AddHandler` und `RemoveHandler`.  
  
 [!CODE [VbVbalrEventError#1](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrEventError#1)]  
  
## Siehe auch  
 [Event Statement](../Topic/Event%20Statement.md)   
 [AddHandler \- löschen](assetId:///fc464cf8-582c-48a6-a9c2-185c4c3d5ff8)   
 [RemoveHandler \- löschen](assetId:///35c17f61-6e22-4b87-b6e1-3ed0c27a88a0)   
 [Events](../Topic/Events%20\(Visual%20Basic\).md)