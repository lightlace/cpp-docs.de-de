---
title: "Typ oder &#39;With&#39; erwartet"
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
  - "vbc30988"
  - "bc30988"
helpviewer_keywords: 
  - "BC30988"
ms.assetid: ab9c0cee-9fe4-4764-a3c2-aec16e709d4c
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "shoag"
manager: "wpickett"
---
# Typ oder &#39;With&#39; erwartet
Wenn Sie eine Instanz einer Klasse deklarieren, muss auf das Schlüsselwort `New` ein Typname oder `With` folgen. Die folgenden Anweisungen deklarieren z. B. jeweils, dass `client` eine Instanz der `Customer`\-Klasse ist. Der Typname `Customer` folgt auf `New`.  
  
```  
' Dim client As New Customer()  
' The next declaration uses an object initializer.  
Dim client As New Customer() With {.Name = "Litware, Inc."}  
```  
  
 Beginnend mit [!INCLUDE[vb_orcas_long](../misc/includes/vb_orcas_long_md.md)] können Sie ein Objekt als eine Instanz eines anonymen Typs deklarieren. In diesem Fall geben Sie keinen Datentyp an. In Deklarationen anonymer Typen folgt das Schlüsselwort `With` auf `New`.  
  
```  
Dim person = New With {.Name ="Mike Nash", .Age = 27}  
```  
  
 **Fehler\-ID:** BC30988  
  
### So beheben Sie diesen Fehler  
  
-   Ändern Sie die Deklaration so, dass `With` oder ein Typname auf `New` folgt.  
  
## Siehe auch  
 [Anonymous Types](../Topic/Anonymous%20Types%20\(Visual%20Basic\).md)   
 [Object Initializers: Named and Anonymous Types](../Topic/Object%20Initializers:%20Named%20and%20Anonymous%20Types%20\(Visual%20Basic\).md)   
 [New Operator](../Topic/New%20Operator%20\(Visual%20Basic\).md)   
 [NotInBuild: Deklarationsanweisungen in Visual Basic](assetId:///81f3c398-f45c-4d95-80bf-aa39d1a0fb30)