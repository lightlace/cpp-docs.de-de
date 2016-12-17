---
title: "Ein Ausdruck vom Typ &#39;&lt;typname1&gt;&#39; kann nicht dem Typ &#39;&lt;typname2&gt;&#39; angeh&#246;ren"
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
  - "vbc31430"
  - "bc31430"
helpviewer_keywords: 
  - "BC31430"
ms.assetid: 1d527033-3f6f-4945-b1d3-5ef59a1e1b53
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "shoag"
manager: "wpickett"
---
# Ein Ausdruck vom Typ &#39;&lt;typname1&gt;&#39; kann nicht dem Typ &#39;&lt;typname2&gt;&#39; angeh&#246;ren
Ein `TypeOf`...`Is`\-Ausdruck überprüft eine Objektverweisvariable auf einen Datentyp, den er nicht enthalten kann.  
  
 In manchen Fällen kann der Compiler bestimmen, dass ein `TypeOf`...`Is`\-Test zwangsläufig fehlschlagen muss, z. B. wenn zwischen zwei Klassen keine Vererbungsbeziehung besteht.  
  
 Dieser Fehler kann durch folgenden Code generiert werden.  
  
 `Dim refVar as System.Windows.Forms.Form`  
  
 `If TypeOf refVar Is System.Array`  
  
 `End If`  
  
 Da <xref:System.Windows.Forms.Form> und <xref:System.Array> völlig voneinander unabhängige Typen sind, kann der Compiler bestimmen, dass der Ausdruck `TypeOf`...`Is` für jeden Wert von `refVar` den Wert `False` zurückgibt.  
  
 **Fehler\-ID:** BC31430  
  
### So beheben Sie diesen Fehler  
  
-   Testen Sie die Variable auf einen realistischen Datentyp, oder entfernen Sie den `TypeOf`...`Is`\-Test ganz.  
  
## Siehe auch  
 [TypeOf Operator](../Topic/TypeOf%20Operator%20\(Visual%20Basic\).md)   
 [How to: Determine What Type an Object Variable Refers To](../Topic/How%20to:%20Determine%20What%20Type%20an%20Object%20Variable%20Refers%20To%20\(Visual%20Basic\).md)