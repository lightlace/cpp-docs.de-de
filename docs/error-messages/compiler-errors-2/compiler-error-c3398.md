---
title: "Compilerfehler C3398"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C3398"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3398"
ms.assetid: 26f8c8a4-526f-415b-8047-155c5cd4f180
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3398
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Operator': Konvertierung von 'function\_signature' in 'function\_pointer' nicht möglich. Der Quellausdruck muss ein Funktionssymbol sein.  
  
 Wenn die [\_\_clrcall](../../cpp/clrcall.md)\-Aufrufkonvention bei der Kompilierung mit **\/clr** nicht angegeben ist, generiert der Compiler zwei Einstiegspunkte \(Adressen\) für jede Funktion, einen systemeigener Einstiegspunkt und einen verwalteten Einstiegspunkt.  
  
 Standardmäßig gibt der Compiler den systemeigenen Einstiegspunkt zurück, aber es gibt einige Fälle, in denen der verwaltete Einstiegspunkt erwünscht ist \(z. B. beim Zuweisen der Adresse zu einem `__clrcall`\-Funktionszeiger\). Damit der Compiler den verwalteten Einstiegspunkt in einer Zuordnung zuverlässig auswählen kann, muss die rechte Seite ein Funktionssymbol sein.