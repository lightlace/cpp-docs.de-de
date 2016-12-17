---
title: "Der lambda-Parameter &#39;&lt;Parameter&gt;&#39; verbirgt eine Variable in einem einschlie&#223;enden Block, eine zuvor definierte Bereichsvariable oder eine implizit im Abfrageausdruck deklarierte Variable."
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
  - "bc36641"
  - "vbc36641"
helpviewer_keywords: 
  - "BC36641"
ms.assetid: ee08c366-29d1-4abb-b14c-23ae2b9680e7
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "shoag"
manager: "wpickett"
---
# Der lambda-Parameter &#39;&lt;Parameter&gt;&#39; verbirgt eine Variable in einem einschlie&#223;enden Block, eine zuvor definierte Bereichsvariable oder eine implizit im Abfrageausdruck deklarierte Variable.
Eine Variable in einem Lambdaausdruck weist denselben Namen wie eine zuvor im gleichen Gültigkeitsbereich definierte Variable auf. Dies kann eine Variable in einem einschließenden Codeblock für einen geschachtelten Lambdaausdruck, eine zuvor in einer LINQ\-Abfrage definierte Bereichsvariable oder eine Variable sein, die implizit für eine LINQ\-Abfrage deklariert wird.  
  
 **Fehler\-ID:** BC36641  
  
### So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass alle Variablen im Lambdaausdruck über eindeutige Namen verfügen, die im selben Bereich nicht doppelt vorkommen.  
  
## Siehe auch  
 [Lambda Expressions](../Topic/Lambda%20Expressions%20\(Visual%20Basic\).md)   
 [Introduction to LINQ in Visual Basic](../Topic/Introduction%20to%20LINQ%20in%20Visual%20Basic.md)   
 [LINQ](../Topic/LINQ%20in%20Visual%20Basic.md)