---
title: "Problembehandlung bei Ausnahmen: Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "Microsoft.VisualStudio.Tools.Applications.Runtime.ControlNotFoundException-Ausnahme"
ms.assetid: d780b8cc-c3f1-45ed-8f8e-3f8728a4b770
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "mblome"
manager: "douge"
---
# Problembehandlung bei Ausnahmen: Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException
Eine <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>\-Ausnahme wird ausgelöst, wenn ein <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> eine Zeile nicht mit dem angegebenen Format analysieren kann.  
  
 Die `Error Line`\-Eigenschaft des Ausnahmeobjekts enthält den Text der Zeile, die den Fehler verursacht.  
  
## Tipps  
 **Stellen Sie sicher, dass der TextFieldType\-Parameter und der Delimiter\-Parameter korrekt definiert sind.**  
 Der `TextFieldType` \(mit Trennzeichen oder mit fester Breite\) muss dem Format der Datei entsprechen. Wenn `TextFieldType` den Wert `FixedWidth` besitzt, überprüfen Sie, ob die `FieldWidths`\-Eigenschaft korrekt festgelegt wurde. Wenn `TextFieldType` den Wert `Delimited` besitzt, überprüfen Sie, ob die `Delimiters`\-Eigenschaft korrekt festgelegt wurde.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>   
 [Parsing Text Files with the TextFieldParser Object](../Topic/Parsing%20Text%20Files%20with%20the%20TextFieldParser%20Object%20\(Visual%20Basic\).md)   
 [How to: Read From Comma\-Delimited Text Files](../Topic/How%20to:%20Read%20From%20Comma-Delimited%20Text%20Files%20in%20Visual%20Basic.md)   
 [How to: Read From Fixed\-width Text Files](../Topic/How%20to:%20Read%20From%20Fixed-width%20Text%20Files%20in%20Visual%20Basic.md)