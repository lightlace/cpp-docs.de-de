---
title: "An dieser Stelle darf das Fragezeichen (?) nicht verwendet werden."
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
  - "bc36637"
  - "vbc36637"
helpviewer_keywords: 
  - "BC36637"
ms.assetid: a54c46e7-8fd8-4941-9fce-72f2b41b5e24
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "shoag"
manager: "wpickett"
---
# An dieser Stelle darf das Fragezeichen (?) nicht verwendet werden.
Das Fragezeichen \(?\) kann verwendet werden, um anzugeben, dass ein Werttyp oder eine Struktur NULL\-Werte zulässt. Die Verwendung in anderen Fällen ist eingeschränkt. Der folgende Code generiert beispielsweise diese Ausnahme.  
  
```  
' Not valid. ' #Const found = True?  
```  
  
 **Fehler\-ID:** BC36637  
  
### So beheben Sie diesen Fehler  
  
-   Entfernen Sie das Fragezeichen \(?\) aus der Deklaration.  
  
## Siehe auch  
 [Nullable Value Types](../Topic/Nullable%20Value%20Types%20\(Visual%20Basic\).md)