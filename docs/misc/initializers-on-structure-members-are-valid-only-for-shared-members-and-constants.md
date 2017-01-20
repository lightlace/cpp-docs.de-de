---
title: "Initialisierer f&#252;r Strukturmember sind nur f&#252;r Shared-Member und -Konstanten g&#252;ltig."
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
  - "bc31049"
  - "vbc31049"
helpviewer_keywords: 
  - "BC31049"
ms.assetid: 8356978e-7f84-4932-be0f-dda005c9f8ca
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "shoag"
manager: "wpickett"
---
# Initialisierer f&#252;r Strukturmember sind nur f&#252;r Shared-Member und -Konstanten g&#252;ltig.
Eine Strukturmembervariable wurde als Teil ihrer Deklaration initialisiert.  
  
 **Fehler\-ID:** BC31049  
  
### So beheben Sie diesen Fehler  
  
-   Verwenden Sie eine Konstante anstelle eine Variablen.  
  
-   Fügen Sie der Struktur einen parametrisierten Konstruktor hinzu. Zum Beispiel:  
  
    ```  
    Structure TestStruct Public t As Integer Sub New(ByVal Tval As Integer) t = Tval End Sub End Structure  
    ```  
  
## Siehe auch  
 [How to: Declare a Structure](../Topic/How%20to:%20Declare%20a%20Structure%20\(Visual%20Basic\).md)   
 [Constants and Enumerations](../Topic/Constants%20and%20Enumerations%20in%20Visual%20Basic.md)