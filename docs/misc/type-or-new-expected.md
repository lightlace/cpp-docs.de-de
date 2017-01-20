---
title: "Typ oder „New“ erwartet."
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
  - "vbc32092"
  - "bc32092"
helpviewer_keywords: 
  - "BC32092"
ms.assetid: b3041c1d-837c-4d58-bbb4-5c46f227b66d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "shoag"
manager: "wpickett"
---
# Typ oder „New“ erwartet.
Ein Typparameter in der Deklaration eines generischen Typs führt eine Einschränkungsliste mit dem `As`\-Schlüsselwort ein, gibt aber keine gültige Einschränkung an.  
  
 Eine Einschränkung für einen Typparameter muss eine gültige Klasse oder Schnittstelle bzw. eines der Schlüsselwörter `Class`, `Structure` oder `New` sein. Wenn Sie eine ungültige oder keine Einschränkung angeben, generiert der Compiler diesen Fehler.  
  
 **Fehler\-ID:** BC32092  
  
### So beheben Sie diesen Fehler  
  
1.  Bestimmen Sie, wie der Typparameter eingeschränkt werden soll, und geben Sie die entsprechende Einschränkung in der Einschränkungsliste an.  
  
2.  Wenn Sie den Typparameter durch eine Klasse oder Schnittstelle einschränken möchten, stellen Sie sicher, dass die Einschränkung die richtige Schreibweise verwendet.  
  
3.  Denken Sie daran, dass mehrere Einschränkungen für einen einzelnen Typparameter durch Kommas voneinander getrennt werden und die Einschränkungsliste in geschweifte Klammern eingeschlossen \(`{ }`\) wird.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Class \(Visual Basic\)](assetId:///0777c6e6-46bc-451b-ad70-57b49d4ef4f7)   
 [Structure \(Visual Basic\)](assetId:///263ce115-ac36-4c05-8cb7-0e0eead5c6d0)   
 [New Operator](../Topic/New%20Operator%20\(Visual%20Basic\).md)   
 [Type List](../Topic/Type%20List%20\(Visual%20Basic\).md)