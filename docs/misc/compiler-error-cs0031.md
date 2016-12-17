---
title: "Compilerfehler CS0031"
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
  - "CS0031"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0031"
ms.assetid: 91f11ae9-9143-41f4-8002-5c38c8ee0651
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0031
Der Konstantenwert 'wert' kann nicht in einen 'typ' konvertiert werden. \(verwenden Sie die unchecked\-Syntax zum Überschreiben\)  
  
 Es wurde versucht, einer Variablen einen Wert zuzuweisen, deren Typ den Wert nicht speichern kann. Weitere Informationen finden Sie unter [Typen](../Topic/Types%20\(C%23%20Programming%20Guide\).md).  
  
 Im folgenden Beispiel wird CS0031 sowohl in checked\- als auch in unchecked\-Kontexten generiert:  
  
```  
// CS0031.cs namespace CS0031 { public class a { public static void Main() { int num = (int)2147483648M; //CS0031 // Try using a larger numeric type instead: // long num = (long)2147483648M; //CS0031 const decimal d = -10M; // Decimal literal unchecked { const byte b = (byte)d; // CS0031 // For small values try using a signed byte instead: // const sbyte b = (sbyte)d; } } } }  
```  
  
## Siehe auch  
 [unchecked](../Topic/unchecked%20\(C%23%20Reference\).md)