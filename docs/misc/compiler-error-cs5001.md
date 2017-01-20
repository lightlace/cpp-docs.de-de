---
title: "Compilerfehler CS5001"
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
  - "CS5001"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS5001"
ms.assetid: e1e26e75-84e0-47c7-be8a-3c4fd0d6f497
caps.latest.revision: 14
caps.handback.revision: "14"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS5001
Das Programm 'programm' enthält keine als Einstiegspunkt geeignete statische Main\-Methode.  
  
 Dieser Fehler tritt auf, wenn sich in dem Code, aus dem die ausführbare Datei erstellt wird, keine statische [Main](../Topic/Main\(\)%20and%20Command-Line%20Arguments%20\(C%23%20Programming%20Guide\).md)\-Methode mit ordnungsgemäßer Signatur befindet. Dieser Fehler tritt ebenfalls auf, wenn die Eintrittspunktfunktion `Main`, mit falscher Groß\-\/Kleinschreibung definiert ist, etwa als klein geschriebenes `main`.  
  
-   `Main` muss als statisch deklariert sein und [void](../Topic/void%20\(C%23%20Reference\).md) oder [int](../Topic/int%20\(C%23%20Reference\).md) zurückgeben, ferner darf sie entweder keine Parameter oder einen Parameter vom Typ `string[]` besitzen.  
  
## Beispiel  
 Im folgenden Beispiel wird CS5001 generiert:  
  
```  
// CS5001.cs // CS5001 expected public class a { // Uncomment the following line to resolve. // static void Main() {} }  
```  
  
## Siehe auch  
 [Main\(\) und Befehlszeilenargumente](../Topic/Main\(\)%20and%20Command-Line%20Arguments%20\(C%23%20Programming%20Guide\).md)