---
title: "Auf &quot;MyBase&quot; m&#252;ssen &quot;.&quot; und ein Bezeichner folgen"
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
  - "bc32027"
  - "vbc32027"
helpviewer_keywords: 
  - "BC32027"
ms.assetid: 39e5512c-ef1e-46a3-a96c-277ea24bfee2
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# Auf &quot;MyBase&quot; m&#252;ssen &quot;.&quot; und ein Bezeichner folgen
`MyBase` ist keine echte Objektvariable und darf nicht allein stehen. Es wird nur verwendet, um auf einen Member der Basisklasse der aktuellen Instanz zuzugreifen.  
  
 **Fehler\-ID:** BC32027  
  
### So beheben Sie diesen Fehler  
  
-   Wenn Sie Memberzugriff vorsehen, geben Sie den Memberzugriffsoperator \(.\) und ein Member der Basisklasse nach `MyBase` an.  
  
-   Wenn Sie keinen Memberzugriff vorsehen, deklarieren und initialisieren Sie eine Instanz der Basisklasse, oder entfernen Sie den Verweis auf `MyBase`.  
  
## Siehe auch  
 [MyBase \- löschen](assetId:///52491d06-6451-4f6f-9aa6-8fab59bbc2b9)   
 [Inheritance Basics](../Topic/Inheritance%20Basics%20\(Visual%20Basic\).md)