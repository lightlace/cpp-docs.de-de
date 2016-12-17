---
title: "Compilerfehler CS1021"
ms.custom: na
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CS1021"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1021"
ms.assetid: 0346ba58-d7cd-40bd-bcad-b90117fdc9b5
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1021
Die integrale Konstante ist zu groß.  
  
 Ein Wert, der einem [integralen Typ](../Topic/Integral%20Types%20Table%20\(C%23%20Reference\).md) zugewiesen wurde, ist größer als der größtmögliche ganzzahlige Wert ohne Vorzeichen.  
  
 Im folgenden Beispiel wird CS1021 generiert:  
  
```  
// CS1021.cs enum F : int { a=(int)2590000000000000000000   // CS1021 } public class clx { public static void Main() { } }  
```