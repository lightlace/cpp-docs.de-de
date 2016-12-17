---
title: "Compilerfehler CS1560"
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
  - "CS1560"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1560"
ms.assetid: 772c4543-6c8d-453f-ae3f-d333528eb8b3
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1560
Ein ungültiger Dateiname wurde für die Präprozessordirektive angegeben. Der Dateiname ist zu lang oder kein gültiger Dateiname.  
  
 Der Dateiname, der mit [\#line](../Topic/%23line%20\(C%23%20Reference\).md) angegeben wurde, überschreitet \_MAX\_PATH \(256 Zeichen\), oder die Zeile, auf der `#line` gefunden wurde, überschreitet 2000 Zeichen.  
  
## Beispiel  
 Im folgenden Beispiel wird CS1560 generiert:  
  
```  
// cs1560.cs using System; class MyClass { public static void Main() { Console.WriteLine("Normal line #1."); #line 21 "MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890MyFile1234567890.txt"   // CS1560 } }  
```