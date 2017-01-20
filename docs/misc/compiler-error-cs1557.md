---
title: "Compilerfehler CS1557"
ms.custom: na
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS1557"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1557"
ms.assetid: 1615e028-aeb7-4788-bd87-8e49e502d698
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1557
"Klasse" befindet sich in einer anderen Ausgabedatei und kann daher nicht für die Main\-Methode verwendet werden.  
  
 Die [\/main](../Topic/-main%20\(C%23%20Compiler%20Options\).md)\-Compileroption wurde für eine Ausgabedatei in einer Kompilierung mit mehreren Ausgabedateien angegeben. Die Klasse wurde aber nicht im Quellcode für die \/main\-Kompilierung gefunden, sondern sie wurde in einer Quellcodedatei für eine der anderen Ausgabedateien der Kompilierung gefunden.