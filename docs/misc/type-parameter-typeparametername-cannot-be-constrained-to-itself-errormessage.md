---
title: "Typparameter &lt;Typparametername&gt; kann nicht auf sich selbst beschr&#228;nkt werden: &lt;Fehlermeldung&gt;."
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
  - "bc32113"
  - "vbc32113"
helpviewer_keywords: 
  - "BC32113"
ms.assetid: a74128ae-11d0-46bf-8c0b-c7a2bf881d17
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "shoag"
manager: "wpickett"
---
# Typparameter &lt;Typparametername&gt; kann nicht auf sich selbst beschr&#228;nkt werden: &lt;Fehlermeldung&gt;.
Eine Einschränkungsliste für einen Typparameter enthält den Typparameter selbst.  
  
 Eine Einschränkungsliste für einen Typparameter kann eine beliebige Anzahl von Schnittstellen und höchstens eine Klasse angegeben. Ein für diesen Typparameter angegebenes Typargument muss jede angegebene Schnittstelle implementieren und von der angegebenen Klasse erben. Wenn der Compiler auf eine Einschränkungsliste trifft, benötigt er bereits definierte Schnittstellen und Klassen. Ein Typparameter wird erst dann als definierter Typ betrachtet, wenn er durch ein geeignetes Typargument ersetzt wird, das vom Code bereitgestellt wird, der den generische Typ erstellt.  
  
 **Fehler\-ID:** BC32113  
  
### So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie die Schreibweise des Typparameters und der Einschränkungen in seiner Einschränkungsliste.  
  
2.  Wenn keine Rechtschreibfehler vorhanden sind, entfernen Sie den Namen des Typparameters aus seiner Einschränkungsliste. Er kann nicht auf sich selbst beschränkt werden.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [Type List](../Topic/Type%20List%20\(Visual%20Basic\).md)