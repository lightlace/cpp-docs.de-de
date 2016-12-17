---
title: "Compilerfehler CS1520"
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
  - "CS1520"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1520"
ms.assetid: 1aeeee83-52a6-45dc-b197-a9a6de3a220c
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS1520
Die Methode muss einen Rückgabetyp besitzen.  
  
 Eine Methode, die in einer Klasse, Struktur oder Schnittstelle deklariert ist, muss einen expliziten Rückgabetyp haben. Im folgenden Beispiel hat die Square\-Methode einen Rückgabewert des Typs [string](../Topic/string%20\(C%23%20Reference\).md):  
  
```  
class Test { string IntToString(int i) { return i.ToString(); } }  
```  
  
 Im folgenden Beispiel wird CS1520 generiert:  
  
```  
// CS1520a.cs public class x { // Method declaration missing a return type MyMethod()   // CS1520 {} // Add the desired return type: // void MyMethod2() // { } public static void Main() { } }  
```  
  
 Dieser Fehler kann auch auftreten, wenn sich die Schreibweise des Namens eines Konstruktors von der Klassen\- oder Strukturdeklaration unterscheidet, wie im folgenden Beispiel. Da der Name nicht mit dem Klassennamen identisch ist, interpretiert der Compiler ihn als eine normale Methode, nicht als einen Konstruktor, und erzeugt den Fehler:  
  
```  
// CS1520b.cs public class Class1 { // Should be Class1, not class1 public class1()   // CS1520 { } static void Main() { } }  
```  
  
## Siehe auch  
 [Methoden](../Topic/Methods%20\(C%23%20Programming%20Guide\).md)   
 [Konstruktoren](../Topic/Constructors%20\(C%23%20Programming%20Guide\).md)