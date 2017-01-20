---
title: "Compilerfehler CS0555"
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
  - "CS0555"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0555"
ms.assetid: e4b2f890-98b4-4578-b1de-ebaafc8b3da2
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "wiwagn"
manager: "wpickett"
---
# Compilerfehler CS0555
Ein benutzerdefinierter Operator kann kein Objekt vom einschließenden Typ übernehmen oder in ein Objekt des einschließenden Typs konvertieren.  
  
 Benutzerdefinierte Konvertierungen in Werte einer einschließenden Klasse sind nicht zulässig. Ein solcher Operator ist nicht erforderlich.  
  
 Im folgenden Beispiel wird CS0555 generiert:  
  
```  
// CS0555.cs public class MyClass { // delete the following operator to resolve this CS0555 public static implicit operator MyClass(MyClass aa)   // CS0555 { return new MyClass(); } public static void Main() { } }  
```