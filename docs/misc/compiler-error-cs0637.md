---
title: "Compilerfehler CS0637"
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
  - "CS0637"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0637"
ms.assetid: 02f6964c-0fcc-4f81-8ebb-0330aecdde19
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0637
Das FieldOffset\-Attribut ist für statische oder konstante Felder nicht zulässig.  
  
 Das [FieldOffset](frlrfsystemruntimeinteropservicesfieldoffsetattributeclasstopic)\-Attribut darf nicht für Felder verwendet werden, die mit [static](../Topic/static%20\(C%23%20Reference\).md) oder [const](../Topic/const%20\(C%23%20Reference\).md) gekennzeichnet sind.  
  
 Im folgenden Beispiel wird CS0637 generiert:  
  
```  
// CS0637.cs using System; using System.Runtime.InteropServices; [StructLayout(LayoutKind.Explicit)] public class MainClass { [FieldOffset(3)]   // CS0637 public static int i; public static void Main () { } }  
```