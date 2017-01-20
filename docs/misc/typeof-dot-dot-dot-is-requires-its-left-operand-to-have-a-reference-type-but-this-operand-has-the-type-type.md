---
title: "„TypeOf ... Is“ erfordert, dass der linke Operand einen Verweistyp hat. Dieser Operand hat jedoch den Typ &lt;Typ&gt;."
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
  - "bc30021"
  - "vbc30021"
helpviewer_keywords: 
  - "BC30021"
ms.assetid: a6e76fc8-9c7f-4e55-8b68-e6e7b03a6737
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "shoag"
manager: "wpickett"
---
# „TypeOf ... Is“ erfordert, dass der linke Operand einen Verweistyp hat. Dieser Operand hat jedoch den Typ &lt;Typ&gt;.
Der `TypeOf...Is`\-Ausdruck überprüft die Laufzeittyp\-Kompatibilität einer Objektvariable. Diese Kompatibilität ist für Werttypen nicht definiert.  
  
 **Fehler\-ID:** BC30021  
  
### So beheben Sie diesen Fehler  
  
-   Wenn `Option Strict` \= `Off`, verwenden Sie die `TypeName`\- oder `VarType`\-Funktion, um die Datentypinformationen der Variablen abzurufen.  
  
-   Wenn `Option Strict` \= `On`, bestimmt die Variablendeklaration den Datentyp der Variablen.  
  
## Siehe auch  
 [Comparison Operators in Visual Basic](../Topic/Comparison%20Operators%20in%20Visual%20Basic.md)   
 [NICHT IM BUILD: TypeName\-Funktion \(Visual Basic\)](assetId:///6197bc6c-e8a6-4711-883c-0c95e94e272c)   
 [NICHT IM BUILD: VarType\-Funktion \(Visual Basic\)](assetId:///e820b6fc-faa6-4de4-836a-0466032dc190)   
 [Option Strict Statement](../Topic/Option%20Strict%20Statement.md)