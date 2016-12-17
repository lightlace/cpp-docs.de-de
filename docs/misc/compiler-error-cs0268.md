---
title: "Compilerfehler CS0268"
ms.custom: na
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS0268"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0268"
ms.assetid: a4faca71-8b4a-4f22-a89e-59d92ced48cb
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0268
Der importierte Typ „type“ ist ungültig. Er enthält eine Basisklassen\-Ringabhängigkeit.  
  
 Dieser Fehler tritt auf, wenn ein aus einer anderen Sprache importierter Typ eine Basisklassen\-Ringabhängigkeit aufweist. Ein solcher Typ kann in einem C\#\-Programm nicht verwendet werden. Um diesen Fehler zu beheben, überprüfen Sie Typen, die aus anderen Sprachen in referenzierte Assemblys oder Module importiert wurden.