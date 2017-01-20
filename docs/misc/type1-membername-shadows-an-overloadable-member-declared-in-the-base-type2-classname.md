---
title: "&lt;typ1&gt; &#39;&lt;membername&gt;&#39; f&#252;hrt Shadowing f&#252;r einen &#252;berladbaren Member aus, der in Basis-&lt;type&gt; &#39;&lt;klassenname&gt;&#39; deklariert ist"
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
  - "bc40003"
  - "vbc40003"
helpviewer_keywords: 
  - "BC40003"
ms.assetid: 1e0d2061-0ad9-4915-b946-d55cb5d5ee80
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;typ1&gt; &#39;&lt;membername&gt;&#39; f&#252;hrt Shadowing f&#252;r einen &#252;berladbaren Member aus, der in Basis-&lt;type&gt; &#39;&lt;klassenname&gt;&#39; deklariert ist
\<typ1\> '\<membername\>' führt Shadowing für einen überladbaren Member aus, der in Basis\-\<type\> '\<klassenname\>' deklariert ist. Wenn Sie die Basismethode überladen möchten, muss die Methode als 'Overloads' deklariert werden.  
  
 Eine abgeleitete Klasse definiert eine `Function` oder `Sub`\-Prozedur oder eine `Property` mit dem gleichen Namen wie eine in der Basisklasse definierte Prozedur oder Eigenschaft. Da Prozeduren und Eigenschaften überladbare Member sind, kann die abgeleitete Klasse entweder überladen oder Shadowing für den Basisklassenmember ausführen. Der Code der abgeleiteten Klasse gibt jedoch weder [Overloads](../Topic/Overloads%20\(Visual%20Basic\).md) noch [Shadows](../Topic/Shadows%20\(Visual%20Basic\).md) in der Deklaration an. Bei Abwesenheit beider Schlüsselwörter geht der Compiler von `Shadows` aus.  
  
 Im Sinne eines guten Programmierstils geben Sie entweder `Overloads` oder `Shadows` an. Dadurch wird Ihr Code einfacher zu lesen und zu verstehen.  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md).  
  
 **Fehler\-ID:** BC40003  
  
### So beheben Sie diesen Fehler  
  
-   Wenn Sie die Basisklassenmethode oder \-eigenschaft überladen möchten, schließen Sie das Schlüsselwort `Overloads` in die Deklaration ein.  
  
-   Wenn Sie Shadowing für die Basisklassenmethode oder \-eigenschaft ausführen möchten, schließen Sie das Schlüsselwort `Shadows` anstelle von `Overloads` ein.  
  
-   Wenn Sie das Basisklassenmember weder überladen noch Shadowing für es ausführen möchten, ändern Sie den Namen des abgeleiteten Klassenmembers.  
  
## Siehe auch  
 [Procedure Overloading](../Topic/Procedure%20Overloading%20\(Visual%20Basic\).md)   
 [Overloads](../Topic/Overloads%20\(Visual%20Basic\).md)   
 [Shadows](../Topic/Shadows%20\(Visual%20Basic\).md)   
 [Shadowing in Visual Basic](../Topic/Shadowing%20in%20Visual%20Basic.md)   
 [Function Statement](../Topic/Function%20Statement%20\(Visual%20Basic\).md)   
 [Sub Statement](../Topic/Sub%20Statement%20\(Visual%20Basic\).md)   
 [Property Statement](../Topic/Property%20Statement.md)