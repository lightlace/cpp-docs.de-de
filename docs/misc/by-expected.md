---
title: "&quot;By&quot; erwartet."
ms.custom: na
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vbc36605"
  - "bc36605"
helpviewer_keywords: 
  - "BC36605"
ms.assetid: d0397b6e-bfc2-400c-92fc-efe82036cfdb
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "shoag"
manager: "wpickett"
---
# &quot;By&quot; erwartet.
Eine `Order By`\- oder `Group By`\-Klausel wurde ohne das `By`\-Schlüsselwort angegeben.  
  
 **Fehler\-ID:** BC36605  
  
### So beheben Sie diesen Fehler  
  
1.  Fügen Sie der `Order By`\- oder `Group By`\-Klausel das `By`\-Schlüsselwort hinzu. Im Folgenden finden Sie ein Beispiel dazu:  
  
    ```vb#  
    Dim customersByCountry = From cust In customers _  
                             Order By cust.Country, cust.City _  
                             Group By CountryName = cust.Country _  
                             Into RegionalCustomers = Group, Count() _  
                             Order By CountryName  
    ```  
  
## Siehe auch  
 [How to: Sort Query Results](../Topic/How%20to:%20Sort%20Query%20Results%20by%20Using%20LINQ%20\(Visual%20Basic\).md)   
 [Order By Clause](../Topic/Order%20By%20Clause%20\(Visual%20Basic\).md)   
 [Group By\-Klausel](../Topic/Group%20By%20Clause%20\(Visual%20Basic\).md)   
 [Introduction to LINQ in Visual Basic](../Topic/Introduction%20to%20LINQ%20in%20Visual%20Basic.md)   
 [LINQ](../Topic/LINQ%20in%20Visual%20Basic.md)